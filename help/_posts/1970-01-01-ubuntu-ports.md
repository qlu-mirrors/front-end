---
category: help
layout: help
mirrorid: ubuntu-ports
---

Ubuntu Ports 镜像使用帮助
===================

Ubuntu 的软件源配置文件是
`/etc/apt/sources.list`。将系统自带的该文件做个备份，将该文件替换为下面内容，即可使用
TUNA 的软件源镜像。


<form class="form-inline">
<div class="form-group">
	<label>选择你的ubuntu版本: </label>
	<select class="form-control release-select" data-template="#apt-template" data-target="#apt-content">
		<option data-release="trusty">14.04 LTS</option>
		<option data-release="xenial">16.04 LTS</option>
		<option data-release="bionic">18.04 LTS</option>
		<option data-release="focal">20.04 LTS</option>
		<option data-release="impish">21.10</option>
		<option data-release="jammy" selected>22.04 LTS</option>
	</select>
</div>
</form>

{% raw %}
<script id="apt-template" type="x-tmpl-markup">
# 默认注释了源码镜像以提高 apt update 速度，如有需要可自行取消注释
deb https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}} main restricted universe multiverse
# deb-src https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}} main restricted universe multiverse
deb https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}}-updates main restricted universe multiverse
# deb-src https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}}-updates main restricted universe multiverse
deb https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}}-backports main restricted universe multiverse
# deb-src https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}}-backports main restricted universe multiverse
deb https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}}-security main restricted universe multiverse
# deb-src https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}}-security main restricted universe multiverse

# 预发布软件源，不建议启用
# deb https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}}-proposed main restricted universe multiverse
# deb-src https://{%endraw%}{{ site.hostname }}{%raw%}/ubuntu-ports/ {{release_name}}-proposed main restricted universe multiverse
</script>
{% endraw %}

<p></p>

<pre>
<code id="apt-content">
</code>
</pre>

本镜像仅包含 arm64 armhf ppc64el riscv64 s390x 架构的软件包。
