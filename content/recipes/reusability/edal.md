# Publishing Research Data via the e!DAL-PGP Repository

````{panels_fairplus}
:identifier_text: <>
:identifier_link: 'https://w3id.org/faircookbook/<>'
:difficulty_level: 2
:recipe_type: guidance
:reading_time_minutes: 20
:intended_audience:  data_manager, data_producer, principal_investigator
:has_executable_code: nope
:maturity_level: 0
:maturity_indicator: 0
:recipe_name: Publishing Data with the e!DAL-PGP Repository
````

## Main Objective

The Plant Genomics and Phenomics (PGP) repository provides a scalable infrastructure for publishing research data {footcite}`Arend2014`. 
Submitting data through the e!DAL web wizard ensures that datasets receive a persistent identifier (DOI) and are enriched with high-quality metadata.
This recipe guides users through the specific steps of the e!DAL submission wizard, covering legal agreements, metadata provision, creator management, and data upload.

The main objective is to maximize the **Findability** and **Reusability** of the data by:
1.  Formalizing data usage early through the Data Deposit & License Agreement (DDLA).
2.  Providing rich descriptive metadata (Titles, Abstracts).
3.  Uniquely identifying contributors via ORCIDs and RORs.
4.  Ensuring data integrity during the upload process.

## Graphical Overview

````{dropdown}
:open:
```{figure} ../../../images/edal_flow.png
---
width: 300px
name: eDAL Submission Process
alt: eDAL Submission Process
---
eDAL Submission Process
```
````

## FAIRification Objectives, Inputs and Outputs

|Actions.Objectives.Tasks|Input|Output|
|--- |--- |--- |
|data deposition|Research Data|DOI|
|annotation|Metadata|Landing Page|

## Table of Software and Tools

|Tool Name|
|--- |
|e!DAL-PGP Repository|
|ORCID|
|ROR (Research Organization Registry)|
|e!DAL-PGP Knowledge Base|

## Step-by-Step Process

### Step 0: Login and Initiation

Before submitting data, you must authenticate to the system.
1.  **Login**: Access the e!DAL-PGP web interface and log in using your institutional credentials or the provided authentication method (e.g. ELIXIR AAI).
2.  **Start Submission**: From your dashboard, click the **"New Submission"** button to launch the submission wizard.

### Step 1: Data Deposit & License Agreement (DDLA)

The first step of the wizard is legal clearance. You will be presented with the **Data Deposit & License Agreement (DDLA)**.
1.  **Review Terms**: Read the terms carefully. This agreement confirms you have the right to publish the data and that you accept the repository's terms of service.
2.  **Accept**: You must accept the DDLA to proceed to the metadata entry stages.

### Step 2: Provide Basic Dataset Information

The wizard will now ask for the core identity of the dataset (displayed as "Step 2 of 4").

1.  **Dataset Title**: Provide a descriptive title.
    * *Example:* "My PhD project" is insufficient; prefer titles that describe the biological context (e.g. "Drought stress response in winter wheat").
2.  **Description**: Enter a comprehensive abstract describing the content and purpose of the dataset.
3.  **License**: Select an appropriate license from the dropdown menu to define usage rights. The default recommendation is often `Creative Commons Attribution 4.0 International`.

### Step 3: Add Creator Information and Affiliations

In Step 3, you must credit the individuals responsible for the data. This interface connects authors to global identifiers.

1.  **Review Current Authors**: The list displays current authors with their roles (e.g. Creator) and ORCID iDs.
2.  **Add/Edit Author**: When adding a new author, a detailed form appears:
    * **Author Role**: You must select between **Creator** (primary researcher) or **Contributor**. *Note: At least one creator is required.*
    * **ORCID**: Input the author's Open Researcher and Contributor ID (e.g. `0000-0002-1825-0097`) to ensure unique identification.
    * **Sync Info**: Use the **"Sync signed in user info"** button to auto-fill fields if you are adding yourself.
    * **Affiliation**: Provide the institution name (e.g. "Brown University").
    * **ROR ID**: It is highly recommended to include the Research Organization Registry ID (e.g. `https://ror.org/05gq02987`) to resolve the affiliation unambiguously.

### Step 4: Upload Research Data

The final configuration step (Step 4 of 4) handles the physical transfer of files. The interface offers two methods.

#### Option A: Local File Upload
Use this for standard uploads from your workstation.
1.  Select the **Local file upload** tab.
2.  Click **"Dateien auswählen" (Select files)** to browse your computer.
3.  **Verification**: Check the file table which displays:
    * **Relative Path**: Ensure your directory structure is preserved (e.g. `bridge_isatab_export/s_study.txt`).
    * **File Type & Size**: Verify that the file sizes match your expectations (e.g. `text/plain`, `12584` bytes).

#### Option B: S3 Access
Use this for cloud-to-cloud transfers of large datasets.
1.  Select the **S3 Access** tab.
2.  Provide the Endpoint, Access Key, Secret Key, and Bucket Name to stream data directly from object storage.

### Step 5: Final Review and Submission

Once the files are verified:

1.  **Finish**: Click the **Finish** button at the bottom right.
2.  **Review**: The system will display a final summary of your submission (Metadata, Authors, and Files).
3.  **Submit**: Confirm the submission. The dataset is now locked and sent to the internal review team for Quality Control (QC).

## Conclusion

By following these steps, you ensure that your dataset is not only stored safely but is also semantically rich and legally cleared. 
The use of **ORCIDs** for authors and **ROR IDs** for affiliations (Step 3) ensures that credit is tracked globally. 
The verification of **Relative Paths** during upload (Step 4) guarantees that complex data structures remain intelligible for future reusers.

### What to read next?
- [Learn to move through maturity levels with ISA metadata model](https://faircookbook.elixir-europe.org/content/recipes/maturity/isa-maturity-progression.html)
- [Learn to make computational workflows FAIR](https://w3id.org/faircookbook/FCB062)

## References

````{dropdown} **References**
```{footbibliography}
```
````

## Authors
````{authors_fairplus}
Sebastian: Writing - Original Draft
DanielArend: Writing - Original Draft
````

## Licence
````{license_fairplus}
CC-BY-4.0
````