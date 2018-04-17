---
layout: post
title:  "第74条：谨慎地实现Serializable接口"
date:   2018-04-17 12:23:10 +0800
categories: effective-java
tag: Java
---


实现Serializable接口的缺点：
1. 一旦一个类被发布，就大大降低了“改变这个类的实现”的灵活性。
2. 增加了出现Bug和安全漏洞的可能性。
3. 随着类发行新的版本，相关的测试负担也增加了。