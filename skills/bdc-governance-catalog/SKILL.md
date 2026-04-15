---
name: bdc-governance-catalog
description: Use when the user is working with the SAP BDC catalog — enriching metadata, classifying data, publishing assets to the catalog, managing business glossaries/KPIs, controlling tags, analyzing impact/lineage, or asking what's new in BDC governance. Trigger phrases include "BDC catalog", "BDC metadata", "BDC data classification", "BDC asset publishing", "BDC glossary", "BDC KPI", "BDC lineage", "BDC impact analysis", "BDC what's new", "BDC governance".
---

# SAP BDC Governance & Catalog

## Catalog Overview & Strategy

The catalog is the central place where you discover, classify, profile, understand, and prepare all data in your enterprise. Users with the **Catalog Administrator** role are responsible for connecting source systems to the catalog, monitoring those systems, enriching and classifying objects, and publishing them as catalog assets.

### Why Data Governance Matters

An effective data governance strategy addresses critical challenges:
- Unknown data assets or duplicated efforts across the organization
- Unclear data meaning and intent without consistent documentation
- Stale, unreliable data for current use
- Difficulty controlling consumer access to data

The catalog brings all organizational data together as a one-stop-shop for seamless data discovery and governance, enabling users to map complete data source views, build governance standards, and offer trusted self-service data access.

## Core Roles & Responsibilities

### Catalog Administrator
Responsible for overall setup and data governance implementation:
- **Connect**: Add data source systems to the catalog and extract metadata for data products and assets
- **Classify and Enrich**: Create and apply consistent business terms, descriptions, tags, and other information
- **Publish**: Prepare and make available governed assets to all data users

Data source systems are connected automatically via SAP Business Data Cloud formation or manually via local SAP Datasphere.

### Catalog User
Data modelers and business users who:
- **Discover**: Search, filter, and explore available data items
- **Evaluate**: View metadata, descriptions, impact, and lineage to understand data items
- **Use**: Open assets in source systems, install data product APIs to SAP Datasphere spaces, or use assets in data projects

## Catalog Concepts

### Assets
Any data or analytic object made available in the catalog (e.g., local table or view from SAP Datasphere, story from SAP Analytics Cloud). Assets are the objects you provide governance around and publish for discovery and consumption.

### Data Products
Self-contained sets of data exposed via APIs for consumption outside the producing application. SAP applications like SAP S/4HANA Cloud produce data products consumable in SAP Datasphere via SAP Business Data Cloud data packages. Data products have an active release status, which automatically makes them appear in the catalog.

**Note**: Catalog enrichments for data products (term and tag relationships) are not currently available.

### Domains
Organizational containers for data products in SAP Business Data Cloud that provide a metadata-centric way to organize and govern products by aligning assets, access, and lifecycle responsibilities to organizational units.

### Data Providers & Content Aggregators
Data providers are persons or companies offering data products. They develop, maintain lifecycle, manage versions, licensing agreements, data freshness, and API performance. They may work independently or with content aggregators.

## Asset Publishing Workflow

### Publish to Catalog

**Publishing** is the act of making assets visible and available to catalog users. Unpublished assets are available only to Catalog Administrators. Before publishing, administrators can:
- Edit and enrich metadata
- Apply appropriate classifications
- Ensure overall asset quality

**Publishing actions**:
- **Publish**: Make assets discoverable within the formation where they originated
- **View Data Products**: See data products from source systems in all formations (start with inactive status; become active when intelligent applications are installed or data packages are activated)
- **Share Data Products**: After activation, share data products with other SAP systems or supported external systems (SAP S/4HANA, SAP Databricks, SAP HANA Cloud, SAP Customer Data Platform, SAP SuccessFactors)
- **Exclude from Automatic Publishing**: Prevent specific items from being automatically published
- **Unpublish**: Remove items from catalog view
- **Delete**: Remove items with "Unavailable" functional status

**Publication Statuses**:
- Published (active in catalog)
- Unpublished (visible only to administrators)
- Functional statuses (Current, Unavailable, etc.) indicate asset state

## Classification & Tagging

### Tags Overview
Tags allow you to classify data assets into clear categories. The catalog provides a hierarchical tagging system for organized asset management.

**Classification** is the process of organizing assets into clear categories using tags. Example: Create a "Bike Products" category with hierarchical tags for product types, regions, or business lines.

