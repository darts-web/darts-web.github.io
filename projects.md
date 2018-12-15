---
layout: page
title: Projects
permalink: /projects/
author: Stephan de Hoop
---
<html>

<head>
  <style>
    h2  {
		color: rgb(44,196,251);
		display: inline; 
		font-weight: bold;
		}
	.center {
	  display: block;
	  margin-left: auto;
	  margin-right: auto;
	  width: 85%;
		}
  </style>
</head>

<body>
<h1 class="page-title">{{ page.title }}</h1>

<h2><a id="Mark">Scalable hybrid framework for a geothermal simulator </a></h2>
<div class="sub-section" style="padding-left: 15px;">
	<p text-align="justify">Various novel computing architectures, like massively parallel and multi-core, as well as computing accelerators, 
	like GPUs or TPUs, continue to emerge regularly.  
	In order to harvest the performance benefits of these architectures to the full extent and speed up simulation,  the source code has to be 
	inevitably rewritten, sometimes almost completely. The biggest challenge here in terms of complexity, variety and size is linearization procedure, 
	since it depends on the governing equations, choice of primary unknowns, physical/chemical phenomena taken into account, and other factors. 
	In this project, we demonstrate how to extract complex physics-related computations from the main simulation loop, leaving only an algebraic 
        multilinear interpolation kernel instead.</p>
	<p text-align="justify"> The key element here is operator-based linearization (OBL)<sup>1</sup>. The state-based terms of governing equations 
	are parametrized in the physical space of the problem forming dynamically expanding lookup tables. These tables are used in linearization to 
	approximate operators along with derivatives with respect to governing unknowns using piecewise multilinear interpolation in physical space.
	<img src="{{ site.baseurl }}/assets/img/project_photos/operator_coarsening.gif" width="70%" class="center">
	<em>Typical representation of operator in 2D parameter-space (pressure-composition).</em> </p>
	<p text-align="justify"> The method not only significantly reduces the amount of property-related computations, but detaches physics and simulation
	kernels. In combination with linear solvers, which usually have made available soon once the new architecture is introduced, the approach accommodates 
	execution of the entire nonlinear loop on the latest hardware and computational architectures<sup>2</sup>. The balance between the accuracy 
	and performance is managed via the approximation error of physical description.
	<img src="{{ site.baseurl }}/assets/img/project_photos/GPUvsCPU.png" width="75%" class="center">
	<em> Time spent on linerization of 3-component compositional run in full SPE10 (728 nonlinear iterations).</em> </p>
	<p text-align="justify"> The framework is implemented in C++11 and exposed into Python coupling the flexibility of the script language with 
	the performance of C++. Moreover, particular framework components can be extended in Python and still be involved in C++ simulation 
        process. In addition, all fluid / rock properties, involved in computation of state operators, can be derived in Python without serious impact 
	on overall simulation performance thanks to OBL. The integrated simulation framework exploits the approach to provide the flexible, modular, 
	computationally efficient modeling package for various applications, including geothermal<sup>3</sup>, thermal-compositional<sup>4</sup>, and 
	reactive compositional problems<sup>5</sup>. </p>
	<hr>
</div>
<br>

<h2><a id="Stephan">Thermal flow and transport with dissolution </a></h2>
<div class="sub-section" style="padding-left: 15px;">
	<p text-align="justify">Increasing demand for geothermal energy in the Netherlands has led to the investigation of high enthalpy carbonate 
	reservoirs, located in the Lower Carboniferous (Dinantian carbonates). Pilot projects have encountered heavily karstified reservoir intervals 
	during the drilling process, resulting in unpredicted hazards. The origin of the karst has been interpreted as a combination of epigenic and 
	hypogenic processes<sup>6</sup>. Predicting the spatial distribution of hypogenic caves and other discontinuity networks in the subsurface is 
	currently in an under developed state, mainly due our inability to obtain images of the subsurface at sufficient resolution but also due to the 
	high complexity of the system (interplay between chemical, mechanical, and flow processes).</p>
	<p text-align="justify">This project mainly focusses on the development of a reactive transport module for DARTS, in particular on the 
	implementation of the Element Based Formulation<sup>5</sup> and fully unstructured dicretization methods for (naturally) fractured 
	reservoirs<sup>7</sup>.
	<img src="{{ site.baseurl }}/assets/img/project_photos/example_gif.gif" width="75%" class="center">
	<br>
	<em>Preliminary results on dissolution patterns in carbonates, obtained with the Reactive Transport and unstructured discretization modules in 
	DARTS.</em></p>
	<p text-align="justify">The next steps of this research are on combining three methods: 1) large-scale high-resolution outcrop data, acquired 
	with a Mobile Mapping System (handheld LiDAR); 2) small-scale laboratory experiments studying the interplay between dissolution of the fracture 
	plane under mechanical stress; 3) integrating this in numerical models acquired with DARTS simulation framework. This will lead to improved 
	predictions on the spatial distribution of karst and other discontinuity networks in the subsurface.
	<img src="{{ site.baseurl }}/assets/img/project_photos/comparison_lidar_and_photos.png" width="75%" class="center">
	<br>
	<em>Comparison between the High-Resolution LiDAR point cloud data set and color photographs (from inside the cave systems).</em></p>
	<p text-align="justify">My other acedemic interests lie in Uncertainty Quantification, particularly in using coarse-scale models for fine-scale predictions.
	<img src="{{ site.baseurl }}/assets/img/project_photos/uncertainty_trajectory.png" width="75%" class="center">
	<br>
	<em>Taken from de Hoop et al. (2018)<sup>8</sup>. Here we have proposed a method to use coarse-scale models in the prediction of fine-scale response uncertainty.</em></p>
	<hr>
