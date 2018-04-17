---
layout: post
title:  "第68条：executor和task优先于线程"
date:   2018-04-16 20:12:53 +0800
categories: effective-java
tag: Java
---


使用java.util.concurrent.Executors类来开发线程池。同时使用ScheduledThreadPoolExecutor来代替timer。具体同步见《Java Concurrency in Practice》