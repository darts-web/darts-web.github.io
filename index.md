---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
header-img: /assets/img/logo_wider.png
inverse-img: true
---
<html>

<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
h3		{color: rgb(44,196,251);display: inline; font-weight: bold;}
* {box-sizing: border-box;}

body { 
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
}

.header {
  overflow: hidden;
  background-color: #f1f1f1;
  padding: 20px 10px;
}

.header a {
  float: left;
  color: black;
  text-align: center;
  padding: 12px;
  text-decoration: none;
  font-size: 18px; 
  line-height: 25px;
  border-radius: 4px;
}

.header a.logo {
  font-size: 25px;
  font-weight: bold;
}

.header a:hover {
  background-color: #ddd;
  color: black;
}

.header a.active {
  background-color: dodgerblue;
  color: white;
}

.header-right {
  float: right;
}

@media screen and (max-width: 100px) {
  .header a {
    float: none;
    display: block;
    text-align: left;
  }
  
  .header-right {
    float: none;
  }
}
</style>
</head>

<body>
	<img style="width: 35%; height: auto;" src="{{site.baseurl}}/assets/img/logo_wider.png" alt="DARTS">
	<div class="MainBody">
		<h1 class="page-title">What is DARTS?</h1>
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
	<div class="BlogPosts">
		<h1 class="page-title">DARTS posts</h1>
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

</body>
</html>
Some general links: <br>
[TU Delft website][TUD] <br>

[TUD]: https://www.tudelft.nl
[link_to_repo]: https://github.com/darts-web/darts-web
