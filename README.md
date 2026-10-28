# Evaluating Vision-Language Models for Urban Change

## Overview

This repository contains data and resources for evaluating the capabilities of Vision-Language Models (VLMs) in understanding urban environments and identifying changes in the built environment over time.

The research explores how VLMs can percieve urban structures, understand the functional characteristics of neighborhoods, detect temporal changes in the built environment from urban map. The map is constructed from building footprint data and available Point of Interest (POIs) downloaded from OpenStreetMap (OSM). 
The dataset covers three urban study areas: **Chicago, Los Angeles (LA), and Brooklyn**, with building data and POIs corresponding to **2013 and 2023**.


## Research Objectives

The main objectives of this research are to:

- **Understand the built environment:** Examine neighborhood characteristics using building footprints and POIs.
- **Evaluate VLM capabilities:** Assess how effectively VLMs interpret urban environments and extract meaningful information.
- **Detect temporal changes:** Investigate changes in building configurations between different years.
- **Analyze neighborhood development:** Explore whether information extracted by VLMs can support the assessment of neighborhood development over years.


## Repository Structure

The repository is organized by city. Each city directory contains building-level CSV files for 2013 and 2023, together with a `dataset` directory containing neighborhood images and ground-truth metadata.

```text
Evaluating-VLMs-for-Urban-Change/
│
├── README.md
│
└── data/
    │
    ├── Chicago/
    │   ├── building_data_with_cat_2013_Chicago.csv
    │   ├── building_data_with_cat_2023_Chicago.csv
    │   └── dataset/
    │       ├── images/
    │       │   ├── <GEOID>_2013.png
    │       │   ├── <GEOID>_2023.png
    │       │   └── ...
    │       └── metadata/
    │           └── final_agent_ground_truth.json
    │
    ├── LA/
    │   ├── building_data_with_cat_2013_LA.csv
    │   ├── building_data_with_cat_2023_LA.csv
    │   └── dataset/
    │       ├── images/
    │       │   ├── <GEOID>_2013.png
    │       │   ├── <GEOID>_2023.png
    │       │   └── ...
    │       └── metadata/
    │           └── final_agent_ground_truth.json
    │
    └── Brooklyn/
        ├── building_data_with_cat_2013_Brooklyn.csv
        ├── building_data_with_cat_2023_Brooklyn.csv
        └── dataset/
            ├── images/
            │   ├── <GEOID>_2013.png
            │   ├── <GEOID>_2023.png
            │   └── ...
            └── metadata/
                └── final_agent_ground_truth.json
```

## Dataset Description

### 1. Building-Level Data

Each city has two CSV files containing building-level data for 2013 and 2023.

| Attribute | Description |
|---|---|
| `GEOID` | Identifier associated with the census tract to which the building belongs. |
| `geometry` | Polygon geometry representing the building footprint, typically encoded as a WKT geometry string. |
| `height` | Recorded building height. |
| `nycdoitt:bin` | Building Identification Number (BIN) attribute, where available in the source data. |
| `building` | Building-related attribute from the source dataset, such as a building type or tag. |
| `building_category` | Category assigned to the building, such as `accomodation` in the supplied example. |

The available attributes may vary depending on the source data and city.

**Files:**
- `building_data_with_cat_2013_city.csv` — Building-level data for 2013.
- `building_data_with_cat_2023_city.csv` — Building-level data for 2023.

### 2. Neighborhood Images

**Directory:** `dataset/images/`

This directory contains images representing census tracts for both 2013 and 2023.

The images provide visual representations of neighborhood building configurations (polygins) and POIs (points) between the two time periods.
Each city's image directory contains the corresponding images for its census tracts and study years.

### 3. Ground-Truth Metadata

**Directory:** `dataset/metadata/`

This directory contains a JSON file with ground-truth (GT) information for the dataset.
The ground-truth information provides reference labels for evaluating model outputs. 

## Research and Evaluation Tasks

The dataset supports the investigation of three broad aspects of urban understanding:

1. **Physical & Functional characteristics:** Percieving features regarding building footprints and POIs from urban map.
2. **Temporal change:** Comparing observations from 2013 and 2023 to examine changes in the built environment.
Together, these tasks support an evaluation of whether VLMs can interpret urban environments and reason about neighborhood change rather than simply describe individual images.

## Getting Started

To explore the dataset:

1. Navigate to the relevant city directory under `data/`.
2. Open the 2013 and 2023 building CSV files to inspect the building-level attributes.
3. Explore `dataset/images/` to access census-tract images for the two years.
4. Inspect the JSON file in `dataset/metadata/` to understand the ground-truth labels and their organization.
5. Match the relevant images and building records using the available census-tract identifiers and metadata.

## Intended Use

This repository is intended to support research on:

- Vision-Language Models for urban understanding
- Building-level feature extraction
- Visual analysis of urban environments
- Temporal built-environment change detection
- Neighborhood development assessment

## Citation

If you use this dataset in your research, please cite the associated publication.
Tasmiah Tamzid Anannya, Tanzima Hashem, and Mohammed Eunus Ali. 2026. From Footprints to Futures: Evaluating VLMs for Physical, Functional, and Temporal Urban Change Detection. In The 34th ACM International Conference on Advances in Geographic Information Systems (SIGSPATIAL ’26), November 03–06, 2026, Riverside, CA, USA. ACM, New York, NY, USA, 13 pages. https://doi.org/10.1145/3841645.384331

## License

The license and permitted uses of the dataset should be specified by the repository owner. Please add an appropriate license before distributing the data or authorizing reuse.
