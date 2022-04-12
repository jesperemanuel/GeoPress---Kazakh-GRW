# GeoPressureTemplate

Analysing geolocator data with pressure is full of potential, but the the path is long and the journey can be challenging. `GeoPressureTemplate` is a [Github repository template](https://docs.github.com/articles/creating-a-repository-from-a-template/) for a startup R project to make that journey easier.

## What is this template and who is it for? :mag_right:

`GeoPressureTemplate` aims to help researchers analyse their geolocator data with [`GeoPressureR`](https://raphaelnussbaumer.com/GeoPressureR/). It provides the backbone R code containing the folder structure and code to correctly label your data and produce basic trajectory figures. 

In essence, it contains the code from all the [GeoPressureR vignettes](https://raphaelnussbaumer.com/GeoPressureR/articles/) packaged in an `.R` file to make it easy for you to apply it to your own data. 

## What do you need to use this template? :computer:

- Geolocator data containing pressure, light and activity data.
- Have read the [GeoPressureR vignettes](https://raphaelnussbaumer.com/GeoPressureR/articles/) (:warning: You should be familar with the **full process involved** before starting with your own project)
- Basic R experience
- A Github account


## Project structure :file_folder:

Following the recommendations of [rrrpkg](https://github.com/ropensci/rrrpkg), the project contains:
1. Standard description files at the root (`DESCRIPTION`, `.Rproj`, `README.md`, `LICENCES`,...)
2. `data/` folder containing the raw geolocator data, the pressure and light labelled files and the data generated with the code from `analysis/`. Note that you could put the geolocator and labelization files in `raw-data`, following `usethis()` standard 
3. `analysis/` contains all the `.R` code used for your project
4. `report/` reads the data generated and produces sharable results (figures, html page, manuscript, etc...)
<details>
  <summary>See directory tree</summary>

```
GeoPressureTemplate
├── DESCRIPTION          		# project metadata and dependencies
├── README.md            		# top-level description of content and guide to users
├── GeoPressureTemplate.Rproj    # R project file
├── data
│   ├── 0_PAM
│   │   ├── 18LX
│   │   │   ├── 18LX_20180725.acceleration
│   │   │   ├── 18LX_20180725.data
│   │   │   ├── 18LX_20180725.glf
│   │   │   ├── 18LX_20180725.log
│   │   │   ├── 18LX_20180725.magnetic
│   │   │   ├── 18LX_20180725.pressure 
│   │   │   └── 18LX_20180725.settings
│   │   └── 22BT
│   │       └── ...
│   ├── 1_act_pres_labels
│   │   ├── 18LX_act_pres-labeled.csv
│   │   ├── 18LX_act_pres.csv
│   │   ├── 22BT_act_pres-labeled.csv
│   │   ├── 22BT_act_pres.csv
│   │   └── ...
│   ├── 2_light_labels
│   │   ├── 18LX_light-labeled.csv
│   │   ├── 18LX_light.csv
│   │   ├── 22BT_light-labeled.csv
│   │   ├── 22BT_light.csv
│   │   └── ...
│   ├── 3_pressure_prob
│   │   ├── 18LX_pressure_prob.Rdata
│   │   ├── 22BT_pressure_prob.Rdata
│   │   └── ...
│   ├── 4_light_prob
│   │   ├── 18LX_light_prob.Rdata
│   │   ├── 22BT_light_prob.Rdata
│   │   └── ...
│   ├── 5_static_prob
│   │   ├── 18LX_static_prob.Rdata
│   │   ├── 22BT_static_prob.Rdata
│   │   └── ...
│   ├── 6_basic_graph
│   │   ├──	18LX_basic_prob.Rdata
│   │   ├── 22BT_basic_prob.Rdata
│   │   └── ...
│   ├── 7_wind_graph
│   │   ├──	18LX_wind_prob.Rdata
│   │   ├── 22BT_wind_prob.Rdata
│   │   └── ...
│   └── gdl_settings.xlsx
├── analysis
│   ├── 1-pressure.R
│   ├── 2-light.R
│   ├── 3-static.R
│   ├── 4-basic-graph.R
│   └── 5-wind-graph.R
└── report
    ├── 1-pressure.R
    ├── 2-light.R
    ├── 3-static.R
    ├── 4-basic-graph.R
    └── 99-combined.R
```
</details>

## Where to start? :bulb:

### Create your project 

- Create your project repo by clicking on "[Use this template](https://github.com/Rafnuss/GeoPressureTemplate/generate)" button on the Github page.
- Choose a project name (`my_tracking_study_name`) specific to your research. Note that `my_tracking_study_name`  will become the name of your folder on your computer too. Add a description of your study.
- Clone the repository on your computer
- Done! :tada:

### Make yourself at home :house:

- Rename `GeoPressureTemplate.Rproj` to `my_tracking_study_name.Rproj`.
- Open the R project file with RStudio. 
- Edit the `DESCRIPTION` file (see https://r-pkgs.org/description.html for details). Start the version to `0.0.1` or `0.1.0`.
- Delete the content of `README.md` and start writing your research objectives, describing your basic data, method etc.
- Install the dependencies needed with

```
devtools::install()
```


- Delete the content of `data/` (but keep the directory tree). Put your PAM data in `data/0_PAM/` in a folder with the GDL_ID code (e.g. `data/0_PAM/18LX/`)
- Enter the information you already have about your track in the `gdl_setting.xlsx` spreadsheet. You can add new columns if needed.

## Start analysing the data :chart_with_upwards_trend:

Now that you are set-up, it's time to start the serious work. :grimacing: Follow the order of the `.R` code in the `analysis/` folder. They follow the same order as the vignettes (but with different numerotation).

|  GeoPressureTemplate analysis |  GeoPressureR vignettes  |
|---|---|
|  `1-pressure.R`  |  [Creating probability maps from pressure data](https://raphaelnussbaumer.com/GeoPressureR/articles/pressure-map.html) |
|  `2-light.R` |  [Creating probability maps from light data](https://raphaelnussbaumer.com/GeoPressureR/articles/light-map.html) |
|  `3-static.R` | [Preparing data for trajectory modelling](https://raphaelnussbaumer.com/GeoPressureR/articles/preparing-data.html)  |
|  `4-basic-graph.R` |  [Modeling trajectory with a graph](https://raphaelnussbaumer.com/GeoPressureR/articles/basic-graph.html) |


## Generate Report :page_facing_up:
Coming soon!


## Advanced options :link:

- Generate your DOI with [Zenodo](https://zenodo.org/).
- Generate a citation file with [`usethis::use_citation`](https://usethis.r-lib.org/reference/use_citation.html) and [`cffr`](https://github.com/ropensci/cffr).
- Use [`renv`](https://rstudio.github.io/renv/index.html) to make your work reproducable.
- Export your data on [Movebank](https://www.movebank.org/cms/movebank-content/import-custom-tabular-data).
