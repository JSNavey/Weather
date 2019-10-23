# Global Average Temperature 
https://temperature-statistic.netlify.com

The graph presents the means of global temperature.  The data has been recording since 1880 until 2018. 

## Ojectives of this repository ##
- To solidify the knowledge of how to get the data by using fetch() and asynchronous events handler with Promise (async / await) which it makes the code shorter and more readable.
- To render the data to the DOM and display it as a line graph on HTML5 canvas with `Chart.js`.

## Steps ##

***Get Data***
1. Load CSV dataset and sae locally.
2. Create a test file and add a few dataset into it. This will make it easier to inspect and figure it out as the data is smaller.
3. Create `getData()` to fetch the data by using `fetch()` and `async / await` instead of using `.then()`. Return the rdata in text form `response.text()`.
4. Parse the dataset to be row and columm with `split()` and `slice()`.
5. And select the data that we need which is only `year and temperature: columm[0], columm[1]`.
6. Create empty array variables(`xYear = [] / yTemp = []`). Push `year` and `temperature` values into them.
*Note:*
*Number in CSV file is String so we need to convert the number into Number by using `parseInt() or parseFloat()`.*
*The temperature data is based on the means which is `14°C` so I need to add 14 to get the real temperature degree.* 
7. Return `{ xYear, yTemp }` as an object. *So I can move xYear and yTemp from global variables into the getData function which makes the code looks cleaner and avoid any future problems*

***Draw the Line Chart with Chart.js***
8. Install Chart.js CDN in script tag in head section.
9. Create `<canvas id="chart"></canvas>`. 
10. Copy the sample code and paste above `getData() function`.
11. Create `chart()` and cover the graph sample code.
12. Set a new variable to hold the data that fetch from `getData function` with Promise.
13. Change the id in `document.getElementById('chart')`. to be the same as canvas's id.
14. Change `type: ''` to be line.
15. Set `labels: tempData.xYear` for X axis values.
16. Under datasets, set `data: tempData.yTemp`. for Y axis values.
17. Adjust background color, border color and fill elements.
18. Add temperature degree symbol for temperature axis (Y) in options block.
19. Style canvas using inline style (because there're only the size and background color so I decide to use inline instead of creating a new CSS file).
20. Document the process in README :)

## Tools, Libraries and References ##
- VS extension `Live Server`: a quick development live server with live borowser reload.
- Chart.js
- Data from: https://data.giss.nasa.gov/gistemp and Temperature Means from https://earthobservatory.nasa.gov/world-of-change/DecadalTemp

###### Tip #####
To add temperature degree symbol on Mac `shift option 8`. 

