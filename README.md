# Cara Saven AI Wallpaper Visualiser

A production AI-powered visualisation tool developed by **[LekkerAI](https://lekkerai.dev/)** for **Cara Saven Wall Design**. LekkerAI is a startup founded by **Abdul-Qadir and Zach**. The Visualiser helps customers preview a selected wallpaper design in a photo of their own room before moving into the enquiry and quote process.

**Try the live Visualiser:** [Open the Meander wallpaper on Cara Saven](https://carasaven.com/graphic-geometric/meander/) and select **“Visualise This Design”**.

> **Meander is simply an example.** The Visualiser is integrated across Cara Saven’s wallpaper catalogue, so customers can open a wallpaper design on the Cara Saven website and launch **“Visualise This Design”** from that product page.

> This repository is a **sanitised public showcase**. The production source code remains private because this is a live client application containing client-specific implementation details, infrastructure and proprietary logic.

## The problem

Choosing wallpaper online is difficult because customers have to imagine how a design will look in their own space. Static product images do not give enough context around room layout, lighting, furniture and scale.

The Visualiser was built to reduce that uncertainty by turning a customer's own room photo into a more useful pre-purchase visual experience.

## What the product does

1. A customer selects a wallpaper design on the Cara Saven website.
2. They select **“Visualise This Design”** and upload a photo of their room.
3. The application processes the room and design through an AI-assisted image-editing workflow.
4. The result aims to preserve the original room while applying the selected wallpaper to the relevant wall surfaces.
5. The customer can review the visualisation and continue into the enquiry / quote journey.

## Product flow

![Cara Saven Visualiser product flow](assets/visualiser-flow.jpg)

*Sanitised overview of the live customer journey: Cara Saven product page → upload a wall photo → AI visualisation result → enquiry handoff.*

## Technical overview

The production application combines:

- **React + TypeScript** frontend
- **Vite** application tooling
- **Tailwind CSS + shadcn/ui** interface components
- **Cloud database and serverless backend functions**
- **AI image-editing workflow** for room visualisation
- **Product catalogue integration**
- **Customer enquiry workflow**
- Request validation, fallback handling and usage controls

## Selected implementation details

The production code is private, but the following gives a more concrete view of the engineering work behind the live application without exposing proprietary implementation details.

### Product-to-Visualiser handoff

The Visualiser is designed to start from the customer's selected wallpaper rather than as a disconnected image tool. Product context is carried from the Cara Saven product journey into the Visualiser so the customer arrives with the relevant design already selected.

### AI image-editing orchestration

The backend accepts the customer's room image and selected wallpaper, validates the request and passes the images through a server-side AI image-editing workflow. The workflow is designed around **editing the customer's existing room**, rather than generating an unrelated replacement scene.

### Reliability and fallback handling

The visualisation flow includes request validation, payload/image-size controls, error handling, usage controls and fallback behaviour so that failures can be handled more predictably in a real customer-facing environment.

### Serverless application layer

Backend responsibilities are separated into serverless functions rather than placing sensitive application logic in the browser. These functions support the visualisation workflow, product-data handoff, image handling and enquiry process while keeping private credentials server-side.

### Business workflow integration

The generated visualisation is not the end of the journey. The application connects the result to the client's enquiry / quote process, allowing the AI experience to support an actual commercial customer flow rather than operating as a standalone demo.

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

## About LekkerAI

**[LekkerAI](https://lekkerai.dev/)** is a startup founded by **Abdul-Qadir and Zach**. The Cara Saven Visualiser was developed through LekkerAI as a real client product, from concept and product scoping through to implementation, deployment and ongoing iteration.

## My contribution

I co-developed the product through **LekkerAI**, from concept through to a working production application. My involvement included:

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

The live experience linked above is the best way to evaluate the finished product in its intended customer journey. The technical sections in this showcase are intended to demonstrate the scope and engineering decisions behind the product without publishing material that should remain private.

---

**Developed by:** [LekkerAI](https://lekkerai.dev/) — founded by Abdul-Qadir and Zach  
**Project type:** Production client application  
**Status:** Live  
**Role:** Co-development, product and implementation