</div>
<br>        
<h2><a id="Yang">Flow and reactive transport in high-enthalpy geothermal systems </a></h2>
<div class="sub-section" style="padding-left: 15px;">
	<p text-align="justify">This project will focus on the phase-transition induced nonlinear flow problem, in combination with chemical reactions, 
	within high-enthalpy geothermal systems. In comparison with low-enthalpy geothermal systems limited to production of hot water, the obvious 
	features of high-enthalpy systems are significantly higher temperature and steam (or water-steam) dominated physical behaviors. Phase transition 
	is happening due to the heat exchange between the injected cold water and in-situ rock/fluid. In addition, the chemical equilibrium, present in 
	the original reservoir, may be disturbed by both the fluid transport and reaction with injected water containing different temperature and 
	chemical species which can become complicated by liquid-vapor phase transition with salt dissolution and precipitation.</p>
	<p text-align="justify">Because of phase transition and the large variation in thermo-dynamic properties between liquid water and steam, the 
	nonlinear numerical solution of governing equations in fully-implicit approximation can experience difficulties commonly known as ‘negative 
	compressibility’.
	<img src="{{ site.baseurl }}/assets/img/project_photos/neg_compr.gif" width="60%" class="center">
	<br>
	<em>Convergence map using Newton update.</em> </p>
	<p text-align="justify"> A multi-level physics parameterization approach is proposed to solve this problem within Operator-base Linearization (OBL) 
	framework<sup>1</sup>. In OBL approach, the continuous operators in the covering equations, related to different physical mechanisms (e.g. 
	convection or conduction), are translated into multi-dimensional tables. In the course of simulation, only the supporting points are evaluated 
	based on the reference physics while points between them are interpolated. The coarser the physics is, the more linear the operators become. 
	In our continuation approach, we start with the coarse approximation of the governing physics in pressure-enthalpy parameter-space. Due to a 
	more linear form of operators, only a few nonlinear iterations reduce residual below the predefined tolerance. Next, the OBL approximation is 
	modified towards the reference nonlinear physics and a few more iterations bring the residual below the tolerance again. With the refinement in 
	physics, the solution will gradually approach the final results where residual will satisfy the convergence criteria of the reference physics.
	<img src="{{ site.baseurl }}/assets/img/project_photos/neg_compr_cont.gif" width="60%" class="center"> 
	<br>
	<em>Convergence map using OBL continuation.</em></p>
	<p text-align="justify"> The proposed continuation approach avoids the negative compressibility phenomena since the problem at coarser 
	approximation has a unique gradient pointing towards the correct solution. The proposed approch is unconditionally stable as can be seem in figure 
	below. As a result, simulation can perform at larger timesteps in comparison to the traditional Newton-based nonlinear solution.
	<img src="{{ site.baseurl }}/assets/img/project_photos/convergence_map.png" width="100%" class="center">
	<em>Convergence map for regular initial guesses for Newton (left) and OBL-contunuity (right).</em> </p>
	<br>                                                  
	<hr>
</div>
<br>

<h2><a id="Xiaocong">Modeling of variation in liquid mobility in foam EOR </a></h2>
<div class="sub-section" style="padding-left: 15px;">
	<p text-align="justify"> Liquid injectivity directly following foam is very poor. Liquid first fingers through the trapped foam. It then dissolves gas trapped within the fingers, and overall 
	mobility rises sharply. During prolonged gas injection following foam, however, a region forms near the inlet and slowly propagates downstream in which gas mobility is much greater. The abrupt 
	rise in gas mobility appears to reflect a significant decline in water saturation. This decline reflects in part liquid evaporation, and also pressure-driven flow and capillary effects on the 
	core scale. In this region, the mobility of subsequently injected liquid is much greater than downstream, and liquid sweeps the entire core cross-section rather than a single finger. Mobility 
	in the region of liquid fingering is insensitive to the quality of foam injected before gas and the duration of the period of gas injection. These results suggest that there is a small region 
	very near the well, crucial to overall injectivity, in which liquid mobility is much greater than that further from the well.
	<img src="{{ site.baseurl }}/assets/img/project_photos/foam.png"> 
	<em>Foam injection experimental results<sup>9</sup>.</em> </p>
	<p text-align="justify"> This project aims to predictive modeling of this phenomena. An accurate model should be constructed at continuous core scale and incorporate all important phenomena -
	phase behavior in the gas-brine system, effective foam model, surfactant model with shear-thinning rheology etc. Once the model is constructed, it will be implemented in ADGPRS framework with 
	all important governing properties. This model will be compared with experiments and used as an initial guess for a data-driven OBL-based model. Next, the OBL model will be regressed to the 
	experimental data and serve as a platform for numerical upscaling to the reservoir (field) scale. </p>
	<hr>
