# Room-and-Pillar Mining: Underground Surveying and 3D CAD/GIS

A research and simulation project for underground survey control network design, traverse accuracy assessment, and interactive 3D visualization of room-and-pillar mining environments.

## Interactive 3D Mine Model

[![Room-and-pillar underground mining 3D CAD/GIS visualization](https://raw.githubusercontent.com/phisan-chula/2027-RoomPillar/0dc209da0c4cc0fe179a86c391e023ab66fff7f3/Room_Pillar_3d.jpeg)](https://sites.google.com/view/subsurface-3d-cadgis-room-and-/full-page-embed)

**[Launch the interactive 3D CAD/GIS application](https://sites.google.com/view/subsurface-3d-cadgis-room-and-/full-page-embed)**

The browser-based demonstration provides configurable room-and-pillar geometry, multiple mining horizons, engineering and geomechanical indicators, 3D and 2D views, virtual walkthroughs, and illustrative machinery fleet and SLAM visualization.

### Room-and-Pillar Mining with Machinery and Access Ramps

**[Launch the interactive 3D machinery and ramp model](https://phisan-chula.github.io/2027-RoomPillar/room_pillar_machinery_ramp.html)** (requires GitHub Pages to be enabled for the `main` branch, root directory).

[View or download the HTML source](room_pillar_machinery_ramp.html) — alternatively, download the HTML file and open it in a WebGL-enabled browser with internet access.

### Example mine configuration

| Parameter | Value |
|---|---:|
| Model extent | 1,000 × 1,000 m |
| Pillar dimensions | 15 × 15 m |
| Corridor width | 8 m |
| Unit cell pitch | 23 m |
| Excavation height | 5 m |
| Mining horizons | 5 |
| Vertical interval | 50 m |

## Underground Traverse Network Simulation

The Python simulation investigates error propagation and geometric degeneracy in long underground survey control networks, where GNSS positioning is unavailable. It compares total station observation strategies, consecutive station links, and supplementary gyro-theodolite azimuth observations using least-squares network adjustment.

| Simulation parameter | Configuration |
|---|---|
| Traverse length | 5 km and 10 km |
| Control target spacing | 250 m (example simulation) |
| Horizontal direction standard deviation | 2 arcsec |
| Distance standard deviation | 3 mm |
| Gyro-azimuth standard deviation | 5, 20 or 60 arcsec |
| Network datum | Inner-constraint and fixed-control scenarios |
| Error ellipses | 95% confidence level |

Simulation cases compare networks with and without consecutive total station links and gyro observations, including gyro observation intervals of every fifth and tenth total station setup.

## Repository Contents

| File or directory | Description |
|---|---|
| [corridor_network_sim_updated.py](corridor_network_sim_updated.py) | Survey network simulation, adjustment preparation and visualization |
| [script_simu/](script_simu/) | Batch scripts for 5 km and 10 km traverse experiments |
| [RESULT_run_5km_gyro5sec/](RESULT_run_5km_gyro5sec/) | Example simulation results |
| [RESULT_run_5km_gyro5sec_fix/](RESULT_run_5km_gyro5sec_fix/) | Example fixed-control simulation results |
| [Traverse_Degeneracy_Dec2026.pdf](Traverse_Degeneracy_Dec2026.pdf) | Technical report on traverse degeneracy |
| [Traverse_Degeneracy_Dec2026.docx](Traverse_Degeneracy_Dec2026.docx) | Editable technical report |
| [UndergrTraverse_PSN.pdf](UndergrTraverse_PSN.pdf) | Additional underground traverse documentation |
| [subsurface_3d_machinery_room_and_pillar.html](subsurface_3d_machinery_room_and_pillar.html) | Interactive subsurface 3D visualization |
| [underground_room_and_pillar_cad_gis_map_plan.html](underground_room_and_pillar_cad_gis_map_plan.html) | Underground CAD/GIS map and plan visualization |

## Running the Simulation

Clone the repository and install the Python dependencies:

```bash
git clone https://github.com/phisan-chula/2027-RoomPillar.git
cd 2027-RoomPillar
pip install numpy pandas geopandas shapely scipy lmfit matplotlib
```

Install GNU Gama (with `gama-local` available on your PATH) for network adjustment and optionally install `feh` for viewing output plots in Linux.

Run an example experiment from the repository root:

```bash
bash script_simu/run_5km_gyro5sec_fix
```

The batch script runs five network configurations in parallel and generates plots, observation XML, coordinate CSV files and logs.

## Research Objectives

- Quantify longitudinal and transverse positioning uncertainty in extended underground traverses.
- Assess the contribution of gyro-theodolite azimuth observations and total station network connectivity.
- Compare survey control strategies for long underground corridors.
- Explore integration of underground survey control, 3D CAD/GIS, machinery navigation and SLAM-based mapping.

**Research prototype:** Simulation results and illustrative mine geometry are intended for research and engineering evaluation, not as a substitute for site-specific survey or geotechnical design validation.
