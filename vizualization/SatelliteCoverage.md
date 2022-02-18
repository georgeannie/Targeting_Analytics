# Visualizations

The visualization notebooks address the two primary objectives of the challenge:

Scenario 1: Determine the “hits” where a satellite has geodetic overlap of any vessel(s) at any point(s) in time.

Scenario_1_visualization.ipynb
Scenario 2: Determine if any “holes” exist in the data that cause a loss of fidelity in data (e.g. missing identifiers).

Scenario_2_visualization.ipynb
The visualization notebooks are located here (off the main branch of the repo):

./visualization/*.ipynb
To run the visualization notebooks, perform the following steps using a computer with Docker installed:

Step 0. Change your directory to the ./visualization directory off the main branch of the repo.

cd visualization/
Step 1. Build the Jupyter Docker image using the Docker Compose program. Using a Windows Powershell or Mac/Linux Terminal, run the following command with root/admin privileges.

docker-compose build
Step 2. Start the Jupyter Docker image using the Docker Compose program. Using a Windows Powershell or Mac/Linux Terminal, run the following command with root/admin privileges.

docker-compose up -d
If you are running the container locally, you can access the Jupyter Notebook server by entering the following in your browser of choice: http://localhost:8888.

If you are running the container remotely (e.g., AWS), you can access the Jupyter Notebook server by entering the following in your browser of choice: http://<myipaddress>:8888.

NOTE: It is possible to combine Steps 1 and 2 by running the following command.

docker-compose up --build -d
Step 3. Stop the Jupyter Docker image using the Docker Compose program. Using a Windows Powershell or Mac/Linux Terminal, run the following command.

docker-compose stop
  
## Visualization Instructions
  
### Map 1 (Scenario_1_visualization.ipynb)
Map 1 is intended to display the field of views of selected satellites druing selected 5 minute time intervals. The field of view polgyons displayed on the map are colored by the confidence of the field of view calculation (green being High Confidence and red being Low Confidence). The map will also plot any vessels seen by the satellite during the selected time period. The vessels will be displayed as a cluster which can be clicked to expand and show more vessels.

Run the cells up to and including the cell containing the code to create Map 1, following the Map 1 label, or alternately select "Run All Cells" and navigate to the cell below the Map 1 label
Choose from various filter options to see the field of view of a selected satellite during a selected time period.
Choose an entity that owns the satellite. For example, in the first filter box choose 'CIS' as the satellite owner. This selection will update the options available in filter two to satellites owned by 'CIS'.
Choose a satellite owned by your selected entity or country. For example, choose 'COSMOS 1346'.
Choose a year, month and time to show field of views for your selected satellite. In this example, choose January 1, 2015.
Finally, choose a time period during your selected date to show your selected satellite field of views for. For example, choose '2015-01-01 16:00:00+00:00' as a start date and '2015-01-01 16:55:00+00:00' as an end date.
Click the 'Update Map' button.
Below the 'Update Map' button will be a printed progress message that will alert the user about what the visulization is doing. When the map is done rendering, the progress message will say 'Finished.'

### Map 2 (Scenario_1_visualization.ipynb)
Map 2 is intended to display the union of the field of views of selected satellites during selected 5 minute time intervals within a user defined area of interest. The map will plot the union of the foreign entity's field of views in red as well as any ships seen by the foreign satellies in red. The map will also display the union of the US' satellites' field of views in green as well as any ships seen by the US satellites in green. the area of interest is displayed in gray. Please note that this has been tested on a limited set of configurations (e.g. MacOS), it may not work properly on others.

Run the cell containing the code to create Map 2
Choose from various filter options to see the field of view of a selected satellite during a selected time period.
Choose an entity that owns the satellite. For example, in the first filter box choose 'CIS' as the satellite owner. This selection will update the options available in filter two to satellites owned by 'CIS'.
Choose a satellite owned by your selected entity or country. For example, choose 'AIST 1', 'AIST 2' and 'COSMOS 1346'.
Choose a satellite owned by the US. For example, choose '50 SAT', 'ACRIMSAT' and 'AEROCUBE 2'.
Choose a year, month and time to show your selected satellite field of views for. In this example, choose January 1, 2015.
Finally, choose a time period during your selected date to show your selected satellite field of views for. For example, choose '2015-01-01 05:00:00+00:00' as a start date and '2015-01-01 20:00:00+00:00' as an end date.
Click on the square icon on the left-hand toolbar of the map to activate the draw tool. Then, click and drag over an area of interest on the map.
Beneath the 'Update Map' button will be a printed progress message that will alert the user about what the visulization is doing. When the map is done rendering, the progress message will say 'Finished.'
Click the 'Refresh Map' button to clear the last drawn polygon. Draw a new polygon to recalculate the map.

### Map 3 (Scenario_1_visualization.ipynb)
Run the cell containing the code to create Map 3.
Select the MMSI of a desired vessel in the drop down.
Click 'Update Map' to plot any sightings of the vessel during 2015, (plotted in increasing time order).
