---
layout: page
title: "Members of DARTS project"
description: "Collaborators working on this project."
---
<html>
<body>
{% for member in site.data.members %} 
	<br>
	<p>
	{% if member.visible == true %}
		<img src="{{ member.img }}" style="margin-top:0px; margin-bottom:5px; margin-right:10px; float:left; width:125px !important">
		
		<h1>{{ member.name }}</h1>
		
		<h2>{{ member.role }}</h2>
		
		{% if member.github %} 
			<span class="social-share-googleplus"><a href="https://github.com/{{ member.github }}" title="Github"><img src="{{ "/assets/img/icons/github-icon.png" | prepend: site.baseurl }}" style="height:20px">Github</a></span> 
		{% endif %}
		
		{% if member.url %}
			<span><a href="{{ member.url }}" title="Website"><img src="{{ "/assets/img/icons/url-icon.png"| prepend: site.baseurl }}" style="height:20px">Website</a></span>
			<br>
		{% endif %}

		{% if member.bio %} 
			{{ member.bio }}
			<br>
		{% endif %}	
		
		{% if member.project_link %}
			<span><a href="{{ member.project_link | prepend: site.baseurl }}" title="Project">Link to project description.</a></span>
		{% endif %}
		<br>
	{% endif %}
	<br>
	<hr>
	</p>
{% endfor %}
</body>
</html>