</div>
<br>

<h2><a id="Kiarash">Dynamic simulation of the geothermal well performance </a></h2>
<div class="sub-section" style="padding-left: 15px;">
	<p text-align="justify"> Recently, the innovative idea of the geothermal well with the composite well has been proposed. There are significant advantages that composite well can bring to 
	the industry including lower installation cost, resistance to corrosion, and the transparency for monitoring the near well area. Despite this, the long term exploitation of this casing may 
	introduce additional risks and uncertainties, mechanical deformation and chemical interactions with the fluid and the reservoirs. In addition, the hydrocarbon co-production lead to the multiphase 
	flow in the well which can have a strong impact on the performance of reservoirs and surface facilities.</p> 
	<p> In order to use such technologies intelligently, it requires the robust model to capture efficiently the above-mentioned physics in the well.  We will design a numerical framework for predictive 
	simulation and monitoring of geothermal wells taking into account, thermal, hydraulic, mechanical and chemical interactions coupled with the flow in wellbore and near wellbore  porous media. This 
	framework will be based on the farther enhanced multi-segmented well model originated from petroleum related reservoir simulation.</p>
	<hr>
</div>
<br>

<h2><a id="References">References: </a></h2>
<h5>
	<ol>
	  <li> Voskov, D.V, 2017. Operator-based linearization approach for modeling of multiphase multi-component flow in porous media, Journal of Computational Physics, 337, 275-288. 
		<a href = "https://doi.org/10.1016/j.jcp.2017.02.041" target="_blank">doi:10.1016/j.jcp.2017.02.041</a>
	  </li>
	  <li> Khait, M., D. Voskov, 2017. GPU-offloaded general-purpose simulator for multiphase flow in porous media, SPE Reservoir Simulation Conference, pp. 1293-1302. 
		<a href = "https://doi.org/10.2118/182663-MS" target="_blank">doi:10.2118/182663-MS</a>
	  </li>
	  <li> Khait M., D. Voskov, 2018. Operator-based linearization for efficient modeling of geothermal processes, Geothermics, 74, 7-18. 
		<a href = "https://doi.org/10.1016/j.geothermics.2018.01.012" target="_blank">doi:10.1016/j.geothermics.2018.01.012</a>
	  </li>
	  <li> Khait, M., D. Voskov, 2018. Adaptive parameterization for solving of thermal/compositional nonlinear flow and transport with buoyancy, SPE Journal, 23 (2), pp. 522-534. 
		<a href = "https://doi.org/10.2118/182685-PA" target="_blank">doi:10.2118/182685-PA</a>
	  </li>
	  <li> Kala, K., D. Voskov, 2018. Parameterization of element balance formulation in reactive compositional flow and transport, 16th European Conference on the Mathematics of Oil Recovery, ECMOR. 
		<a href = "https://doi.org/10.3997/2214-4609.201802113" target="_blank">doi:10.3997/2214-4609.201802113</a>
	  </li>
	  <li> Reijmer, J. J., Johan, H., Jaarsma, B., & Boots, R. (2017). Seismic stratigraphy of dinantian carbonatesin the southern netherlands and northern belgium.Netherlands Journal of Geosciences,96(4),353–379. 
		<a href = "https://doi.org/10.1017/njg.2017.33" target="_blank">doi:10.1017/njg.2017.33</a>
	  </li>
	  <li> Karimi-Fard, M., Durlofsky, L. J., & Aziz, K. (2003, January). An efficient discrete fracture model applicable for general purpose reservoir simulators. In SPE Reservoir Simulation Symposium. Society of Petroleum Engineers. 
		<a href = "https://doi.org/10.2118/79699-MS" target="_blank">doi:10.2118/79699-MS</a>
	  </li>
	  <li> de Hoop, S., Voskov, D., Vossepoel, F., & Jung, A. (2018). Quantification of coarsening effect on response uncertainty in reservoir simulation. In Ecmor xvi-16th european conference on the mathematics ofoil recovery. 
		<a href = "https://10.3997/2214-4609.201802223" target="_blank">doi:10.3997/2214-4609.201802223</a>
	  </li>
	  <li> Gong J., Vincent-Bonnieu S., Kamarul Bahrim R., Groenenboom J., Farajzadeh R., Rossen W. (2018)
		Modelling of liquid injectivity in surfactant-alternating-gas foam enhanced oil recovery. In SPE EOR
		Conference at Oil and Gas West Asia. Society of Petroleum Engineers, 2018.
		<a href = "https://doi.org/10.2118/190435-MS" target="_blank">doi:10.2118/190435-MS</a>
	  </li>
	</ol>
</h5>
