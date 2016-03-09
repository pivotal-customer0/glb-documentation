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
* GSLB PLatform: AWS, Azure, Dyn, F5

# Solution Logical Architecture
The main goal of a GSLB & PCF architecture is to provide optimized traffic distribution across PCF foundations deployed in multiple DataCenters or Geographies.   

<p align="center">
<img src="images/Overview.png">
<br>
</p>

**Warning**: Applications designed for peer communication or requiring access to geographically replicated data services will incur design and operational difficulty when PCF Foundations are separated by highly latent & geographically dispersed networks.

# Planning & Pre-Requisites
Planning for PCF to host an application across foundations requires seom basic planning and setup...

**1**: What is the application routed namespace?

In the examples covered in this delivery kit,  all applications will be mapped to a _*.customer0.net_ route.   This route will exist as part of a "shared-domain" in both of our example PCF foundations.

**2**: Who owns the DNS?

**3**: SSL, SANs, & SNI ...

   

## Solution Requirements
### PCF
### SSL
### DNS
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
