There are two directories in this project:

1. "source" contains all of the original portfolio files 2. "production" contains the updated version of the portfolio files

To run this application, open production/index.html.

To run this application so that PageSpeed Insights can be used without hosting it on a server, perform the following steps (it is assumed that ngrok has been installed).

1. cd to the production directory, and use the python command shown below to run a local server:

```bash
$> cd /path/to/production
$> python -m SimpleHTTPServer 8080
```

2. To view the page in a browser, go to localhost:8080

3. In the same directory as the previous step, run the following ngrok command to make the local server set up in the previous step accessible remotely:

``` bash
$> ngrok 8080
```

4. Copy the public URL ngrok provides and run it through PageSpeed Insights.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~~~~~~~~~~~~~~~~~~~~~~~~~ OPTIMIZATION SUMMARY ~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ index.html ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The initial PageSpeed Insight scores were: 89 for desktop and 75 for mobile.

The following optimizations were performed to improve the PageSpeed Insights score:

1. Loaded analytics.js asynchronously. This improved my PageSpeed Insights score by 1 for both desktop and mobile.

2. In-lined Google fonts. PageSpeed Insights improved to 81 for mobile and 91 for desktop.

3. In-lined contents of print.css. PageSpeed Insights improved to 87 for mobile and 93 for desktop.

4. In-lined contents of style.css. PageSpeed Insights improved to 93 for mobile and 96 for desktop.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ main.js ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following modifications were made to speed up the scroll rate (to easily check the rate in Hz, a conversion was added to the script to display the rate in Hz along with the average time per frame over 10 frames):

1. In the updatePositions() function, moved the code that queries the current scrollTop element outside of the for loop. This made the average scroll rate almost 10 times faster.

2. Moved the code that queries the document to find all of the pizza objects into the addEventListener() function instead of running that query every time the page is scrolled. This chance made the average scroll rate nearly 4 times faster.

The following modifications were made to speed up the pizza re-sizing:

1. Moved command to query number of randomPizzaCotainers outside of for loop. Also replaced query commands inside the changePizzaSizes() function with the randomPizzaItems object built outside the function.

2. Since all pizzas are sized together, only query current size for one of the objects, not all of them inside a for loop.
