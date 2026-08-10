docs

08/10/2026

  Completed first function used in the tear sheet (BETA)
  Took some time to learn how to properly calculate beta using the tools available in pandas and NumPy because I have very minimal experience with data frames. At first, I was trying to extract values from the ["Close"] column on the data frame and put them into a list so I could work with them in a way I am comfortable with. I quickly realized that is not possible or even worth it because there are methods built into the libraries that I am using to Calculate everything I need. 
  Using the Covariance(.cov()) and Variance(.var()) methods I was quickly able to calculate beta for my example stock of TSLA.
   
   Now my next goals will be to format the beta function to take user input and calculate alpha. 
