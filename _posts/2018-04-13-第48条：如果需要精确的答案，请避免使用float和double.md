---
layout: post
title:  "第48条：如果需要精确的答案，请避免使用float和double"
date:   2018-04-13 15:48:15 +0800
categories: Java
tag: Java
---


浮点数float和double的计算结果不太准确，甚至无法精准计算10的任何负数次方。如果想计算精准值，需要使用BigDecimal、int或者long来计算。但如果数值超过18位数字就必须使用BigDecimal。