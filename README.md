There are two directories in this project:

1. "source" contains all of the original portfolio files 2. "production"
contains the updated version of the portfolio files

To run this application, open production/index.html.

To run this application so that PageSpeed Insights can be used without hosting
it on a server, perform the following steps (it is assumed that ngrok has been
installed).

1. cd to the production directory, and use the python command shown below to run
a local server:

```bash
$> cd /path/to/production
$> python -m SimpleHTTPServer 8080
```

2. To view the page in a browser, go to localhost:8080

3. In the same directory as the previous step, run the following ngrok command
to make the local server set up in the previous step accessible remotely:

``` bash
$> ngrok 8080
```

4. Copy the public URL ngrok provides and run it through PageSpeed Insights.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~~~~~~~~~~~~~~~~~~~~~~~~~ OPTIMIZATION SUMMARY ~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The initial PageSpeed Insight scores were: 89 for desktop and 75 for mobile.

The following optimizations were performed to improve the PageSpeed Insights
score:

1. Loaded analytics.js asynchronously. This improved my PageSpeed Insights
score by 1 for both desktop and mobile.

2. In-lined Google fonts. PageSpeed Insights improved to 81 for mobile and 91
for desktop.
