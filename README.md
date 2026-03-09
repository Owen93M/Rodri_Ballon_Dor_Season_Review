# Rodri Ballon D'Or Season Review

# Project Overview
* The idea of this project is to analyse the defensive and attacking attributes of Rodri's Balon D'or winning season, against other players that play in his position from across the different leagues `(EPL, La Liga, Ligue 1, Bundesliga)`.
# Code Overview

### _Imports_
<img width="843" height="472" alt="Image" src="https://github.com/user-attachments/assets/5caf45a5-2ec5-464d-8a1e-60df1788a3b2" />

* I imported all libaries that were needed to manipluate the data and create graphs and charts.
* Using `'set_option()'` function. I displayed specific number of rows and columns.
* Modifiying the layout with `'IPython.display'` and importing `'display'` & `'HTML'` to render HTML content to the workbook.
----------------
### _Opening & Reading File_
<img width="3724" height="607" alt="Image" src="https://github.com/user-attachments/assets/11834c6c-505e-432c-b203-3cba0d581d1f" />

* I created a variable that read and storef the `csv` file using the `read_excel()` function.
* Then showed the DataFrame, while using the `head()` function to only show wanted rows.

### _Shape_
<img width="642" height="114" alt="Image" src="https://github.com/user-attachments/assets/a6d867ef-3bfa-426d-84c7-6641afdbd158" />

* I looked at how many `Columns` & `Rows` in the DataFrame using `shape`.

### _Describe_
<img width="3708" height="573" alt="Image" src="https://github.com/user-attachments/assets/b496daf7-3250-4c21-b88b-a2bc2193ec65" />

* To see the numerical destription of each column on attributes such as  `Count`, `Mean` & `Standard Deviation (STD)` the `describe()` function was used.  

### _Open And Read - Other Leagues_
<img width="3753" height="1584" alt="Image" src="https://github.com/user-attachments/assets/5a04d7b5-a6bd-4ac7-9291-15a660765f73" />

* I used the previous process on all the data files for the other leagues.

 ### _Selecting Players By Positions_
<img width="3725" height="587" alt="Image" src="https://github.com/user-attachments/assets/efc2ece6-14ae-4314-a5d2-9d990d26d37b" />

* Create a variable to store the values. Index the data by `Column` and `Values` of the column.  

### _Combining English Players DataFrames_
<img width="2450" height="578" alt="Image" src="https://github.com/user-attachments/assets/36ea35ae-cd31-49b8-9122-bd1dd0c59722" />

* I placed all the DataFrames created for English players into a variable and changed them into a `list format ([])`
* A variable was created, with pandas `(pd)` and I used `concat` function on the DataFrame made previous to combine and store all the DataFrames.
* I then called DataFrame with selected columns to show the outcome. 

 ### _Combining All DataFrames DataFrames_
<img width="3734" height="376" alt="Image" src="https://github.com/user-attachments/assets/0eb92693-de8d-46db-8e05-5df956fce70c" />

* I repeated process for all the other leagues DataFrames.

 ### _Finding Defensive Mean_
<img width="716" height="227" alt="Image" src="https://github.com/user-attachments/assets/a21b9b4c-be4c-48e1-8459-a70e1ec1195e" />

* Iwanted to know what the `Mean` of all the values were, so in a varaible `(d_mean)` i stored the value from the `mean()` function on the selected column `[Defensive duels per 90]`.
---------------
## Defensive Graphs
### _Defensive Duels Per 90_

<img width="1684" height="1275" alt="Image" src="https://github.com/user-attachments/assets/e7a5acc7-61d6-4991-b64d-78f48d701ca6" />

* I used `figsize` to declare how high and wide the graph should be and then added values into the `()`
* To plot `plt` the figures `x` & `y` axes, i used the `axes()` function.
* I wanted to show the age of each player along with there names, as i think it is important to show what stage of their career these players were. To do this created a variable (`players_age`) to display both the players name and age.
    * I called the column from the DataFrame that stores the player's names `[Player]`.
    * Then i added a space & placed a `+` to connect the following `age` code.
    * Inside a set of `''`, i added another space which was follwed by `\n`, this places the next code on a new line then add another space next to it. After that i next placed a `()`, a set of `''` and 2 more `+`, with spaces around them, and inbetweeen them called the `DataFrame [plyr_dfs]` and `Column ['Age']`.After this i needed to change the data to a `String` using `astype()` function and placed `'str'` in the `()`.
