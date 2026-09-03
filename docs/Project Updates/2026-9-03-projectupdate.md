# Technical Specifications Complete
*September 3, 2026*

The Lyrasis CST Interoperability Project Phase I Team is excited to share technical specifications for **six** new features for Lyrasis Community-Supported Technologies! The features are based on specific [community-supported use cases](https://lyrasisorghome.github.io/InteroperabilityProject/Project%20Updates/2026-03-06-projectupdate/).

In May, we added Senior Software Engineer Ryan Morrison-Westphal to the team. With Ryan's expertise, we sped up the project and produced the level of detail required for developers to create the intended features.

## Feature Overviews
The project team designed six features. All 5 CSTs (ArchivesSpace, CollectionSpace, DSpace, Fedora, VIVO) are represented across the features.

The feature descriptions below are based on the design so far, not the true implementation of the products. Nothing has been built yet. The next phase of the CST Interoperability Project is feature and product development. During the development phase, details about the functionality and user experience are subject to change. The Phase I team used technical specification documents (link) to communicate the detail and context required to design features as intended.

### [Integration Scenario Registry](https://github.com/lyrasisorghome/InteroperabilityProject/issues/58)
*Fedora, DSpace, VIVO, CollectionSpace, and ArchivesSpace*

The Integration Scenario Registry is a new product, not a new feature or enhancement to an existing CST. It is an open hub for people working with any CST to submit information or search for information about integrations. Integrations among CSTs (e.g., Fedora <> DSpace) are accepted as well as integrations that link to technology outside of the Lyrasis CST ecosystem (e.g., Fedora <> Archive-It).

The product is specified as a read/write GitHub-native registry. Anyone with a GitHub account can submit an integration to the registry, guided by a submission form and data model. The data model requires users to include the source system, the target system, the type of integration, what protocols or standards it requires, and a description of the integration. Optional information includes links to code repositories, configuration notes, system versions, dependencies, and other information. The team suggested building a search interface that anyone with an internet connection can search without a login, and designed a moderation process.

### [VIVO SWORD Deposit](https://github.com/lyrasisorghome/InteroperabilityProject/issues/54)
*VIVO, any SWORD server*

The VIVO SWORD Deposit feature will allow users to deposit a file to a SWORD-enabled repository (e.g., DSpace, Dataverse), such as a publication or research data set. After the file is deposited, a link to the content is written back to the user's VIVO profile.

Users may deposit a .pdf or a METS-compliant .zip file by navigating to a publication entry and selecting a new option, e.g. "SWORD Deposit." The user will be prompted to upload a file and select "Deposit." The file is deposited to the SWORD-enabled repository and a VIVO website is added to the publication. The website contains a link back to the object in its repository. 

An administrator enables and configures the SWORD endpoint through a combination of editing VIVO runtime properties and entering endpoint information in a new Site Admin > Site Configuration > SWORD Configuration GUI.

### [ArchivesSpace SWORD Deposit](https://github.com/lyrasisorghome/InteroperabilityProject/issues/45)
*ArchivesSpace, any SWORD server*

The ArchivesSpace SWORD Deposit feature will allow users to deposit one or more files to a SWORD-enabled repository (e.g., DSpace, Dataverse), such as digitized collection material or born-digital archives. 

Users may deposit any file type that the SWORD endpoint accepts. There are three distinct user journeys (modes) specified in the feature design:

1. Users may deposit **a single file** by entering edit mode on the associated Archival Object or Resource, then Instances > Add Digital Object > Create > (new option) Upload File Version.

2. Users may deposit **many files and relate them 1:1** to an archival object by entering edit mode on the associated Archival Object or Resource, then (new option) Batch Upload and Link > Upload files.

3. Users may deposit many files and relate them all to one Archival Object or Resource by entering edit mode on the associated Archival Object or Resource, then Instances > (new button) Upload Digital Objects > Upload files.

Metadata from the Archival Object, including a link back to the digital object, is used to create the digital objects in the SWORD-enabled repository. 

After the file or group of files is deposited, ArchivesSpace digital objects for each file deposited to the endpoint are created. Each digital object contains a link to the item in the SWORD-enabled repository. 

Once published (which the repository administrator can configure to be a default mode for the feature), each new digital object will appear in the ArchivesSpace PUI linked to an Archival Object or Resource.

An administrator enables and configures the SWORD endpoint in a new GUI page similar to the existing "Manage OAI-PMH Settings" interface.

### [ArchivesSpace <> DSpace Digital Object Linker](https://github.com/lyrasisorghome/InteroperabilityProject/issues/7)
*ArchivesSpace, DSpace*

The ArchivesSpace DSpace Digital Object Linker feature will allow users to create digital objects in ArchivesSpace from existing DSpace items, such as digitized archives or institutional archives. 

The feature then links the two records together, posting a link to the DSpace item in the ArchivesSpace Digital Object and a link to the ArchivesSpace Archival Object in the DSpace item.

The feature design recommends using existing functionality and user interfaces that will make the user journey similar to adding a digital object today. All user journeys start by entering the edit mode on the Archival Object or Resource to link, and navigating to Instances. From Instances, a user may select a new button, e.g. "Add DSpace Items." 

This will expand a list of every immediate child archival object of the host record. Each row shows the child title (or display string) and an input that can hold a provisional link to one DSpace item.

The new feature searches the DSpace API. The user can link search results in two modes:

1. Create a DO from & Link a single DSpace item to an ArchivesSpace Archival Object

2. Create DOs & Link many DSpace items to many ArchivesSpace Archival Objects

After the file or group of files is linked, ArchivesSpace digital objects for each file deposited to the endpoint are created. Each digital object contains a link to the item in the SWORD-enabled repository. 

Once published (which the repository administrator can configure to be a default mode for the feature), each new digital object will appear in the ArchivesSpace PUI linked to an Archival Object or Resource.

ArchivesSpace Digital Objects are always created anew in this feature; existing Digital Objects are *not* appended with a new File Version. An administrator enables and configures the DSpace endpoint in a new GUI menu similar to the existing "Manage OAI-PMH Settings" interface.

### [OAI-PMH for CollectionSpace](https://github.com/lyrasisorghome/InteroperabilityProject/issues/46)
*CollectionSpace, any OAI-PMH harvester*

The OAI-PMH for CollectionSpace feature will enable the Open Archives Initiative Protocol for Metadata Harvesting. After an administrator enables the feature, harvesters will be able to collect data and digital objects from CollectionSpace collection objects that are marked as *Published To* the CollectionSpace Public Browser. An administrator enables and configures the OAI-PMH settings endpoint in a new graphical user interface (GUI).

### [Shared Discovery for CollectionSpace and ArchivesSpace](https://github.com/lyrasisorghome/InteroperabilityProject/issues/51)

The Shared Discovery for CollectionSpace and ArchivesSpace specification describes a how a new search product could unify published CollectionSpace and ArchivesSpace records in one interface.

The design offers two display implementation options: (1) Display records from each repository side by side; or (2) display records in a unified interface. The project team recommended Display Option 1.

During the implementation phase, the implementation team will develop the search and display product, and release open source code so that other institutions may use it as a baseline for developing their own shared CollectionSpace/ArchivesSpace search.

## Technical Specification Documents
### About the Docs
Each specification document defines actors and roles, describes integration architecture, proposes configuration details, outlines behavior and error scenarios, and includes other information for developers as required per the project's RFP.
### Links to the Docs
1. [Integration Scenario Registry](https://github.com/lyrasisorghome/InteroperabilityProject/issues/58)
2. [VIVO SWORD Deposit](https://github.com/lyrasisorghome/InteroperabilityProject/issues/54)
3. [ArchivesSpace SWORD Deposit](https://github.com/lyrasisorghome/InteroperabilityProject/issues/45)
4. [ArchivesSpace <> DSpace Digital Object Linker](https://github.com/lyrasisorghome/InteroperabilityProject/issues/7)
5. [OAI-PMH for CollectionSpace](https://github.com/lyrasisorghome/InteroperabilityProject/issues/46)
6. [Shared Discovery for CollectionSpace and ArchivesSpace](https://github.com/lyrasisorghome/InteroperabilityProject/issues/51)

### How to Read the Docs
If you are primarily a staff user of a Lyrasis CST, you may want to read the intro then start with the Behavior Scenarios toward the end of the doc. Developer users may find interest in more of the details between those two points.
### How we made the Docs
From March to April 2026, the project team (Jess Farrell and Bridget Almas, with support from Community Staff teams) expanded use cases into gherkin-syntax behavior driven design scenarios. The behavior scenarios surfaced many questions about system architecture that we began investigating. To speed the project up, we ran the behavior scenarios through Claude to identify a list of technical specification gaps. 

In May, Ryan Morrison-Westphal, Senior Software Engineer, joined the Redstart Works team to enhance the detail of the specification documents and fill known gaps. Ryan drew upon his experience with system architecture, behavior-driven design, and full-stack software development across a variety of technology stacks, as well as his experience writing and implementing technical specifications at Amazon, to expand and iterate on the drafts produced in March and April. Ryan now works as an independent software consultant through Tripping the Bits.

After many iterations and reviews of the documents among the consultant team, the CST Director of Operations, and the CST Community Staff teams, we arrived at the documents we're sharing today. The consultant team occasionally used Claude to check for inconsistencies during revisions when, for example, a design element is changed in a 50-page specification document, and we had to find all of the places where that change would affect a feature description, diagram, behavior scenario or table data.

## What's Next
Stay tuned for updates as the CST Interoperability Project heads into Phase II, Implementation!