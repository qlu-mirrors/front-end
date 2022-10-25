---
category: help
layout: help
mirrorid: gentoo-portage
---

## [Gentoo Linux](https://www.gentoo.org/) 的镜像配置方法如下：

### Gentoo Portage 镜像配置：

#### `rsync` 方式

修改 `/etc/portage/repos.conf/gentoo.conf` ,将

```
sync-uri = rsync://rsync.gentoo.org/gentoo-portage
```

修改为

```
sync-uri = rsync://{{ site.hostname }}/gentoo-portage
```

#### `git` 方式

第一次使用 `git` 同步方式的用户需要进行如下操作：

- 修改 `/etc/portage/repos.conf/gentoo.conf`
		- 将 `sync-type` 改为 `git`
		- 将 `sync-uri` 改为 `https://{{ site.hostname }}/git/gentoo-portage.git`
- 删除 `/var/db/repos/gentoo`
- 执行 `emerge --sync`

已经配置 `git` 同步的用户只需：

- 修改 `/etc/portage/repos.conf/gentoo.conf`
		- 将 `sync-uri` 改为 `https://{{ site.hostname }}/git/gentoo-portage.git`
- 于 `/var/db/repos/gentoo` 下，执行 `git remote set-url origin https://{{ site.hostname }}/git/gentoo-portage.git`
- 执行 `emerge --sync`

### Distfiles 配置：

在 `/etc/portage/make.conf` 中加入：

```
GENTOO_MIRRORS="https://{{ site.hostname }}/gentoo"
```

配置好以上两项后,执行 `emerge --sync` 进行更新。

### Gentoo Prefix Bootstrap 镜像配置：

在运行 Bootstrap 脚本之前，可通过设置以下环境变量选择 Bootstrap 过程中使用的镜像。

```
export GENTOO_MIRRORS="http://{{ site.hostname }}/gentoo"
export GNU_URL="http://{{ site.hostname }}/gnu"
export SNAPSHOT_URL="http://{{ site.hostname }}/gentoo/snapshots"
```

Bootstrap 成功后，若对 Gentoo Portage 和 Distfiles 换源，可参照以上几节，只需将 `/etc` 换成 `$EPREFIX/etc`
