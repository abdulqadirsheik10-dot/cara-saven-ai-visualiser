# Cara Saven AI Wallpaper Visualiser

A production AI-powered visualisation tool developed for **Cara Saven Wall Design**. It helps customers preview a selected wallpaper design in a photo of their own room before moving into the enquiry and quote process.

**Try the live Visualiser:** [Open the Meander wallpaper on Cara Saven](https://carasaven.com/graphic-geometric/meander/) and select **“Visualise This Design”**.

> This repository is a **sanitized public showcase**. The production source code remains private to protect client-specific implementation details, infrastructure, credentials and proprietary logic.

## The problem

Choosing wallpaper online is difficult because customers have to imagine how a design will look in their own space. Static product images do not give enough context around room layout, lighting, furniture and scale.

The Visualiser was built to reduce that uncertainty by turning a customer's own room photo into a more useful pre-purchase visual experience.

## What the product does

1. A customer selects a wallpaper design on the Cara Saven website.
2. They select **“Visualise This Design”** and upload a photo of their room.
3. The application processes the room and design through an AI-assisted image-editing workflow.
4. The result aims to preserve the original room while applying the selected wallpaper to the relevant wall surfaces.
5. The customer can review the visualisation and continue into the enquiry / quote journey.

## Technical overview

The production application combines:

- **React + TypeScript** frontend
- **Vite** application tooling
- **Tailwind CSS + shadcn/ui** interface components
- **Cloud database and serverless backend functions**
- **AI image-editing workflow** for room visualisation
- **Product catalogue integration**
- **Customer enquiry workflow**
- Request validation, fallback handling and basic usage controls

## High-level architecture

```text
Customer
   |
   v
Cara Saven product page
   |
   v
Visualise This Design
   |
   v
React / TypeScript web application
   |
   v
Serverless application layer
   |-------------------------------|
   |               |               |
   v               v               v
AI visualisation   Product data    Enquiry workflow
workflow           integration
   |
   v
Visualisation result
```

## Technical challenges solved

### Preserving the customer's room

The core challenge is not simply generating an attractive room image. The useful result needs to stay recognisable as the customer's original space while changing the wall treatment. The production workflow was iterated around that constraint rather than treating the task as generic image generation.

### Handling real customer uploads

The application has to work with user-provided images rather than controlled demo assets. The production system therefore includes input validation, image-size handling, error states and fallback behaviour around the visualisation workflow.

### Connecting the visualisation to a real business journey

The product is not a standalone AI demo. It connects the visualisation experience to the client's existing product catalogue and enquiry process so that the generated result can support an actual customer decision.

## My contribution

I co-developed the product from concept through to a working production application. My involvement included:

- Product scoping and feature decisions
- User-flow and experience design
- Implementation and integration work
- AI workflow integration and iteration
- Testing and debugging
- Deployment and ongoing product refinement with the client

## Why the production repository is private

This is a real client application, not an open-source demo. The production repository contains client-specific logic and infrastructure that should not be published publicly.

For that reason, this showcase intentionally does **not** include:

- Production credentials or environment configuration
- Private backend or infrastructure details
- Internal AI prompts or model configuration
- Client/customer data
- Proprietary integration logic
- Production source code

The live experience linked above is the best way to evaluate the finished product in its intended customer journey, while this repository provides enough technical context to understand the scope of the work without exposing information that should remain private.

---

**Project type:** Production client application  
**Status:** Live  
**Role:** Co-development, product and implementation
