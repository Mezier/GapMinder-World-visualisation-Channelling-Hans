# GapMinder-World-visualisation-Channelling-Hans
## Preface 

Information Visualisation is one of important course of my postgraduate study. The reproduce of GapMinder World Visualisation is my final assignment of this course. D3, JavaScript, HTML is the main technology I used in this project. This blog is written for recording the effect of this project, the knowledge I learned in the leaning process, and the solution of some problems. The original [source code]() could be found on my [github]().

Hans Rosling is a data visualisation legend. His 2006 TED talk, the Best Stats you’ve Ever Seen, is one of the most viewed videos on the [TED website]  (http://bit.ly/2doLzAY). An updated interactive version of the GapMinder World 
visualisation used in that demo is [available](www.gapminder.org/tools). 


In this assignment I will create an information visualisations that is an homage to Hans Rosling, which means I will recreate the GapMinder World visualisation using d3.js. A simple demo of the visualisation is reproduced below. I will discuss the specific details on the function Part.

![myGapMinder](http://i64.tinypic.com/sqi7ex.jpg)

The data required to drive this visualisation can be download on official website or created by yourself for practicing. The fields in this file are as follows:

* Country: The country name
* Year: The year for this data observation
* Population: The population of the country in this year
* LifeExp: Average life expectancy in years
* GDP: Average GDP in inflation adjusted dollars
* Code: The country code
* Region: The region in which the country belongs (similar to continent)
* Area: The area of the country in square kilometres
* Coastline: the number of kilometres of coastline belong 

[Jump to Technology ](#build) 



<p id = "build"></p>
---

## Main Functions 


### 1. Every bubble represents one country of the world

The main canvas is a bubble plot. Each bubbles represents a country in your raw data. There are many states in the world, so different color represents different state to have a better visualisation about the plot. Countries of the world described by GDP and Life Expectancy mapped to x and y axis position. The population of each country mapped to bubble area. 


### 2. Ability to view data for a particular year and animate the change from year to year.

This function could be implemented by setInterval and clearInterval function.

<pre><code>
function run(){
   if(i){
   clearInterval(i);
   $("#startButton").val("start");
   i=null;
   }else{				
    i = setInterval(function() {generateVis();}, 700);
    $("#startButton").val("stop");
        }
		}
</pre></code>

### 3. A control which allows the journey of a country to be seen as a trace of positions in the scatter plot in a static visualidation rather than animated.

In this function, we should using transparency to achieve this.
_Pay Attention_: This function could only be implemented when the plot is static.
![trace](http://i66.tinypic.com/11kyt6o.jpg)

### 4. Two extra bar charts which show the number of countries per region and the number of countries with each government type, and they uptate as the year is changed.
In this funciton, we should using two different extra SVG canvas rather than trying to include all visualisations on a single canvas.</br>
_Pay Attention_:The data of bar charts should changed from year to year.

![p1](http://i67.tinypic.com/wlccxz.jpg)

### 5. A checkbox in the right of the bubble chart for choosing specific countries to visualize the bubble chart more directly

If you click the start button to see the changing bubble chart, it’s too many and messy. When choosing the specific country (try to choose countries with big population to have a better insight about the chart), it can reduce the opacity of non-selected countries to mark the selected one. </br>
Hint: When the chart is static, click the bubble, you can only see the selected bubble’s trace while hidden other countries. If you want see all countries again, click the start button in the bottom to animate the bubble chart. 

![checkbox](http://i67.tinypic.com/4ik20m.jpg)

---


## PostScript

This is the main function I have achieved during the assignment. The details and raw data can be found on the source code which is posted in my [github](). 


—— By Mezier 19/01/2018


