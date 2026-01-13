---
layout: post.njk
title: Art and science of manging "Data as a Product" in modern distributed SAP world 
date: 2026-01-12
description: Introduction to Data Products
tags:
  - blog
  - SAP Data Products
  - Data Mesh 
  - SAP BDC
---

In the modern digital enterprise, data is no longer simply a byproduct of operations - it's a core business asset that drives innovation, decisions, and customer experience. Yet, the challenge lies not in generating data, but in managing it effectively.

## Two Worlds of Data: Operational and Analytical
Most enterprise landscapes are split into two planes of data.

* The operational data plane is transactional and stateful. It powers business applications and captures what is happening right now - for example, a sales order being created in SAP S/4HANA.​
* The analytical data plane is temporal and aggregated. It looks across history to support reporting, forecasting, and advanced analytics

In SAP-centric environments, data is typically replicated from the operational plane into the analytical plane using technologies such as SAP Landscape Transformation (SLT) or Smart Data Integration (SDI). Over time, this analytical side has evolved into two distinct archetypes:​
* Data warehouse: structured, governed models for BI and reporting.​
* Data lake: flexible storage for raw and semi-structured data, often consumed by data science and machine   learning workloads


#### ETL:

{% image "src/assets/images/ETL-PROCESS.png", "ETL process", "100vw" %}

## The Old World: Monolithic Architectures and Emerging Pain Points


As data use cases multiplied and sources diversified, monolithic architectures such as SAP Business Warehouse began to show cracks. The centralized approach created bottlenecks:
* High cost of discovering and trusting quality data.
* Performance issues from concentrating vast amounts of data in a single system.
* Organizational barriers between domain experts who produce the data and teams who consume it.

In essence, while businesses grew more data-driven, their data architectures failed to scale with agility.

## The Paradigm Shift: Enter Data Mesh

A fresh way of thinking emerged in 2019 when zhamak dehghani introduced the concept of the Data Mesh. It proposed three revolutionary principles:
* Decentralized data ownership and architecture.
* Treating data as a product.
* Self-serve data infrastructure as a platform.

Instead of one central team governing all enterprise data, Data Mesh empowers domain teams to own, design, and deliver data products - high-quality data sets that others can easily discover and use.

## Data as a Product: Bridging Technology and Mindset

At the heart of Data Mesh lies the philosophy of Data as a Product (DaaP).
This approach borrows from traditional product design principles:
clear ownership and accountibility 
Focus on consumer expirience 

Under this principle, a data product is a well-defined, discoverable, and governed data asset, exposed through stable contracts such as APIs or events, and described with rich metadata. It is not just a table; it is a complete package


## What Is a Data Product?
A data product can be thought of as a node in the data mesh: it takes one or more inputs, applies transformations, and serves outputs tailored to consumer needs. In practice, a robust data product typically spans five aspects:

 {% image "src/assets/images/Dataproduct.png", "Data Product", "100vw" %}


1. Data aspect
- The core dataset: business objects (e.g., sales orders, material master), facts, or analytical aggregates.
- Exposed in a read-only, consistent, and stable shape designed for sharing.

2. API & event aspect
- How consumers access the data: REST APIs, OData, SQL endpoints, events, or open-sharing protocols such as Delta Sharing in modern data fabrics.​
- Interoperable schemas that allow integration with tools across the landscape.​

3. Metadata aspect
- Human- and machine-readable descriptions: purpose, schema, lineage, quality indicators, and dependencies.​
- Stored and searchable in a data catalog or product dictionary so others can easily discover and evaluate the product.​

4. Product aspect
- managed with a product mindset: defined owner, roadmap, and lifecycle from creation to deprecation.​
- Quality, documentation, and user feedback are treated as first-class concerns, not afterthoughts.​

5. Business semantic aspect
- Links raw technical structures to business meaning via a semantic model (for example, entities, relationships, measures, and hierarchies).​
- Ensures that data consumers across domains interpret concepts like "sales order", "net value", or "material" consistently

SAP systems provide illustration of these concepts. In SAP S/4HANA, business objects are exposed through ABAP Core Data Services (CDS) views, which form a Virtual Data Model (VDM) over underlying tables.​

 {% image "src/assets/images/I-SalesOrder.png", "sales order Product", "100vw" %}


For instance, the Sales Order object is represented by various CDS views (such as I_SalesOrder and its related entities) that harmonize data from multiple database tables into semantically rich views. These views:​
- Provide a stable, documented schema oriented around business concepts rather than low-level table structures.​
- Can serve as the data backbone for downstream products in platforms like SAP Datasphere, which then package them with additional metadata, governance, and sharing capabilities.​
From a Data Mesh perspective, a curated Sales Order view enriched with metadata and exposed through a catalog is an excellent example of a data product.

{% image "src/assets/images/BDCData.png", "BDC data", "100vw" %}

## The Promise: Why Data Products Matter
Adopting data products transforms the way organizations derive value from their data:
- Discoverability - Consumers can easily find and - understand datasets through metadata-driven catalogs.
- Trust and Quality - Clear ownership ensures accountability and data integrity.
- Agility - Domain teams can independently publish and evolve data without central bottlenecks.
- Interoperability - Standardized APIs and schemas enable consistent reuse across platforms.
- Faster Insights - Data flows more efficiently to analytics, AI, and business applications.

In essence, Data as a Product turns fragmented data into valuable assets - usable, reliable, and meaningful - fueling innovation across both operational and analytical domains

## 

---
