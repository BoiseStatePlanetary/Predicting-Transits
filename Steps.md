## Steps
1. Go to https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TransitView/nph-visibletbls?dataset=transits
2. In Target Ephemerides select upload list of target names. Drag and drop or select the target file. (File from Elisabeth, doomed_targets_rev_20220202)
3. Next, under Observer location select Earth Observatory and then “Custom Lat/Lon”. Enter 44.49833 in the N. Latitude and -114.33388 in E. Longitude for Challis Telescope.
4. In Observing window select Custom start/end dates and set the dates needed. Usually a month or so span.
5. Select Predict Events, it might take a minute or two to collect all the data.
6. In the next window go to Select Columns - Event Window and select: Event Ingress Calendar UT, Event Ingress JD UT, Event Ingress Altitude, Event Midpoint Altitude, 
7. Event Egress Calendar UT, Event Egress JD UT, Event Egress Altitude
8. In the same Select Columns window scroll down to Observability Stats and select: Duration Observable Before Event, Duration Observable After Event
9. In the same Select Columns window scroll down to Photometry and select V band.
10. After selecting your columns they should all populate in the main window.
11. Next, set the Event Fraction Observable to =1
12. Set the Event Egress Altitude (degrees), Event Ingress Altitude (degrees), and the Event Midpoint Altitude (degrees) to >=30.
13. Next, remove the most precise flag (originally set at 1). 
14. Set the Duration Observable before and after the event to >=0.5 (Elisabeth makes a note that we would rather have 1 hour but we can filter later).
15. Finally to get the events in order, sort by Event Ingress JD UT by clicking once on the upwards arrow in that column. Download the table.
16. Open Jupyter notebook. Be sure to have a folder labeled “ephem_files” and put the table just made from the NASA Exoplanet Archive in the folder.
17. Next run the ipny file labeled “Find_Transits_Window”. In the third cell change both the when = “Challis-Transits” and file_for_when[“Challis-Transits”] to whatever name fits the data (an example is Challis-Transits-May-June).
18. Also change the csv in ephem_files/csv to the name of the table that is now in the folder ephem_files.
19. After running the entire Notebook, you should end up with a file in the main folder with the same name as made in step 17.
20. Download this text file and filter for any days with no events
