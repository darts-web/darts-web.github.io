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
  </style>
</head>

<body>
<h1 class="page-title">{{ page.title }}</h1>

<h2><a id="Mark">Scalable hybrid framework for a geothermal simulator </a></h2>
<div class="sub-section" style="padding-left: 15px;">
	<p text-align="justify">Various novel computing architectures, like massively parallel and multi-core, as well as computing accelerators, like GPUs or TPUs, continue to emerge regularly.  
	   In order to harvest the performance benefits of these architectures to the full extent and speed up simulation,  the source code has to be inevitably rewritten, sometimes almost completely. 
           The biggest challenge here in terms of complexity, variety and size is linearization procedure, since it depends on the governing equations, choice of primary unknowns, physical/chemical 
           phenomena taken into account, and other factors. In this project, we demonstrate how to extract complex physics-related computations from the main simulation loop, leaving only an algebraic 
           multilinear interpolation kernel instead.</p>
	   <p> The key element here is operator-based linearization (OBL)<sup>1</sup>. The state-based terms of governing equations are parametrized in the physical space of the 
           problem forming dynamically expanding lookup tables. These tables are used in linearization to approximate operators along with derivatives with respect to governing unknowns using piecewise 
           multilinear interpolation in physical space.  The method not only significantly reduces the amount of property-related computations, but detaches physics and simulation kernels. In combination 
           with linear solvers, which usually have made available soon once the new architecture is introduced, the approach accommodates execution of the entire nonlinear loop on the latest hardware and 
           computational architectures<sup>2</sup>. The balance between the accuracy and performance is managed via the approximation error of physical description. </p>
	   <p> The framework is implemented in C++11 and exposed
           into Python coupling the flexibility of the script language with the performance of C++. Moreover, particular framework components can be extended in Python and still be involved in C++ simulation 
           process. In addition, all fluid / rock properties, involved in computation of state operators, can be derived in Python without serious impact on overall simulation performance thanks to OBL. The 
           integrated simulation framework exploits the approach to provide the flexible, modular, computationally efficient modeling package for various applications, including geothermal<sup>3</sup>, 
           thermal-compositional<sup>4</sup>, and reactive compositional problems<sup>5</sup>. </p>
	<hr>
</div>
<br>

<h2><a id="Stephan">Thermal flow and transport with dissolution </a></h2>
<div class="sub-section" style="padding-left: 15px;">
	<p text-align="justify">My current work involving DARTS consists of ...</p>
	<p text-align="justify"><img src="{{ site.baseurl }}/assets/img/project_photos/example_gif.gif">
	<br>
	<em>Dissolution patterns.</em></p>
	<p>My other acedemic interests lie in Uncertainty Quantification ...</p> 
	<hr>
</div>
<br>

<h2><a id="Yang">Flow and reactive transport in high-enthalpy geothermal systems </a></h2>
<div class="sub-section" style="padding-left: 15px;">
	<p text-align="justify"> This project focus on the nonlinear convergence associated with flow, phase-transition and chemical reactions in high-enthalpy geothermal systems. 
	In comparison with low-enthalpy geothermal systems limited to production of hot water, the obvious features of high-enthalpy systems are significantly higher temperature and two-phase (water-steam) 
	dominated physical behaviors. Phase transition is happening due to the heat exchange between the injected cold water and in-situ rock/fluid. In addition, the chemical equilibrium, present in the 
	original reservoir, may be disturbed by both the fluid transport and reaction with injected water containing different temperature and chemical species which become more complicated due to liquid-vapor 
	phase transition with salt dissolution and precipitation. </p>
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
	very near the well, crucial to overall injectivity, in which liquid mobility is much greater than that further from the well.</p>
	<p text-align="justify"><img src="{{ site.baseurl }}/assets/img/foam.png"> 
	<br>
	<em>Foam injection experimental results.</em></p>        

	<p> This project aims to predictive modeling of this phenomena. An accurate model should be constructed at continuous core scale and incorporate all important phenomena -
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
	</ol>
</h5>
