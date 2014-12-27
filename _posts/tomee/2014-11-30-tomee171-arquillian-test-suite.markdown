---
layout: post
title:  "Arquilian test suite extension doesn't work with tomee 1.7.1"
date:   2014-11-30 11:17:07
categories: java-ee java-ee6 testing tomee arquilian 
---

[Arquillian] [arquillian] lacks test suites but a very nice [Arquillian test suite custom extension] [arquillian-test-suite] exists.  Apart from offering Junit's @Suite functionality, it's  real advantage is that makes tests run faster, by allowing multiple Shrinkwrap deployments to be deployed at once. Without this every Arquillian test class run, needs a separate archive deployment, start and stop of the  managed or remote container. This worked very well for me, with Jboss 7.1 and Wildfly. Unfortunately due to some bug in Tomee's Arquilian adapter this doesn't work with Tomee 1.7.1 and is expected to be fixed at version 1.7.2.

The [original discussion] [ref-1] of the bug become a [Tomee issue] [ref-2]. A workaround, or alternative strategy if you prefer, specific to Tomee 1.7.x is presented [here] [ref-3].


[arquillian]:	http://arquillian.org/
[arquillian-test-suite]: https://github.com/ingwarsw/arquillian-suite-extension
[ref-1]: https://github.com/ingwarsw/arquillian-suite-extension/issues/14
[ref-2]: https://issues.apache.org/jira/browse/TOMEE-1349
[ref-3]: http://rmannibucau.wordpress.com/2014/09/30/arquillian-tomee-and-big-applications-avoid-n-times-the-same-dump/