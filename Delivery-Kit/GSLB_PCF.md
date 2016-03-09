---
title: GSLB & PCF
layout: post
authors: Merlin Glynn, John Yi, Jason Sherron, John Calabrese
permalink: 
source-id: 
published: false
---

<p align="center">
<img src="images/Pivotal-logo.png">
<br>
Global Server Load Balancing (GSLB) PCF
<br>
 **THIS IS A DRAFT !!!**
</p>

# Overview

This document describes 4 solutions on how to deploy multiple instances (or foundations) of PCF and load balance between them with various public and private on premesis GSLB methods.  This Delivery Kit is broken into the following sections

* Solution Logical Architecture
* Planning & Pre-Requisites
* Solution Deployment

This document will focus on the client facing or "North/South" traffic management points for an application to be published in multiple foundations.  It is beyond the scope of this Delivery Kit to cover topics such as distributed Application or Data architecture.  This topics will be covered in another Customer0 Delivery Kit.

It is assumed that readers of this document are familiar with administration of the following Platforms/Technologies:

* Pivotal Cloud Foundry 1.6/1.7
* DNS
* GSLB Platform: AWS, Azure, Dyn, F5

# Solution Logical Architecture
The main goal of a GSLB & PCF architecture is to provide optimized traffic distribution across PCF foundations deployed in multiple DataCenters or Geographies.  

<p align="center">
<img src="images/Overview.png">
<br>
</p>

A common approach to achieving GSLB is via intelligent DNS resolution and is the core approach that will be covered in each example deployment.

**Warning**: Applications designed for peer communication or requiring access to geographically replicated data services will incur design and operational difficulty when PCF Foundations are separated by highly latent & geographically dispersed networks.

# Planning & Pre-Requisites
Planning for PCF to host an application across foundations requires some basic planning and setup...

**1**: Application routed namespace/domain(s)

In the examples covered in this delivery kit,  all applications will be mapped to a _*.customer0.net_ route.   This route will exist as part of a "shared-domain" in both of our example PCF foundations.

example: _customer0.net_

**2**: PCF System & App domains

Each foundation will still require its own resolvable url space for system access (_api, apps, login, uaa, etc_...) as well as local routed domains that are specific to each foundation for local only route mapps (_*.site-a.pcflab.net_).  This is so that traffic may be routed direct to a foundation regardless of the GSLB state, as well as for admin/pipeline access to actually push apps via the Cloud Foundry api.  These are the same domains that PCF Operations Manager describes as _System_ & _Apps_ Domains.

example:

| Site          | Function             | Domain                     |
| ------------- |:--------------------:| --------------------------:|
| site a        | system		         | _sys.site-a.pcflab.net_    |
| site a        | apps (shared domain) | _cfapps.site-a.pcflab.net_ |
| site b        | system		         | _sys.site-b.pcflab.net_    |
| site b        | apps (shared domain) | _cfapps.site-b.pcflab.net_ |

**3**: DNS

The DNS delegation for the chosen Application Domains must 

**4**: SSL

SANs

   

### GSLB Provider Requirements
* Amazon Route 53
* Azure Traffic Manager
* Dyn
* F5 (On Prem)

# Solution Deployment 
## GSLB PCF w/ AWS Route 53
### Steps

Details

## GSLB PCF w/ Azure Traffic Manager
### Steps

Details

## GSLB PCF w/ AWS Dyn Managed DNS Traffic Management
### Steps

Details

## GSLB PCF w/ F5
### Steps

Details
