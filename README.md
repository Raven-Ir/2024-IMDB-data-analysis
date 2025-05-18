## IMDB ANALYSIS

### Case Study

A film studio has a limited budget and can only invest to put one more movie this year. Not being sure on which genre to choose, they asked from you on some objective metrics on which movies make the biggest revenue with the budget that they are willing to invest.

### Hypothesis: 

#### More engaging movies like action and comedies are more appealing to the audience. When it comes between the two the comedies need less budget to create a bigger revenue.

Therefore, the best direction without taking into account matters from other sectors like the quality of the movie, the trailer that will draw the viewers and the overall investment into promoting the movie, would be to go with the comedy script.

#### Movies loved by the people -therefore highest rating- will bring more revenue, but will require a significantly higher budget. Movies within the 6.5 - 7.5 rating bracket will be the best value to expense metric.


After filtering out the NaN values and the 0 values, we are now going to seperate the dataframe into three categories of entries.

Top Grossing: The first 20.
Middle Grossing: Entries 55-65.
Lowest Grossing: Entries 83-103.

This way we will locate the most popular genres based on their Profit.

### Conclusions

After the first iteration of the top_genres method for the successfull movies we got the top three genres as the following

Adventure           15

Action              10

Comedy               9

Sci-Fi               9

Fantasy              9

Since Comedy, Sci-Fi and Fantasy had the same frequency I decided to add all of them.

After the second iteration of the top_genres method for the moderetaly successfull movies we got the top three genres as the following

Drama                9

Thriller             7

Horror               5

And last but not least, for less successfull movies, the top genres were the following: 

Action              12

Thriller            10

Drama                7

From the above results we can see that the Thriller genre appears to both moderate and low success films. With that in mind we can draw the conclusion, that producing a film withing the thriller genre is a very risky decision, as the probability of it succeding is very low.

Our first hypothesis -based on our sample- is already proved partially true. Producing an action film can be a risky decision. While we find it in the "Sucessful" category, the frequency that is found in the "Not Successful" movies is higher. Whereas, the "Comedy" genre appear only in high percentage frequency in the "Successful" category. Disregarding the factor of the budget, already we can conclude that the chances of a comedy movie creates a higher revenue.

To test the second hypothesis, we will calculate the mean value for each of three above mentioned dataframes that we created. While it is a more conservative way, it is beneficial for the company to be aware budget wise. The highest and the lowest value will also be considered, while the median will be mentioned as well.


### LIMITATIONS:

This project is a imaginery case study, were the budget of the Film Studio is not declared. The entry pool is poor due to the fact that we check only 103 movies, due to the fact that the ideal data are non existant.

### Problems faced:

Changed data.query to data.loc because data.query is not producing a new dataframe as it was needed, whereas data.loc perfoms the modifications in-place.

    filtered_data = data.query('Cleaned_Revenue > 0')
    filtered_data["Profit"] = filtered_data["Revenue"] - filtered_data["Budget"]

The two above lines were converted into one line of code

    data.loc[(data['Budget'] > 0) & (data['Revenue']>0), 'Profit'] = data['Revenue'] - data['Budget']

making it more readable and scalable. We avoided an extra memory alocation by not creating a new copy of the dataframe which was needed, if the "query" was used.

##### Dataset used:
https://www.kaggle.com/datasets/sanadalali/imdb-2024-movies-and-tv-shows

#### Tools used:
- Power BI
- VS code
- Python
- Pandas Library
