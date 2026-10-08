# Cloud Security on Azure

Designing a secure, compliant cloud architecture for a fictional mobility company, plus hands-on Linux and Docker performance testing. Part of the SKY2100 Cloud Security exam at Kristiania. Graded **A**.

## Overview

The case study was NordicRide, a scooter and bike sharing platform operating across several Nordic cities, handling real-time location tracking, payments, and user profiles. The task was to design the cloud foundation, address data protection and compliance for international expansion, and back it up with practical testing.

## Part A — Architecture & governance

- **Service model** – PaaS as the backbone for core services (automatic scaling for rush-hour spikes), SaaS for supporting tools, minimal IaaS only where direct control is genuinely needed, justified with the Cloud Security Alliance shared-responsibility model
- **Deployment** – public cloud with multi-region architecture for low latency and resilience
- **Data protection & GDPR** – keeping EU user data in EU regions, data residency and access control across regions, using **Azure Policy, Azure Blueprint and Azure Compliance Manager** to enforce rules and evidence compliance
- **Secure SDLC** – a four-week security training program building security into every stage of development, based on the Microsoft Security Development Lifecycle
- **NIST CSF 2.0** – mapping all six functions (Govern, Identify, Protect, Detect, Respond, Recover) to concrete operational practices for the platform

## Part B — Hands-on lab

- Set up Ubuntu on VMware and inspected the system (`lscpu`, `ss -tuln`)
- Ran a **DDoS-style load test** against Nginx with ApacheBench while monitoring CPU with `top`
- Repeated the test with Nginx inside a **Docker container** and compared performance — containers added no noticeable overhead
- Pushed concurrent connections until the server failed, then explained how load balancers and auto-scaling would handle that load in production

## Lab screenshots

System inspection — `lscpu` and open ports with `ss -tuln`:

![lscpu output](screenshots/01-lscpu.png)
![Open ports](screenshots/02-open-ports.png)

Load testing Nginx with ApacheBench, native vs inside a Docker container:

![Nginx benchmark](screenshots/03-nginx-benchmark.png)
![Docker benchmark](screenshots/04-docker-benchmark.png)

Pushing concurrent connections — 1000 completes, 2300 fails after 28,864 requests:

![Load test 1000](screenshots/05-loadtest-1000.png)
![Load test 2300 fails](screenshots/06-loadtest-2300-fail.png)

Azure training modules completed during the course:

![Azure training](screenshots/07-azure-training.png)

## Tools & concepts

Microsoft Azure (Policy, Blueprint, Compliance Manager) · NIST CSF 2.0 · GDPR · Cloud Security Alliance · Ubuntu / Linux · Docker · Nginx · ApacheBench · Microsoft SDL

## What I took from it

This is the project that pointed me toward cloud security as a career. Designing for scale, compliance, and failure at the same time, then proving part of it in a lab, is exactly the kind of work I want to do.
