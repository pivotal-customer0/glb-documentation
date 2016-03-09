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

# Solution Logical Architecture
The main goals of a GSLB & PCF architecture are to provide optimized traffic distribution across PCF foundations deployed in multiple DataCenters or Geographies.   

<p align="center">
<img src="images/Overview.png">
<br>
</p>

Warning: Applications designed for peer communication or requiring access to geographically replicated data services will incur design and operational difficulty when PCF Foundations are separated by highly latent & geographically dispersed networks.

# Planning & Pre-Requisites
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
