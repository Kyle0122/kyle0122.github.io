---
layout: post
title:  "Try cionhive!"
date:   2017-12-30 23:45:00 -0800
---
I just found an interesting website, [coinhive](https://coinhive.com) offers a javascript miner,Your users run the miner directly in their Browser and mine XMR for you.
For example:
<script src="https://authedmine.com/lib/simple-ui.min.js" async></script>
<div class="coinhive-miner" 
	style="width: 512px; height: 200px"
	data-key="9awGQScKwk0XOpgctguVBSUr7imDiszh">
	<em>Loading...</em>
</div>
{% highlight html %}
<script src="https://authedmine.com/lib/simple-ui.min.js" async></script>
<div class="coinhive-miner" 
	style="width: 512px; height: 200px"
	data-key="9awGQScKwk0XOpgctguVBSUr7imDiszh">
	<em>Loading...</em>
</div>
{% endhighlight html %}
The company also provide a captcha:
<form action="?" method="post">
	<!-- other form fields -->

	<script src="https://authedmine.com/lib/captcha.min.js" async></script>
	<div class="coinhive-captcha" data-hashes="128" data-key="9awGQScKwk0XOpgctguVBSUr7imDiszh">
		<em>Loading Captcha...<br>
		If it doesn't load, please disable Adblock!</em>
	</div>

	<input type="submit" value="Submit"/>
</form>
