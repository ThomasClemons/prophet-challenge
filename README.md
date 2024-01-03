# prophet-challenge
Assignment for AI/ML Bootcamp Module 8 Challenge

Our assignment was to analyze Mercado Libre's financial and user data to identify growth opportunities using Google Colaboratory and Prophet.

---------------------------------------------------------------------

## Description

I played the role of growth analyst at [Mercado Libre](http://investor.mercadolibre.com/about-us "http://investor.mercadolibre.com/about-us"). Mercado Libre is the most popular e-commerce site in Latin America with over 200 million users.  I was tasked with analyzing the company's financial and user data to identify growth opportunities. I wanted to find out if the ability to predict search traffic can translate into the ability to successfully trade the stock.

This challenge had four steps:

- Step 1: Find unusual patterns in hourly Google search traffic.
- Step 2: Mine the search traffic data for seasonality.
- Step 3: Relate the search traffic to stock price patterns.
- Step 4: Create a time series model with Prophet.


## Getting Started

### Dependencies

- Google User Account
- Google Colaboratory:  Google Colaboratory, or Colab, is a cloud-based notebook space, which allows you to run code in the cloud, rather than locally on your computer. These cloud-based notebooks make it easy to install the tools we need and give us the power of cloud computing.


### Installing

- Clone this repo to your environment
- Setup Google Colaboratory
    - Navigate to [Google Colaboratory](https://colab.research.google.com/notebooks/welcome.ipynb "https://colab.research.google.com/notebooks/welcome.ipynb")
    - You will need a Google account to use Colab. Sign up for an account if you don't already have one. Reference [How to setup a Google account](https://support.google.com/accounts/answer/27441?hl=en "https://support.google.com/accounts/answer/27441?hl=en") for instructions.
    - Within your Google account, navigate to [Google Drive](https://www.google.com/drive/ "https://www.google.com/drive/") and select "Go to Google Drive".
    - After navigating to Google Drive, click the New button and select Folder to create a new folder called "dev".
    - Navigate to the new folder. Once in the folder, you’ll need to connect (download) the Google Colab application:
        1. Click New.
        2. Scroll down to More and expand the dropdown menu.
        3. At the bottom of the menu, click "Connect more apps."
        4. Type “colab” in the top-right search field, and then press Enter to search for the Colaboratory application.
        5. Click the Connect button to download the Colaboratory application.
- Create a Colab Notebook
    - Create a Colab notebook by clicking New, hovering over More, and then selecting Colaboratory.
    - A new tab will launch with a new notebook. Everything is hosted online, but the functionality is very similar to Jupyter Notebook.
- Upload notebook file, '**forecasting_net_prophet.ipynb**', from your repo to Colab as follows:
    1. From the Colab notebook you just opened, click File and then "Upload notebook."
    2. Drag the notebook file into the box to upload.
**NOTE:  When you upload notebooks, Google Drive will save them by default to a folder called Colab Notebooks. These files can easily be moved to the dev folder created earlier.**


### Executing program
- Open '**forecasting_net_prophet.ipynb**' in Colab
- Step through the notebook to see my data preparation and analysis by clicking the "Run" button.
- The results are displayed after each step.

**Step 1: Find Unusual Patterns in Hourly Google Search Traffic**  
The data science manager asks if the Google search traffic for the company links to any financial events at the company. Or, does the search traffic data just present random noise? To answer this question, I looked for unusual patterns in the Google search data for the company, and connected them to the corporate financial events.

To do so, I completed the following steps and answered each question:

1. Read the search data into a DataFrame, and then sliced the data to just the month of May 2020. (During this month, MercadoLibre released its quarterly financial results.) I plotted the results. Do any unusual patterns exist?
2. Calculated the total search traffic for the month, and then compared the value to the monthly median across all months.
3. Did the Google search traffic increase during the month that MercadoLibre released its financial results?

**Step 2: Mine the Search Traffic Data for Seasonality**  
Marketing realizes that they can use the hourly search data, too. If they can track and predict interest in the company and its platform for any time of day, they can focus their marketing efforts around the times that have the most traffic. This will get a greater return on investment (ROI) from their marketing budget.

To that end, I mined the search traffic data for predictable seasonal patterns of interest in the company. To do so, I completed the following steps and answered each question:

1. Grouped the hourly search data to plot the average traffic by the hour of day. Does the search traffic peak at a particular time of day or is it relatively consistent?
2. Grouped the hourly search data to plot the average traffic by the day of the week (for example, Monday vs. Friday). Does the search traffic get busiest on any particular day of the week?
3. Group the hourly search data to plot the average traffic by the week of the year. Does the search traffic tend to increase during the winter holiday period (weeks 40 through 52)?
4. Are there any time based trends that I see in the data?

**Step 3: Relate the Search Traffic to Stock Price Patterns**  
I mentioned my work on the search traffic data during a meeting with people in the finance group at the company. They want to know if any relationship between the search data and the company stock price exists, and they ask if I can investigate.

To do so, I completed the following steps and answered each question:

1. Read in and plotted the stock price data.  Also, concatenated the stock price data to the search data in a single DataFrame.
2. Market events emerged during the year of 2020 that many companies found difficult. But, after the initial shock to global financial markets, new customers and revenue increased for e-commerce platforms. I sliced the data to just the first half of 2020 (2020-01 to 2020-06 in the DataFrame), and then plotted the data. Do both time series indicate a common trend that’s consistent with this narrative?
3. Created a new column in the DataFrame named “Lagged Search Trends” that offsets, or shifts, the search traffic by one hour. Created two additional columns:
    - “Stock Volatility”, which holds an exponentially weighted four-hour rolling average of the company’s stock volatility
    - “Hourly Stock Return”, which holds the percent change of the company's stock price on an hourly basis
4. Does a predictable relationship exist between the lagged search traffic and the stock volatility or between the lagged search traffic and the stock price returns?

**Step 4: Create a Time Series Model with Prophet**  
Now, I need to produce a time series model that analyzes and forecasts patterns in the hourly search data. To do so, I completed the following steps and answered each question:

1. Set up the Google search data for a Prophet forecasting model.  Prophet is a library built by Facebook for forecasting trends in Python. Instead of installing this library on your computer, we used Google Colaboratory. 
2. After estimating the model, I plotted the forecast. How's the near-term forecast for the popularity of MercadoLibre?
3. Plotted the individual time series components of the model to answer the following questions in the space provided in the starter file:
    - What time of day exhibits the greatest popularity?
    - Which day of the week gets the most search traffic?
    - What's the lowest point for search traffic in the calendar year?


## Help

- Please execute all steps in the notebook.  The results of above steps are used in subsequent steps. 


## Authors

- Author:  Tom Clemons

## Version History

- 0.1
    - Initial Release

## Acknowledgments

- Mercado Libre About Us page:  http://investor.mercadolibre.com/about-us
- How to create Google account: https://support.google.com/accounts/answer/27441?hl=en
- Google Colaboratory:  https://colab.research.google.com/notebooks/welcome.ipynb"
- Google Drive:  https://www.google.com/drive/