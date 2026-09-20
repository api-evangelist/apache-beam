---
title: "UnboundedSource and the Watch Transform in the Apache Beam Python SDK"
url: "/blog/python-unboundedsource-watch/"
date: "2026-09-10"
feed_url: "https://beam.apache.org/feed.xml"
---
The Apache Beam Python SDK now has an UnboundedSource API for writing custom unbounded sources and a Watch transform for repeatedly polling an input that keeps growing. I built both during my Google Summer of Code 2026 project with Apache Beam, mentored by Yi Hu. This post describes both APIs as of Beam 2.77.0.
