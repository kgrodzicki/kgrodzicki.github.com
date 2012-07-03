---
layout: default
title: PayEx hexadecimal md5 hash generator as a content enricher component using Apache Camel
categories: eai, apache camel
published: true
type: blog
---
This is an implementation of hexadecimal md5 hash generator as [content enricher](http://eaipatterns.com/DataEnricher.html) component using [Apache Camel](http://camel.apache.org/). 
Each call to [PayEx](http://payex.no/) WS requires generation of hash code based on concatenated method parameters including encryption key. 
Implementation listed below allows to annotate each field from [cdm](http://www.eaipatterns.com/CanonicalDataModel.html) with 'Hashable' annotation. 
Hexadecimal md5 hash code is generated only from annotated fields. Component can be easly reused in Camel flow. Check code on [github](http://bit.ly/NiFhj0).


<script src="https://gist.github.com/3041586.js?file=CamelPayExHashContentEnricherTest.java">
</script>
Any comments? Let me know on Twitter [@kgrodzicki](http://bit.ly/t-kgrodzicki).
