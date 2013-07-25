---
layout: default
title: Content Enricher implementation using Oracle Service Bus
categories: eai soa
published: true
type: blog
---
This is a sample implementation of a [Content Enricher pattern](http://www.eaipatterns.com/DataEnricher.html) in Oracle Service Bus.

## Architecture
<img src ="/img/content-enricher-ID.png" alt="Content Enricher" align="center" width="500" height="300" title="Content Enricher" class="img"/>

## How to run:
You can just import [export jar](https://github.com/kgrodzicki/faggruppe-instegrasjon-soa/tree/master/patterns/content-enricher/implementation/osb) into your local OSB installation
or if you don't have one install prepared [Virtual Box with Oracle WebLogic Server and OSB hosted on Ubuntu 12.04 using Vagrant and Puppet](https://github.com/kgrodzicki/vagrant-ubuntu-osb). 

## Import projects to OSB:
Log in to [http://localhost:7001/sbconsole](http://localhost:7001/sbconsole)  user: weblogic and password: weblogic1
Create session clicking on Create button on left panel.
Go to System Administration > Import Resources > Choose [contentEnricher.jar](https://github.com/kgrodzicki/faggruppe-instegrasjon-soa/blob/master/patterns/content-enricher/implementation/osb/contentEnricher.jar) 
from your local file system > import.
Activate session clicking on Activate button on left panel.

## Test project with soapUI:
From root project directory of Vagrant configuration login with ssh and forward the port 8088 from host to guest machine.
OSB will be able to access mock services running in host soapUI installation.
<script src="https://gist.github.com/kgrodzicki/6070117.js">
</script>
Run the server according to instructions [here](https://github.com/kgrodzicki/vagrant-ubuntu-osb/blob/master/README.md).
Run soapUI tests [POC-DataEnricher-DataEnricherLetterService-soapui-project.xml](https://github.com/kgrodzicki/faggruppe-instegrasjon-soa/tree/master/patterns/content-enricher/soapui) 
from your local machine. LetterServiceSoapBinding MockService has to be up and running during tests.

Any comments? Let me know on Twitter [@kgrodzicki](http://bit.ly/t-kgrodzicki).
