empty
# NetCDF Raster Sandbox (ncview)

A fully browser-based tool for visualizing, analyzing, and exploring multidimensional NetCDF (`.nc`) datasets.

**Live Demo:** <https://coliveir-aer.github.io/ncview/>

## Overview

This application allows users to load NetCDF files directly into their web browser for visualization. It relies on WebAssembly (`h5wasm`) to parse data locally on the client side, meaning no data is ever uploaded to a server. It is built as a highly portable, single-file HTML application.

## Key Features

* **Client-Side Parsing:** Fast, local processing of NetCDF files using WebAssembly and Web Workers.

* **Multidimensional Data Support:**

  * **1D Sequences:** Automatically rendered as interactive line graphs.

  * **2D Rasters:** Rendered as interactive images with customizable colormaps, pan/zoom controls, and a precise pixel inspector.

  * **3D / N-D Volumes:** Visualized via a slice viewer. Includes dynamic axis mapping to easily reorient atmospheric or oceanic profiles with non-standard dimension orders.

* **Geospatial Processing:** Automatic calculation of latitude/longitude coordinates for supported satellite projections (e.g., NOAA GOES-R ABI fixed grid).

* **Map Overlays:** Toggable coastlines and political boundaries (countries and US states) using TopoJSON.

* **Metadata Inspector:** A built-in viewer to examine all global and variable-level attributes and technical metadata (dimensions, data types, fill values).

* **High-Quality Export:** Export any 2D or 3D slice view to a PNG file, with map overlays and colorbars cleanly rendered into the output.

## Usage

Because the project is designed to be fully portable, there is no build step or server required.

1. Open `portable_index.html` in any modern web browser.

2. Drag and drop a `.nc` file into the sidebar dropzone (or click to browse).

3. Select a variable from the sidebar to visualize it.

4. Use the floating control panel within each view to adjust colormaps, toggle map overlays, and export images.

## Technologies Used

* **React** (UI and State Management)

* **h5wasm** (NetCDF/HDF5 Parsing via WebAssembly)

* **Three.js** (3D Volume Slicing & Rendering)

* **Chart.js** (1D Sequence Plotting)

* **TopoJSON** (Map Boundary Rendering)

* **Comlink** (Web Worker Communication)

## Data Attribution

When applicable (e.g., when loading ABI Level 2 imagery), the tool dynamically supports parsing and projecting data from NOAA's Geostationary Operational Environmental Satellites (GOES)-R Series.