### Manage Tags
From the **Catalog & Marketplace** menu:
- Create and manage all tags needed to consistently classify assets
- Organize tags hierarchically for clarity
- Apply tags consistently across assets
- Use tags in search and filter operations to help users discover related assets

### Adding Tags to Assets
On the **Semantic Enrichment tab** of the asset details page:
- Select or search for existing tags
- Create new tags as needed
- Delete tag relationships using the delete button per row
- Tags appear in search results, helping users discover related assets

## Business Glossary & Terms

### Glossary Overview
The business glossary provides a central, shared repository for defining business terms and describing how and where they are used. A well-maintained glossary promotes common understanding across the organization, reduces ambiguity, and provides term relationships linking to other terms, KPIs, and assets.

**Example**: Define "Sales" uniquely for your organization (currency exchanged for goods/services vs. discounted pricing) to eliminate confusion.

### Glossary Structure
A business glossary consists of:
- **Glossary Template**: Defines guidelines and required/optional information for term definitions
- **Categories**: Group related terms hierarchically
- **Defined Terms**: Provide business context and clarity

### Creating & Managing Glossaries

**Best Practice**: Create glossaries in the SAP Business Data Cloud cockpit to make them available across all catalog views. Create in local SAP Datasphere only if intended for a single formation.

**Reference Templates**: When creating a glossary, choose a reference template to pull definition and custom attributes from an existing glossary. Changes are unique to the new glossary—not reflected elsewhere.

**Custom Attributes**:
- Define custom attributes for terms (free text, validated with min/max values, or lookup tables)
- Set attributes as required or optional
- Group input fields into separate tabs or sections
- Create labels offering context and guidance for users
- Example: Create a "Quality Assurance" group with Definition Date (required) and Approved (optional) attributes

### Term Lifecycle
1. Subject matter experts create and define terms, create term relationships, place them in categories
2. Publish terms so organization-wide users can view them
3. Business users search the glossary when they have questions about term meanings

### Creating Glossary Categories
- Define category hierarchies to organize terms logically
- Place related terms within appropriate categories

## Key Performance Indicators (KPIs)

### KPI Overview
A Key Performance Indicator measures progress toward a result such as a goal or objective. KPIs provide an analytical basis for decision-making.

- **Goals/Objectives**: Broader organizational targets (qualitative, time-bound)
- **KPIs**: Metrics indicating progress toward goals

### Using KPIs
- Create relationships between KPIs and assets, terms, and other KPIs
- When users search for KPIs, they find all relevant objects
- Monitor KPI status (Current, Needs Repair) for data quality tracking

### KPI Management
From the **Catalog & Marketplace** menu:
- **Create KPIs**: Define new performance indicators with custom attributes and relationships
- **Edit/Delete**: Modify existing KPIs or remove them
- **Manage Templates**: Define the KPI template structure (required/optional fields, custom attributes, groupings)
- **Manage Relationships**: Create and update KPI-to-asset, KPI-to-term, and KPI-to-KPI links

**Privilege Requirements**: 
- **Catalog KPI Object (–R–––-M)**: View published and unpublished KPIs

### Filtering & Searching KPIs
Search results show KPI filters:
- **Status**: Current, Needs Repair
- **IDs & Keywords**: Filter by defined KPI identifiers or keywords
- **Published/Unpublished**: Show or hide unpublished KPIs
- **Edit Date/Create Date**: Filter by date ranges
- **Related Terms**: Find KPIs linked to specific glossary terms
- **Tenant**: Filter by creation tenant (useful in multi-tenant SAP Business Data Cloud scenarios)

### KPI Import
Import glossary terms and KPIs from Microsoft Excel spreadsheets into the catalog:
- **Import Glossary Terms**: Bulk-import business terms
- **Import Key Performance Indicators**: Bulk-import KPI definitions
- View import details and error handling after import

## Metadata Enrichment

### Asset Enrichment Overview
Metadata enrichment improves asset discoverability and usability by adding:
- Descriptions and context
- Glossary term relationships
- Tags for classification
- KPI relationships

Enriched assets help users find and understand data before consuming it.

### Semantic Enrichment Tab
Access the **Semantic Enrichment tab** on asset details pages to:
- **Add Glossary Terms**: Link business glossary terms to assets
- **Add KPIs**: Associate key performance indicators with assets
- **Add Tags**: Apply classification tags

