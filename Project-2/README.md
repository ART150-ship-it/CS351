# Project #2 Report
|Thread<br>Count|Wall Clock<br>Time|User Time|System Time|Speedup|
|:--:|--:|--:|--:|:--:|
|1|14.44|13.87| 0.47|1.00|
|2|11.15|21.11| 0.67| 1.29|
|3| 5.80|15.59| 0.73| 2.49|
|4| 4.56|15.83| 0.83| 3.17|
|5| 3.97|16.61| 0.98| 3.64|
|6| 3.45|16.53| 1.14| 4.19|
|7| 3.15|17.16| 1.25| 4.58|
|8| 2.87|17.55| 1.31| 5.03|
|16| 2.07|18.96| 2.74| 6.98|
|24| 1.99|19.41| 6.56| 7.26|
|32| 2.07|18.64| 8.76| 6.98|
|40| 1.99|17.69|18.68| 7.26|
|48| 2.00|17.60|17.78| 7.22|
|56| 1.99|17.19|22.42| 7.26|
|64| 1.97|16.67|26.95| 7.33|
|72| 1.96|16.59|26.07| 7.37|
|80| 1.95|16.99|29.21| 7.41|

![Alternate description text](<IMG_0033.HEIC>)

Question 1: I would think that having the most threads does not lead to greater speedup beacuse of you being limited by the amount of data that can be processed. Because that hint makes me think that if you are at the DMV it does not matter if there are 20 or 2 people waiting to be served the workers won't process more people just because there are more people waiting. 

Question 2: I would think that there is no way to get perfect scaling because the system might hang at certain points. 

Question 3:

$$ speedup = \frac{1}{1 - 0.999 + \frac{0.999}{16}} = 0.0634$$

Question 4: 