* To plot the bars. I created the variable `bars` and used `plt.bar()`function. Inside the brackets i called the variable created above `players_age`(this is used for the `x-axis`), and next i called the DataFrame and column desired `(plyr_dfs['Defensive duels per 90']`), then i added the bar `color`, which was chosen to be blue.
* I wanted to show the AVG line this attribute. I plotted the line with `plt.axhline`(axis horizontal line) function. Inside the brackets I created a variable for the `y-axis (y)` and assigned it the value from the `d_mean` variable previously made. I then styled the line with `color`, `linestyle`(dotted / dashed) and the `linewidth` (by numerical value).
* I wanted to highlight specific columns (Rodri, the highest & lowest player) to do this :
   * I created new variable `mrk_plyr`,this is to highlight Rodri's values, i then follow it up with the numberical value that the bar appears on the graph `(3)`. After i useed the `bar` variable from above and placed the selected column `mrk_plyr` in `[]`, used the `set_color()` function and added the color in the brackets `(gold)`.
   * This was then repeated for the lowest and the highest players to highlight the gap.
 * I then wanted to show the value on each bar to make it clearer how far the distance was between each other. I did this by calling the `ax` variable and used the `.barlabel()` function. In this i called:
   * The `bars` variable that was previously made to select each bar.
   * I then used `fmt` (format) variable. Then in `''`, I wrote `%.1f`. This set value to 1 decimal place.
   * I positioned the values at the edge of each bar with `label_type='edge'`.
   * The values were then styled with `fontweight='bold` to make the text stand out, `color='black'` and `fontsize=14`.
 * I then added X & Y labels and a title using the `plt.xlabel()`, `plt.ylabel()` & `plt.title()` function, then added text in `' '`, followed by stylings of `fontsize` and `fontweight`
 * The x-axis labels needed rotating to fit properly so i used the `plt.xticks()` function and added `rotation=45` and `ha='center'` (Horizontal Alignment) inside the `()`.
 * I wanted the background the highlight the bars more so i used `plt.gca()`(Get Current Axes) followed by `.set_facecolor('')` function to set the background color ('lightslategrey')
 * Finally i used `plt.show()` to display the figure.

<img width="871" height="707" alt="Image" src="https://github.com/user-attachments/assets/e735939a-4ab5-42f4-893c-33c6d8d60784" />

1. (Text)
....* (Text)
### _Defensive Duels Won_

*  (Text)

<img width="1369" height="1062" alt="Image" src="https://github.com/user-attachments/assets/b7278ed5-b54c-42f6-975c-866c052c61a8" />

1. (Text)
....* (Text)
### _Interceptions Per 90_

*  (Text)

<img width="1460" height="926" alt="Image" src="https://github.com/user-attachments/assets/8d2a3ef0-b0d2-4df5-b835-94c4f46cf515" />

1. (Text)
....* (Text)

----------------
## Attacking Graphs
### _Using sum() On Column To Find Each Players Value_

<img width="655" height="498" alt="Image" src="https://github.com/user-attachments/assets/0452e48e-42ff-4af1-b719-68c2a802e211" />

### _Shot Per 90_

<img width="1523" height="942" alt="Image" src="https://github.com/user-attachments/assets/9cd644c5-9a47-4dab-b917-0e91813ed165" />

1. (Text)
....* (Text)
### _Shots On Target Per 90_

<img width="1483" height="1279" alt="Image" src="https://github.com/user-attachments/assets/0e58cd3f-c058-4ad0-8492-f9b776d6fa82" />

1. (Text)
....* (Text)
### _Goal Conversion_

<img width="1523" height="343" alt="Image" src="https://github.com/user-attachments/assets/9a312a8c-92b6-40bc-bd7a-6c365e1c3987" />

*  (Text)

<img width="1609" height="1442" alt="Image" src="https://github.com/user-attachments/assets/ad142d2c-9ab0-4e5b-b554-43f43098f707" />

1. (Text)
....* (Text)
### _Players Passing Accuracy_

<img width="1468" height="1303" alt="Image" src="https://github.com/user-attachments/assets/a2255408-89d1-4795-bd10-eab2c718cad1" />

*  (Text)

<img width="1713" height="1217" alt="Image" src="https://github.com/user-attachments/assets/2a085c5b-c0ff-4491-8909-894c92023ea4" />

1. (Text)
....* (Text)
----------------

### _Recieved Passes Per 90 (Avg)_

<img width="982" height="844" alt="Image" src="https://github.com/user-attachments/assets/f1657cd7-83c5-45f3-a7ff-a807c3fde035" />

*  (Text)

<img width="1332" height="1141" alt="Image" src="https://github.com/user-attachments/assets/950ee421-4c6c-415f-bd59-dc598977c958" />

1. (Text)
....* (Text)

------------

### _Pizza Graph - All Defensive KPI's_

<img width="1540" height="1760" alt="Image" src="https://github.com/user-attachments/assets/8f659072-afb2-4350-b7eb-5bc4f5dc61b9" />

*  (Text)

<img width="976" height="1059" alt="Image" src="https://github.com/user-attachments/assets/b0596911-4894-4490-9cc7-69604a687d09" />

1. (Text)
....* (Text)
   
### _Total Season KPI;s_

<img width="1090" height="1745" alt="Image" src="https://github.com/user-attachments/assets/77020db6-8749-4fd2-a35b-4aa80686c09f" />

*  (Text)

<img width="1586" height="1720" alt="Image" src="https://github.com/user-attachments/assets/12dbf07c-ade9-4553-9e5d-213bc324f0cd" />

1. (Text)
....* (Text)
### _Using f-string To Show Each KPI's Value_

<img width="946" height="804" alt="Image" src="https://github.com/user-attachments/assets/3679c15d-338c-4c2d-93a6-813b01ada0fe" />

### _Total Season KPI's Against AVG Of All Competitors_

<img width="1106" height="1763" alt="Image" src="https://github.com/user-attachments/assets/f93f2fc5-7d5a-4eb2-baaf-891c5467be0f" />

*  (Text)

<img width="1523" height="1560" alt="Image" src="https://github.com/user-attachments/assets/e944d98c-500c-4aa5-b12c-b86caabb6614" />

1. (Text)
....* (Text)
