---
layout: default
title: Continuous integeration and deployment with CloudBees
categories: cloudBees
published: true
type: blog
---
Recently in company and private projects I started using [CloudBees](http://www.cloudbees.com/) as cloud deployment platform.
It is really straightforward to set up continous integration(CI)[^ci] and continous deployment[^cd] using:

* __DEV@cloud__ - provides Jenkins, maven repositories, SVN and Git repositories, more details here: [http://www.cloudbees.com/dev.cb](http://www.cloudbees.com/dev.cb).
* __RUN@Cloud__ - brings application server functionality to the cloud. Allows to deploy web, Java EE and Spring applications.

Platform configuration is easy and well documented. Many screencasts allow to get started very fast.

To try out CloudBees provides a free subscription for all of its core platform services.
Check out sample [grails application](https://github.com/kgrodzicki/flashcards-grails/) which use GitHub ``Service Hooks`` to produce build events for Jenkins on DEV@cloud.

[^ci]: [http://en.wikipedia.org/wiki/Continuous_integration](http://en.wikipedia.org/wiki/Continuous_integration)

[^cd]: [http://timothyfitz.wordpress.com/2009/02/10/continuous-deployment-at-imvu-doing-the-impossible-fifty-times-a-day/](http://timothyfitz.wordpress.com/2009/02/10/continuous-deployment-at-imvu-doing-the-impossible-fifty-times-a-day/)
