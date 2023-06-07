21-07771-003: Shoreline Change Analysis
================
Regina Lionheart
2023-06-07

![dumbbell_plot](https://img.shields.io/badge/plot-dumbbell-%231D455C)
![HCA_clustering](https://img.shields.io/badge/stats-HCA%20clustering-%233ECDA3)
![linear_model](https://img.shields.io/badge/stats-linear%20model-%231D455C)
![boxplot](https://img.shields.io/badge/plot-boxplot-%231D455C)
![3D_regression](https://img.shields.io/badge/plot-3D%20regression-%231D455C)
![quartiles](https://img.shields.io/badge/stats-quartiles-%233ECDA3)

![code_style](https://img.shields.io/badge/style-needs%20checking-red)

------------------------------------------------------------------------

TODO: Marketing needs to go over this to ensure it looks good!

> Herrera Environmental Consultants: Placeholder for our logo or
> consistent header

## Table of Contents

- [Project Description](#-Project-Description)
  - [Data Discrepancies](#-Data-Discrepancies)
  - [Metadata](#-Metadata)
- [Location in Herrera Database](#-Location-in-Herrera-Database)  
- [Requirements and Dependencies](#-Requirements-and-Dependencies)
- [Installation and Usage](#-Installation-and-Usage)
  - [Layout of Directory and Data](#-Layout-of-Directory-and-Data)
- [Visualizations](#-Visualization)

------------------------------------------------------------------------

# Project 21-07771 - Task 003

Seashore Conservation Area

**SharePoint Site: [SharePoint
Site](https://herrerainc.sharepoint.com/teams/21-07771-002)**

**Vantagepoint Site: TODO: what’s the best way to link here?**

**Site of Deliverable/Final Report if Applicable:** TODO

------------------------------------------------------------------------

### Project Description

*Be as succinct as possible in this section* This analysis aims to
characterize approximately 25 years of shoreline profile transect data,
provided by NANOOS (Northwest Association of Networked Ocean Observing
Systems). Using this data combined with area expertise, the relevant
coastal areas have been characterized and delineated into “reaches”.

### :droplet: Location in Herrera Database

The original, unmodified data used in this project is located in the
“data_raw” folder within this repository. That folder is backed up to
TODO: Fill this in. Best to use O drive? Or SharePoint?

If you do not have access to the data, please contact the emails listed
at the bottom of the repository.

### 📦 Requirements and Dependencies

TODO: Installation tips will be helpful for libraries/packages, but not
sure they need to be included in basic analysis scripts, especially for
PMs. Suggestions for this section? It was suggested from Paul/Clark to
include a “typical imports” section. A load_packages/import_packages
script could be included in the template repository (that is the case
for this analysis.)

Below is a list of packages and external softwares that this project
utilizes. Please ensure you have the package(s) installed and have
access to the tools listed below. TODO: This was something I involved in
my previous READMEs, but might be more trouble than it’s worth. Original
table(s) included all packages required, and then a separate table for
external data with its location, either URl or location on drive.

| Name                                                                                                                                            | Description                                                                                                      |
|:------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------|
| [`R`](https://www.r-project.org/)                                                                                                               | Programming language used for this project.                                                                      |
| [`NANOOS Profile Data`](https://nvs.nanoos.org/BeachMapping)                                                                                    | The raw data for analysis. If you do not have access to this data, please contact the owners of this repository. |
| [`Washington Coastal Erosion and Hazard Assessment`](https://waecy.maps.arcgis.com/apps/View/index.html?appid=389d0a3ce642485db912d4a416a56e25) | A second database used to compare the accuracy of NANOOS data.                                                   |

### :computer: Installation and Usage

In order to run this script and recreate the analysis, you will need to
have R and Rstudio installed on your computer. All the data produced by
this analysis can be found in the data_secondary/ folder, while all
figures can be found in the figures/ directory.

#### Layout of directory and data

TODO: I think a general layout should be considered part of the
repository template.

This repository is organized into a main Control.Rmd markdown script,
which produces the results from scratch when run in its entirety. The
Control script references folders of raw data (data_raw/), and produces
results data that has been modified or created by the analysis
(data_secondary/). All analysis scripts are contained in the scripts/
directory, which also contains the src/ subdirectory. The src/
subdirectory contains package loading scripts and scripts that produce
or modify data used throughout the analysis.

The data_raw/ folder is **READ ONLY** and should never be modified or
deleted.

#### Detailed description of data and analysis

The raw data consists of approximately 4500 individual profiles across
54 coastal sites in Washington and Oregon, stretching from Moclips to
Cape Disappointment. The profiles are in x y z format (Easting Northing
elevation). The naming convention is prof_X\_ssYY.out where prof is
short for profile, X is the profile number, ss is a season code (e.g. f
= fall) and YY is the year, in the format of the last two digits
(e.g. “98” is 1998”, “00” is 2000, “08” is 2008, etc).

Throughout the course of the analysis, the Control script loads and
tidies the raw profiles, creating a main csv of all profiles that
contain data (see below for data discrepancies). Profiles are visualized
and examined. Profiles are compared to an arbitrary “BasePoint” line set
a reasonable distance inland, and the Euclidean distance between this
BasePoint and each profile is calculated; over time, the increase and
decrease in this Euclidean distance is used as a proxy for shoreline
change (accretion or erosion). The rates of change are also calculated
for each profile.

These profiles are also compared to the [Washington Coastal Erosion and
Hazard
Assessment](https://waecy.maps.arcgis.com/apps/View/index.html?appid=389d0a3ce642485db912d4a416a56e25).

Finally, profiles are clustered into subreaches using a combination of
hierarchical agglomerative clustering and area knowledge. **Please be
aware that the final csv of subreach characterization CANNOT be produced
by this script, only the clustering that informed the final decision.**

#### Metadata

The vertical datum is NAVD88. The horizontal is WA State Plane South.
All of the units are in meters.

#### :exclamation: Data discrepancies

Quite a few profiles are null (empty) and have been removed and noted.
See the “Explore Profiles” section for more information.

A small portion of the profiles had non-conforming filenames: “BigE06”,
“beachface”, etc. These files do not represent a large percentage of the
files and have not been included in the analysis.

Profiles 42 - 47 are in Oregon and have been excluded from most of the
analysis.

*Geographically, profiles do not proceed sequentially.*

------------------------------------------------------------------------

## Visualization

TODO: Put any helpful images here. Should maybe go at the top?

------------------------------------------------------------------------

## 🔧 Pull Requests

Pull requests are welcome. For major changes, please open an issue
first.

All functioning code is located on the main branch. Dev branches are to
be named <specific_issue_description>\_dev.

## 💬 Contributors + Contact Information

- [Regina Lionheart](https://github.com/R-Lionheart)
- [Andrea
  MacLennan](https://www.herrerainc.com/team-member/andrea-maclennan/)
- [Ian David
  Crickmore](https://www.herrerainc.com/team-member/ian-david-crickmore/)
