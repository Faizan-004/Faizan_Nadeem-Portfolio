docs

08/10/2026

  Completed first function used in the tear sheet (BETA)
  Took some time to learn how to properly calculate beta using the tools available in pandas and NumPy because I have very minimal experience with data frames. At first, I was trying to extract values from the ["Close"] column on the data frame and put them into a list so I could work with them in a way I am comfortable with. I quickly realized that is not possible or even worth it because there are methods built into the libraries that I am using to Calculate everything I need. 
  Using the Covariance(.cov()) and Variance(.var()) methods I was quickly able to calculate beta for my example stock of TSLA.
   
   Now my next goals will be to format the beta function to take user input and calculate alpha. 


8/11/2026

  Completed first iteration of calculate_alpha function.
  This function took a little bit of time to get down because of my unfamiliarity with stocks and financial analysis. To calculate Alpha there are 4 things required. The returns of the portfolio, returns of the market, beta of portfolio, and the Risk Free Rate. The beta was the easy part because i had finished that previously, but where i got tripped up was with the Risk Free Rate. The Risk Free Rate is based on the concept of a 0 risk return, the closest thing to that is government backed bonds such as with the US Treasury. While researching I was made aware that there are two tickers that are relevant for this application: ^TNX and ^IRX. TNX models the long term and IRX models the short term. Where I got confused was with how and when to use this. After some trial and error i realized that i would have to calculate the return in a similar way to the portfolio and market returns, BUT, IRX and TNX are actually already showing precent values in the ticker. So when calculating i dont have to adjust the return value into percent form. also I learned that for shorter periods such as 1 year, although IRX tracks the 13 week it is still the most relevent one to use because using the 10 year ticker would be like comparing current economical conditions to those from a decade ago. Calculating the returns was simple as I just took the oldest and newest values in the time period and turned it into a percent change. using all of these i calculate alpha finally. This is the main metric that users will look at to determine the success of their portfolio.

  Next will work on calculating the Sharpe ratio.


8/18/26  
Shapre ratio has been properly implemented after much trial and error. i had to go back through all pervious functions and refactor code as I calculated things differently for each function, now they all return compatible units that i can use in new functions. my next goal is to make the sortino ratio function but before that i have identified a problem that will effect the program as it gets larger. I realized that the way i am currently handling the user's portfolio is by taking the same of the stock and then passing it into the function. this is actually very wrong as it causes me to have to call yf.Ticker(stock) and stock.history on each function. the solution i will use is to create another function that takes the plaintext of the stock and then returns the data frame from yf.Ticker().history. This is because when i call history it makes a API call and attempts to connect to the internet, i have to limit the amount of times i call this and make the history available to all functions.
