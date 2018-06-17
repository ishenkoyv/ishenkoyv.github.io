---
layout: post
title: "Continuous Deployment and Feature Toggles"
date: 2014-10-30 21:23:26 +0200
comments: true
categories:
- Continuous Delivery
mathjax: true
---

## Continuous Delivery vs Continuous Deployment


  Continuous Delivery includes automatic tests, code quality and errors checks. When all stages are passed code is released to production accorgin to business requirements. So business dictates when a build is deployed. 


  __Drawbacks of continuous delivery approach__:

  *  scheduled downtimes
  *  during "silence period" of no release we can cumulate a lot of changes which will be hard to release. This increase release time and possibility of random bugs on production
  *  all changes appear to all customers immidiately and if some bug exists we will get storm of calls and emails and a very little time to rollback changes/make hotfix


  During release process you have to configure all new futures correctly and sometimes configuration error is catched too late.
  

  Imagegine we found some problem with released code. So what can cause it as all changes were tested and pass all delivery stages including automatical and manual testing?
  

  Here some __examples of questions that can arise__:

  *  Is bug in one of numerous check-ins?
  *  Missing unit tests?
  *  Missing automated UA tests?
  *  Missing manual UA tests?
  *  Data out of sync?
  *  Server configuration out of sync?
  *  Capacity vs current load?
  *  Deployment script?

  <!--more-->

  __Continuous Deployment difference to Continuous delivery__

  *  every passing build is deployd to production (e.g. +30 deploys per day)
  *  constantly integrating into production
  *  all enhancements are gated by Config Flags ("dark" releases). Turning flags on, off, user list, 0-100% 
  *  validate in production, hidden from public 

  Software Deploy ≠ Product Launch
  
## Levels of code delivery and releases


  __CD 100-200 LEVELS__

  *  CI environment for automated tests
  *  Commiting to trunk
  *  Branching in code
  *  Config flags (a.k.a feature flags)
  *  Metrics and alerting
  *  Automatic deploy script


  __CD 300 LEVEL__

  *  Deploys vs releases
  *  Decoupled systems, schema changes
  *  Integration and Operations


## Dark Launching

Term dark launching was coined by Facebook engineering team to simulate the new features in production environment well before release.


>  The secret for going from zero to seventy million users overnight is to avoid doing it all in one fell swoop. We chose to simulate the impact of many real users hitting many machines by means of a “dark launch” period in which Facebook pages would make connections to the chat servers, query for presence information and simulate message sends without a single UI element drawn on the page. With the “dark launch” bugs fixed, we hope that you enjoy Facebook Chat now that the UI lights have been turned on.


## Feature Toggles


__Feature toggles are used for dark Launching or phased rollout__. Once latest version of application deployed we can toggle and expose a set of features to selected or all end-users.
 

__Feature toggles can be also used for__,

  *  for avoiding branching and merging  
  *  experimenting such as A/B tests
  *  putting unfinished code in production
  *  reducing risk associated with large change
  *  turning a resources heavy feature OFF in high load conditions

According to Ross Harmes @ Flickr

> Feature flags and flippers mean we don’t have to do merges, and that all code (no matter how far it is from being released) is integrated as soon as it is committed. Deploys become smaller and more frequent; this leads to bugs that are easier to fix, since we can catch them earlier and the amount of changed code is minimized.

Martin Fowler’s explanation of feature toggle,

> The basic idea is to have a configuration file that defines a bunch of toggles for various features you have pending. The running application then uses these toggles in order to decide whether or not to show the new feature.


__Feature toggles in PHP__

  *  [Qandidate toggle](https://github.com/qandidate-labs/qandidate-toggle)
  *  [FeatureToggle (Symfony)](http://github.com/marekkalnik/FeatureToggleBundle)

__Feature toggles in Ruby__

  *  [Flip](http://github.com/pda/flip)
  *  [Rollout](http://github.com/jamesgolick/rollout)
  *  [Degrade](http://github.com/jamesgolick/degrade)

__Feature toggles in Python__

  *  [Gargoyle (Django)](http://github.com/disqus/gargoyle)
  *  [Django Waffle (Django)](http://github.com/jsocol/django-waffle)
  *  [Nexus admin](https://github.com/disqus/nexus)
