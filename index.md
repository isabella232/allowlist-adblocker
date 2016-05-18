---
title: index
layout: default
---

<div class="section sub-section" id="select-platform">
	<span class="select">iOS</span>
	<span class="select">Desktop</span>
	<span class="select">Android</span>
</div>

<div class="section collapsed" id="select-adblock">
	<div class="sub-section collapsed" id="desktop-list">
		<a class="select" href="{{ site.baseurl }}/abp.html">Adblock Plus</a>
		<a class="select" href="{{ site.baseurl }}/ub.html">uBlock</a>
		<a class="select" href="{{ site.baseurl }}/ubo.html">uBlock Origin</a>
		<a class="select" href="{{ site.baseurl }}/brave.html">Brave Browser</a>
	</div>
	<div class="sub-section collapsed" id="android-list">
		<a class="select" href="{{ site.baseurl }}/abp.html">Adblock Plus</a>
	</div>
	<div class="sub-section collapsed" id="ios-list">
	</div>
</div>

<div id="ajax-target"></div>
<script>
	document.querySelector('#select-platform').addEventListener('click', function (e) {
		if (e.target.className.match(/select/)) {
			e.target.classList.add('selected');
			e.currentTarget.classList.add('selected');
		}
	});
</script>