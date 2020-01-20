---
layout: post
title: "Version naming convention (version numbering)"
date: 2014-11-02 22:01:11 +0200
comments: true
categories:
- Development
tags:
- Development Conventions
---

* content
{:toc}


According to development methodology you use periodicaly code changes are delivered to production and you make release.
Release is point in time which you have to freeze for history. With git you can add tag for this, e.g.


```
git tag -a v0.0.1 -m "Release v0.0.1"
git push origin v0.0.1
```

What do all this digits mean?


## Version naming convention 
I use [semantic versioning](http://semver.org/). This approach is popular ([google](https://developers.google.com/java-dev-tools/wintester/html/installation/version_naming_convention), [eclipse](https://wiki.eclipse.org/Version_Numbering) etc.) and http://semver.org/.
So version number contains 3 segments (versions): major, minor, patch:

```
v0.0.1
^ ^ ^
| | |
| | +--- Patch verion (Minor changes, bugfixes etc)
| +----- Minor version (Added new huge functionality)
+------- Major version (Incompatible API changes)
```

When the major segment is changed the minor and patch segments are reset to 0.
When the minor segment is changed the patch segment is reset to 0.

So your releases list will look something like that

```
git tag -l
v0.0.1
v0.0.2
v0.0.3
v0.1.0
v0.1.1
v1.0.0
```


## Upgrading the software version on applying a hotfix
We leave in not an ideal world and sometimes event if your changes are good tested critical bugs appear on production. Such sort of critical bugs should be fixed as fast as possible, so you don't have time to go through all development cycle stages. But this is not a reason to make manual changes on production.

If you made appropriate changes to fix bug and commited changes to git (and to production) you should reflect this moment in versions history, i.e. add tag.
To indicate hotfixes in version name I use patch segment alphabetic suffix

```
v0.0.1a
```
