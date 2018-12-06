---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
header-img: /assets/img/group_photo_workshop.jpg
inverse-img: false
---
<html>

<head>
  <style>
    h3		{color: rgb(44,196,251);display: inline; font-weight: bold;}
  </style>
</head>

<body>
	<div class="BlogPosts">
		<h1 class="page-title">Blog posts:</h1>
		{% for post in site.posts %}
		<div class="post-preview" style="padding-left: 15px;">
			<a href="{{ post.url | prepend: site.baseurl }}">
				<h2 class="page-title">            {{ post.title }}
				</h2>
				{% if post.subtitle %}
				<h3 class="page-subtitle">
					{{ post.subtitle }}
				</h3>
				{% endif %}
			</a>
			<p class="post-meta" style="margin-bottom:5px">Posted by {{ post.author }} on {{ post.date | date: "%B %-d, %Y" }}</p>
			<div class="notepad-index-post-tags" style="">
				{% for tag in post.tags %}<a>{{ tag | capitalize }}</a>{% unless forloop.last %}&nbsp;{% endunless %}{% endfor %}
			</div>
		</div>
		<hr>
		{% endfor %}
	</div>
	&emsp;
	<div class="MainBody">
		<h1 class="page-title">Our Philosophy:</h1>
		<div class="Philosophy" style="padding-left: 15px;">
			<p text-align="justify">
			<h3>Delft:</h3> we belong to Civil Engineering and Geoscience (CEG) Department at Civil Engineering Faculty of TU Delft. The development team directly linked to the new GeoEnergy program which connects Geology, Geophysics and Petroleum Engineering sections of the department. </p>
			<p text-align="justify">
			<h3>Advanced:</h3> the simulation framework is based on the recently proposed Operator-Based Linearization (OBL) approach, which helps to decouple the complex nonlinear physics and advanced unstructured discretization from the core simulation engine. The framework is targeting the solution of forward and inverse problems.
			</p>
			<p text-align="justify">
			<h3>Research:</h3> the development team includes five PhD students from the CEG department and multiple MSc students working on their thesis project on DARTS platform. The simulation platform is developed within Delft Advanced Reservoir Simulation (DARSim) program and linked to multiple research in the area of reservoir simulation, inverse modeling and uncertainty quantification.    
			</p>
			<p text-align="justify">
			<h3>Terra:</h3> the developed framework is utilized for forward and inverse problems in petroleum engineering, low- and high-enthalpy geothermal applications, subsurface storage and subsurface integrity. The primary focus and developed capabilities are currently cover low-enthalpy geothermal operations which include multicomponent multiphase flow of mass and heat with complex chemical interactions. Another focus is thermal-compositional processes for Enhanced Oil Recovery.  
			</p>
			<p text-align="justify">
			<h3>Simulator:</h3> the main simulation kernel implemented on multi-core CPU and many-core GPU architectures. Advance multiscale nonlinear formulation improves the performance of forward and inverse models. Additional afford invested in representative proxy models for complex subsurface processes including multiphase multicomponent flow.  
			</p>
		</div>
	</div>
</body>
</html>
Some general links: <br>
[TU Delft website][TUD] <br>
[Our GitHub repository][link_to_repo] <br>

[TUD]: https://www.tudelft.nl
[link_to_repo]: https://github.com/darts-web/darts-web
