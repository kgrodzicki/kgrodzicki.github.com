---
layout: default
title: Bean validation using Apache Camel
categories: eai
published: true
type: blog
---
This is a sample implementation of bean validation using [Apache Camel](http://camel.apache.org/) with [bean validation](http://camel.apache.org/bean-validation.html) component. There are two test methods. First 
with validation passes and `message` is send to `out queue`. Second method tests that validation fails and `message` is send to [dead letter queue](http://www.eaipatterns.com/DeadLetterChannel.html). 
Check code on [github](http://bit.ly/LjGgD7).

<img src ="/img/validation.jpg" alt="Validation" align="center" width="500" height="200" title="Architecture" class="img"/>
<script src="https://gist.github.com/2968376.js?file=CamelValidationTest.java">
</script>
Any comments? Let me know on Twitter [@kgrodzicki](http://bit.ly/t-kgrodzicki).
