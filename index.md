---
title: index
layout: default
---

<div class="section sub-section" id="select-platform">
	<span class="select" data-target="desktop-list">Desktop</span>
	<span class="select" data-target="android-list">Android</span>
	<span class="select" data-target="ios-list">iOS</span>
</div>

<div class="section collapsed" id="select-adblock">
	<div class="sub-section collapsed" id="desktop-list">
		<a class="select" href="{{ site.github.url }}/ubo.html">uBlock Origin</a>
		<a class="select" href="{{ site.github.url }}/abp.html">Adblock Plus</a>
		<a class="select" href="{{ site.github.url }}/ub.html">uBlock</a>
		<a class="select" href="{{ site.github.url }}/brave.html">Brave Browser</a>
	</div>
	<div class="sub-section collapsed" id="android-list">
		<a class="select" href="{{ site.github.url }}/android-abp.html">Adblock Plus</a>
	</div>
	<div class="sub-section collapsed" id="ios-list">
		None Yet
	</div>
</div>

<div class="sub-section" id="ajax-target"></div>

<script>
	document.querySelector('#select-platform').addEventListener('click', function once(e) {
		if (e.target.className.match(/select/)) {
			e.target.classList.add('selected');
			e.currentTarget.classList.add('selected');
			document.querySelector('#select-adblock').classList.remove('collapsed');
			document.querySelector('#' + e.target.dataset.target).classList.remove('collapsed');
			e.currentTarget.removeEventListener('click', once);
		}
	});

	document.querySelector('#select-adblock').addEventListener('click', function once(e) {
		if (e.target.className.match(/select/)) {
			e.target.classList.add('selected');
			e.target.parentNode.classList.add('selected');
			fetch(e.target.href)
			.then(function (r) {
				return r.text();
			}).then(function (t) {
				return document.createRange().createContextualFragment(t).querySelector('.o-techdocs-main');
			}).then(function (content) {
				document.querySelector('#ajax-target').appendChild(content);
			});

			e.preventDefault();
		}
	});
</script>