**Preview Sections**: Each section shows up to 20 rows; use "Show All" to view more in a separate page.

### Adding Term Relationships to Assets
1. Go to asset details page
2. Select **Semantic Enrichment tab**
3. Select object type (Terms)
4. Search for and select glossary terms
5. For attribute/measure/dimension-level relationships, select **Semantic Enrichment** within those sections
6. Relationships appear in search results, enabling term-based discovery

### Adding KPI Relationships to Assets
1. Access catalog and open asset details page
2. Go to **Semantic Enrichment tab**
3. Select KPI relationships
4. Search for and add KPIs
5. For attribute/measure/dimension relationships, use the relevant section's Semantic Enrichment options
6. KPI links enable KPI-based asset discovery

### Removing Enrichments
- Use the delete button (—) for each row to remove term, tag, or KPI relationships
- Deletions take effect immediately but do not delete the term/KPI itself—only the asset-to-term/KPI link

### Metadata Extraction Monitoring
Enhanced monitoring ensures catalog reliability:
- **Extraction Error Detection**: Errors detected early and visible in extraction summary logs and asset details pages
- **Auto-Resynchronization**: Source systems with data product or API extraction issues are automatically resynchronized
- **Manual Synchronization**: Manually synchronize source systems to update data products
- **Installation Blocking**: Users cannot install data products with outdated APIs
- **Data Product Statuses**: New granular statuses aligned with the Catalog for detailed monitoring of data product provisioning and lifecycle

## Impact & Lineage Analysis

### Understanding Lineage & Impact
The **Impact and Lineage Analysis diagram** helps you understand data provenance and dependencies:

- **Lineage** (left/below): Shows source objects used by the analyzed object. Enables tracing errors to root causes.
- **Impact** (right/above): Shows objects using the analyzed object as a source. Enables understanding change impact on dependent objects.

### Viewing Lineage & Impact
- Click **Open Impact and Lineage** button in the asset or data product header
- Dialog displays an interactive diagram showing:
  - Object-level data analysis
  - End-to-end visualization of object dependencies across multiple systems and layers
  - Source data, transformations, final state, and dependent objects
  - Publication and functional statuses (Published, Current, etc.) on each object

### Diagram Interactions
- **Show/Hide Levels**: Use "Show Next Level" or "Hide" buttons to expand/collapse object hierarchies
- **View Details**: Select objects and use "Show Details" icon to preview properties without closing diagram
- **Open Objects**: If available, use "Open" icon to navigate to object in source system
- **Favorites**: Use "Add to Favorites" icon for frequently-used data products

### Objects Included in Lineage
- SAP Datasphere tables and views
- SAP Analytics Cloud models, stories, and insights
- SAP BW systems: BW Query objects (ELEM), BW Data Transfer Processes (DTPA) and Transformations (TRFN)
- Data subscriptions (DSUB) from SAP BW/4HANA (minimum version: SAP BW/4HANA 2023 Support Package Stack 4)

### System Container Information
- **Connected Systems**: Display user-friendly business or technical name extracted from source system
- **Unmonitored Systems**: Show system type + "unmonitored" label for systems not connected to catalog
- **Additional Details**: When sharing data products, view system type, deployment region, and system ID

## Data Owner Roles & Privileges

Catalog governance requires clear permission structures. Key role privilege combinations control who can:
- Publish/unpublish assets and terms
- Manage tags, glossaries, and KPIs
- View and edit glossaries, terms, KPIs
- Create and manage glossary categories

Refer to detailed privilege matrices in source documentation for complete access control configurations.

## Recent Features & What's New (April 2026)

### Data Transfer Process Support
- New link type (dashed line) in Impact and Lineage Analysis diagram
- Support for BW Data Transfer Processes (DTPA) and associated Transformations (TRFN) across all BW systems
- Complete data traceability control showing how transformations connect to and are used within DTPs
- Better understanding of BW data flow and dependencies

### Data Composer & Customer Data Unification
- SAP Datasphere Data Composer harmonizes customer data from multiple data products
- Consolidates disparate records into comprehensive customer profiles
- Supports deterministic (rule-based) and probabilistic (ML-based) matching models
- Outputs harmonized profiles as "Potential Customer Profile" data product

