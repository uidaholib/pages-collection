# pages-collection

https://github.com/uidaholib/pages-collection

> **project in progress!**

a project to generate a digital collection site using gh-pages given:
- csv of collection metadata
- directory of images or pdfs

Since it uses gh-pages, it is only suitable for small collections, with lower resolution images.
It is intended as a simple template for hands-on teaching about digital libraries.

Configuration and set up will be as easy as possible, and will be documented step-by-step.
We will prefer commonly understood formats (such as CSV over YAML), and convention over configuration (follow the example over learn all the options).

Layout using [Bootstrap](https://getbootstrap.com/docs/4.0/getting-started/introduction/).

## Get started

Create a new GitHub repository by importing or forking this repo.

Edit the `_config.yml` with your collection and repository info.

Look at `docs/metadata-template.csv` for the metadata template, and `docs/metadata-info.csv` for metadata guidelines.

Create your metadata following the template and drop it into `_data` folder replacing `metadata.csv`.

Edit the `_data/metadata-config.csv` to choose the order and display name for the metadata fields. 
The fields will display in the order given in the csv, and will use the "display-name" value. 
Fields not included here will not be displayed.

Put your objects (images, pdfs) in `objects` folder, ensuring that they match the `filename` column of your metadata. For the easiest set up, the filename should match the indexid + file extension.

Create thumbs for your objects, ensuring they match indexid_sm.jpg.

Edit the about page text.

Edit the home page text.

## Features

### data export directory

The project automatically generates versions of you metadata that are exposed in the `/data/` directory for sharing or ingest into other tools.
Visualizations such as the table and subjects make use of the json stored in `/data`.
