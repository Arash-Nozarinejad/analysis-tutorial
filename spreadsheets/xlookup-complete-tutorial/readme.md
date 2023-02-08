# XLOOKUP Complete Beginner to Advanced Tutorial

## Introduction
Lookup functions in spreadsheets allow users to find items in a range based on a criterion they provide. XLOOKUP is the new Microsoft Excel lookup function that has almost complete replaced VLOOKUP, HLOOKUP, and the INDEX/MATCH. 
XLOOKUP is part of the advanced Excel functions called dynamic arrays functions.

XLOOKUP has a number of benefits such as:

* XLOOKUP needs only 3 arguments in most cases.
* It works vertically and horizontally (as opposed to VLOOKUP/HLOOKUP).
* It's a single function (as opposed to INDEX/MATH).
* It can return custom results when no match is found, without needing to use additional functions
* And much more.

You can also read our article on XLOOKUP by [clicking here](https://www.analysistutorial.com/xlookup-complete-tutorial)
And you can watch our Youtube video on XLOOKUP by clicking here (*Youtube link pending*).
We have also provided the Excel file for you to download and test out.

## Syntax
>If you are brand new to XLOOKUP take a quick look at the syntax table, but quickly move onto the examples section of the page and don't get bogged down on the definitions and just replicate the examples provided.

The XLOOKUP function searches a range or an array, and then returns the item corresponding to the first match it finds. If no match exists, then XLOOKUP can return the closest (approximate) match. 
```
=XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found], [match_mode], [search_mode])
````
Argument|Description
-----|-----
**lookup_value**<br />Required* | The value to search for<br />*If omitted. The XLOOKUP returns blank cells it finds in<br />lookup_array
**lookup_array**<br />Required |The array or range to search
**Return_array**<br />Required |The array or range to return
[if_not_found]<br />Optional |If a valid match is not found, return the [if_not_found] text you supply.<br />If a valid match is not found, and [if_not_found] is missing, #N/A is returned.
[match_mode]<br />Optional|Specify the match type: <br />0 - Exact match. If none found, return #N/A. This is the default.  <br />-1 - Exact match. If none found, return the next smaller item. * <br />1 - Exact match. If none found, return the next larget item. <br />2 - A wildcard match.
[search_mode] <br />Optional|Specify the search mode to use: <br />1 - Perform a search starting at the first item - This is the default. <br />-1 - Perform a reverse search starting at the last item. <br />2 - Perform a binary search that relies on lookup_array being sorted in ascending order. If not sorted, invalid results will be returned. <br />-2 - Perform a binary search that relies on lookup_array being sorted in descending order. If not sorted, invalid results will be returned.

## Real life examples
We'll be using a subset of 2015 World Happiness index data.

![dataset]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/01_dataset.png?w=912&ssl=1)
### Example 1 - Vertical Lookup
We'll start by using only the required arguments: lookup_value, lookup_array, and return_array to find the happiness score of the country of Belgium. This is an example of a vertical lookup using XLOOKUP.

![example01_formula]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/02_example_1_formula.png?resize=1080%2C420&ssl=1)
```
=XLOOKUP(H2, A2:A20, D2:D20)
```
Here we have used the value in cell H2 as our lookup_value (Belgium). We have then selected the range of A2:A20 as our lookup_array and the range D2:D20 as our return array.
XLOOKUP will look for the first instance of Belgium (H2) in the column of countries (A2:A20). Here Belgium is the 19th country. XLOOKUP will then return the 19th value in the Happiness Score column (D2:D20).

### Example 2 - Horizontal Lookup
For this example, we will temporarily use a subset of our data arranged in a horizontal way for the purpose of demonstration

![example02_dataset]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/03_example_2_dataset.png?resize=1080%2C62&ssl=1)

Now if we want to select the happiness score of the country of Belgium, we'll use the following formula:

![example02_formula]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/04_example_2_formula.png?resize=1080%2C100&ssl=1)
```
=XLOOKUP(J2, B1:H1, B3:H3)
```
Here we have used the value in cell J2 as our lookup_value (Belgium). We have then selected the range of B1:H1 as our lookup_array and the range B3:H3 as our return array.
XLOOKUP will look for the first instance of Belgium (J2) in the countries row (B1:H1). In our example Belgium is in the H column. So XLOOKUP will return the H value of the Happiness Score row (B3:H3).

### Example 3 - if_not_found argument
We'll now introduce our first optional argument: if_not_found.

The if_not_found argument is a text that will be returned if a matching lookup_value could not be found in the lookup_array.
Let's say we want to find the happiness of score of the country of United Kingdom from our table. If we use the arguments from example 1, we'll get the following result

![example03_na]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/05.png?resize=1080%2C381&ssl=1)
```
=XLOOKUP(H2, A2:A20, D2:D20)
```
But what if we want to provide a more descriptive result in case a value is missing from the table? Like for example we want the message of "Country not found" to be shown. To do this we can use the if_not_found argument. 

![example03_formula]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/06_example_3_formula.png?resize=1080%2C382&ssl=1)
```
=XLOOKUP(H2, D2:D20, A2:A20, "Country not found")
```
Here XLOOKUP will look for United Kingdom (H2) in the Country column (A2:A20), and since United Kingdom is missing the message "Country not found" will be returned.

### Example 4 - match_mode
Next in our list of optional arguments is: match_mode.

When XLOOKUP can't find the lookup_value in the lookup_array, it will either return N/A or the if_not_found arugment if the argument is provided to the formula. But with match_mode you can find the closest value to the lookup_value if the lookup_value is missing. We'll explore this concept now with an example.

Let's say given our data table you're looking for a country with the happiness score of 6. If you use the argument from example 1, you'll get N/A.

![example04_na]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/07_example_4_na.png?resize=1080%2C403&ssl=1)
```
=XLOOKUP(H2, D2:D20, A2:A20)
```
Or if you use the if_not_found argument in as well like example 3, you'll get "Score not found".

![example04_ifnotfound]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/08_example_4_ifnotfoud.png?resize=1080%2C402&ssl=1)
```
=XLOOKUP(H2, D2:D20, A2:A20, "Score not found")
```
But if you provide the match_mode argument (for example 1), you'll get Belgium.

![example04_formula]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/ccpy.png?resize=1080%2C403&ssl=1)
```
=XLOOKUP(H2, A2:A20, D2:D20, "Score not found", 1)
```
Here the XLOOKUP will look for a score of 6 (H2) in the Happiness Score column (D2:D20) but cannot find it. Since we have set the match_mode to 1 (1 means next largest item if an exact match is not found), XLOOKUP will look for next value in the Happiness Score column (D2:D20) that is greater than 6 (H2) and finds the cell D20 which is the 19th item in the lookup_array. Next, XLOOKUP will return the 19th element in the return_array (A2:A20) which is Belgium.

To refresh your memory, there are 4 arguments for match_mode:
* 0 - which means an exact match. And if an exact match is not found, N/A or if_not_found argument is returned.
* 1 - means in case an exact match is not found, the next largest item is returned.
* -1 - means in case an exact match is not found, the next smallest item is returned.
* 2 - mean a wild card match.

### Example 5 - search_mode
The last optional argument is: search_mode.
The search_mode argument specifies how will XLOOKUP search the lookup_array. The arguments for search_mode are the following:
* 1 - XLOOKUP performs a search starting at the first item - This is the default.
* -1 - XLOOKUP performs a reverse search starting at the last item.
* 2 - XLOOKUP performs a binary search that relies on lookup_array being sorted in ascending order. If not sorted, invalid results will be returned.
* -1 - XLOOKUP performs a binary search that relies on lookup_array being sorted in descending order. If not sorted, invalid results will be returned.

Let's say you wanted to find out which Latin American country in our data is the least happy country based on the Happiness Score. You'll write the following:

![example05_formula]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/ccpy.png?resize=1080%2C403&ssl=1)
```
=XLOOKUP(H2, B2:B20, A2:A20, "Region not found", 1, -1)
```
Here XLOOKUP will search for the first instance of Latin America and Caribbean (H2) in the Region column (B2:B20) starting from the bottom. Which is the 5th item from the bottom. Next XLOOKUP will return the 5th item from the bottom in the Country column (A2:A20) which is Brazil.

## Tips & Tricks
XLOOKUP is a powerful yet simple function and there are numerous ways to utilize its potential. Here, we'll teach you three simple tips & tricks to master XLOOKUP.

### Tips & Tricks #1 - Returning multiple Values
XLOOKUP can return multiple values across multiple rows and columns. There are two ways to achieve this:
#### 1 - By using range operator " : "
![tips&tricks01_rangeoperator]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/11_tripstricks_1_rangeoperator.png?resize=1080%2C355&ssl=1)
```
=XLOOKUP(H2, A2:A20,B2:B20:C2:C20)
```
Here XLOOKUP will first look for Iceland (H2) in the Country column (A2:A20) which is the 2nd item in the Country column, next XLOOKUP will look for the 2nd items in the Region column (B2:B20) and the Happiness Rank column (C2:C20) and returns them in two separate columns. By using the range operator between the two column ranges B2:B20 and C2:C20 or by using the range operator like this:
```
=XLOOKUP(H2, A2:A20,B2:C20)
```
Note that using the range operator method the results are from columns that are next to each other. To return items from multiple columns that are not next to each other we have to use the concatenate operator.
##### 2 - By using string concatenate operator " & "

![tips&tricks01_concatenate01]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/12_tripstricks_1_concatenate_1.png?resize=1080%2C355&ssl=1)
```
=XLOOKUP(H2, A2:A20,B2:B20&D2:D20)
```
Again, XLOOKUP will first look for Iceland (H2) in the Country column (A2:A20) which is the 2nd item in the Country column, next XLOOKUP will look for the 2nd items in the Region column (B2:B20) and the Happiness Score column (D2:D20) but this time the results of these ranges are concatenated together and returned in a single column together. You can also make the result more readable by concatenating another string (for example ", ").

![tips&tricks01_concatenate02]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/13_tripstricks_1_concatenate_2.png?resize=1080%2C355&ssl=1)
```
=XLOOKUP(H2, A2:A20,B2:B20&", "&D2:D20)
```
### Tips & Tricks #2 - Using multiple inputs
For this trick we'll first introduce an extra column to our table."GDP per Capita Rounded This column is the GDP per Capita column but rounded to 2 decimal places so that multiple countries would have similar GDP for the purpose of demonstration.

![tips&tricks02_data]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/14_tipstricks_2_data.png?resize=1080%2C391&ssl=1)

XLOOKUP accepts multiple inputs and can assess them across multiple columns.

![tips&tricks02_formula]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/15_tipstricks_2_formula.png?resize=1080%2C311&ssl=1)
```
=XLOOKUP(I2&J2, B2:B20&E2:E20, A2:A20)
```
Here, for lookup_value we have concatenated Region (I2) and GDP (J2). And for lookup_array, we have concatenated Region column (B2:B20) and GDP per Capita Rounded column (E2:E20). XLOOKUP will look the Western Europe in Region column and 1.46 in GDP per Capita Rounded column which is the 4th row. Next from our return_array which is set to Country column (A2:A20) XLOOKUP will return the 4th item, and that is Norway.

### Tips & Tricks #3 - Using a nested XLOOKUP
If you know how to write proper nested XLOOKUP, you have mastered this dynamic array function. Nested XLOOKUP is often used to dynamically select a column and return a single important data point. For example: Let's say you want to know the Region of the country of Mexico, you can write a simple XLOOKUP and get the results you want. However, what if you now change your mind and want to see the happiness rank of Mexico? You can either change your XLOOKUP or write a new XLOOKUP. Or, you can write a nested XLOOKUP to dynamically change the criteria you're looking for. This way you don't need to change your arguments or write a new XLOOKUP. Let's see this concept in action:

![tips&tricks03_formula]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/16_tripstricks_3_formula.png?resize=1080%2C308&ssl=1)
```
=XLOOKUP(H2,A2:A20,XLOOKUP(I2,B1:F1,B2:F20))
```
To better understand what is going on let's break down our formula step by step. We have two XLOOKUPs, an outer XLOOKUP, and an inner XLOOKUP. We have to start with the inner XLOOKUP

![ tips&tricks03_innerxlookup]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/17_tipstricks_3_innerxlookup.PNG.png?w=345&ssl=1)

Here Happiness Score (J2) is our lookup_value and our column headers (B2:F2) are our look_array, our entire table aside from the Country column is our return_array (B2:F20). Happiness Score is the 3rd item in the column headers, XLOOKUP will then return the 3rd column from the return_array, which consists of all the happiness scores of all the countries.
Next Let's take a look again at the outer XLOOKUP and explain what is going on.

![ tips&tricks03_outerxlookup]( https://i0.wp.com/analysistutorial.com/wp-content/uploads/2023/02/18_tipstricks_3_outerxlookup.PNG.png?w=345&ssl=1)

Here XLOOKUP will search for Mexico (I2) in the Country column (A2:A20). Mexico is the 14th country in lookup_array. XLOOKUP will then return the 14th item from the result of inner XLOOKUP which was a list of happiness scores of all the countries. 

Now if we change Happiness Score (J2) to "Region" or any other column name, XLOOKUP will return the correct result every time. We can even keep Happiness Score and change the country. Nested XLOOKUP gives analysts so much more flexibility with very little effort.

## Farewell
Thank you for reading this Github article on XLOOKUP. Creating this tutorial project was very fun and I hope you enjoyed reading it as much as I enjoy creating it.

You can visit our website for more tutorials, guides, case studies, and more by [clicking here](https://www.analysistutorial.com/).

Farewell.