### Data Center Availability Expansion
- Switzerland EU Access (CH20) — no SAP Databricks, no SAP BDC Connect
- Australia (AP20), Singapore (AP21) — no SAP Databricks
- Canada (CA20) — all core solutions
- Korea (AP12), Brazil (BR10, BR20)
- Frankfurt EU Access (EU11) — no SAP Databricks, no SAP BDC Connect
- Saudi Arabia: Dammam (SA30 regulated, SA31 non-regulated) — no SAP Databricks

### Multi-Source System Installation
- Install single intelligent application multiple times for different source systems
- Each source system creates (or reuses) own ingestion space with dedicated APIs
- Source-specific preparation and application spaces created with aliases

### BDC Connect Release
- Available on AWS, GCP, Azure
- Secure zero-copy sharing via Delta Sharing
- Bidirectional data product sharing between SAP BDC and Databricks
- Advanced analytics and AI/ML acceleration

### New System Integrations
- **SAP HANA Cloud**: Integrate as data product consumer
- **SAP SuccessFactors**: Integrate as data provider (human capital management)
- **SAP S/4HANA Cloud Public Edition**: Integrate as data provider
- **SAP Customer Data Platform**: Integrate as data product consumer
- **Existing Databricks Systems**: Share data products to/from Databricks

### Enhanced Installation & Activation Management
- Installation statuses for individual data products and content objects within packages
- Installation/Activation issue cleanup directly from Intelligent Applications and Data Packages page
- Automatic connectivity tests when selecting source systems
- Retry options directly from application/package page
- Detailed failure reasons for investigation

### Catalog Migration & SSO
- **Automated Migration**: Catalog content migrates automatically when adding SAP Datasphere to SAP BDC formation
- **Manual Migration**: Rerun migration for previously-rewired systems
- **User Favorites Migration**: Personal data migrates during catalog migration
- **Bundled SAP Cloud Identity Services**: SSO support for SAP BDC tenant and other SAP products

### Version Incompatibility Enforcement
- Intelligent application/data package incompatibility checked at activation/installation
- Clear error messaging and disabled actions for incompatible versions
- All available applications/packages listed in Available tab regardless of compatibility

### Delta Share Data Products
- Data providers create data products with Delta Sharing output port in SAP Datasphere
- Delta Share data products available in Data Products collection
- SAP Datasphere systems now source both assets and APIs
- Metadata Extractions page shows source systems organized by extracted objects (assets only, APIs only, both)

### Usability Improvements
- Updated glossary terms and KPI creation/management pages
- Visual cues for AI-generated enrichment content
- Updated avatars and colors in catalog search grid view
- Reorganized source property groupings on asset details page
- Renamed monitoring page to "Metadata Extractions"
- Renamed "systems table" to "Remote Systems" with reorganized information
- System-specific actions moved to system rows (e.g., Configure for SAP BW only)
- Updated system details page with toolbar in header

### Activity Tracking
- Track user activities for intelligent applications and data packages
- Monitor installation, uninstallation, update, repair, cleanup
- Monitor activation, deactivation, update, repair, cleanup for data packages
- View correlation ID and failure descriptions per activity

### Data Product Information & Share Status
- View API object information on data product details page
- Improved share status monitoring (checks every 24 hours)
- Auto-update: Deleted shares → Shareable; Long In Progress → Shareable or Shared

### Intelligent Application Entitlement Changes
- New dedicated status when commercial entitlement expires/terminates
- Automatic uninstallation/deactivation no longer occurs (reduces data loss risk)
- Only BDC cockpit users can uninstall applications or deactivate packages
- Visibility over missing entitlements for both cockpit users and SAP back office

### API Information & Object Details
- View detailed information about data product API objects before installation
- Helps users better understand data products before consuming them

### BW Query Objects in Analytics Cloud Lineage
- See BW Query (ELEM) objects from SAP BW 7.5 in SAP Analytics Cloud model/story lineage
- Enabled for live data connect scenarios

### SAP Datasphere Models & Tables in Lineage
- See models from local SAP Datasphere in SAP Analytics Cloud insight lineage
- See SAP Datasphere tables in data product lineage (when source system is SAP Datasphere)
- Note: For insights saved before update, open and re-save in SAP Analytics Cloud, wait minutes for metadata extraction, then view lineage

## References
- `references/governing.pdf` — Complete SAP BDC Catalog Governance Guide (129 pages)
- `references/pdfdownload.pdf` — SAP BDC What's New / Changelog (9 pages)
