# Basics-in-ggplot2

## Introduction

### Drawing your first plot
load the ggplot2 package
```
library(ggplot2)
```
Explore the mtcars data frame with str()
```
str(mtcars)
```
Execute the following command to create your first plot
```
ggplot(mrcars, aes(cyl, mpg))+
  geom_point()
```
Changing cyl to factor will change how the graph is display. Doing this will only present values that are present within the dataset.
```factor(cyl)```
### Mapping data columns to aesthetics
Edit to add a color aesthetic mapped to disp
```
ggplot(mtcars, aes(wt, mpg, color = disp)) +
  geom_point()
```
Try replacing color with size and see how that affects the plot that you just made. Assigning a variable to color or size will affect how the plot is displayed, assigning/grouping by color or size

### Adding geometrics
Explore the diamonds data frame with str()
```
str(diamonds)
```
Add ```geom_point()``` with ```+```. To add another line to a ggplot command a ```+``` has to go immediatly after the previous line is written, indicating that the command (or plot) is not done being created.
```
ggplot(diamonds, aes(carat, price)) +
  geom_point()
```
The ```geom_point()``` command will create a scatterplot. You can also add ```geom_smooth()``` to add a smooth trend line. Give it a shot by adding it to the plot that you just created.

### Changing one geom or every geom
Map the color aesthetic to clarity
```
ggplot(diamonds, aes(carat, price, color = clarity)) +
  geom_point() +
  geom_smooth()
```
You can change the opacity of the points by adding ```alpha``` into the ```geom_point()``` command.
```
ggplot(diamonds, aes(carat, price, color = clarity)) +
  geom_point(alpha = 0.4) +
  geom_smooth()
```
This has change the opacity of the points by 40%.

### Saving plots as vairables
When creating plots you are able to sae them as variables. By doing this, you can later on call the plot that you already made and add on additional characteristics later on. to do this, name you plot and follow it by a ```<-``` and the remaining code to create the plot.

## Aesthetics

### All about aesthetics: color, shape, and size
These are the aesthetics you can consider within aes() in this chapter: ```x```, ```y```, ```color```, ```fill```, ```size```, ```alpha```, ```labels``` and ```shape```.
### All about aesthetics: color vs. fill
The ```color``` aesthetic changes the outline of a geom and the ```fill``` aesthetic changes the inside. ```geom_point()``` is an exception: you use ```color``` (not ```fill```) for the point color. However, some shapes have special behavior.
The default ```geom_point()``` uses ```shape = 19``` which is a solid circle. An alternative shape ```shape = 21```. This is a circle that allows you to use both ```fill``` for the inside and ```color``` for the outline. 
You can call ```?points()``` for a break down on the types of points.
```
ggplot(mtcars, aes(wt, mpg, fill = fcyl)) +
  geom_point(shape = 1, size = 4)
```
### All about attributes: color, shape, size, and alpha
You can specify colors in R using hex codes: a hash followed by two hexadecimal numbers each for red, green, and blue (```"#RRGGBB"```). Hexadecimal is base-16 counting. You have 0 to 9, and A representing 10 up to F representing 15. Pairs of hexadecimal numbers give you a range from 0 to 255. ```"#000000"``` is "black" (no color), ```"#FFFFFF"``` means "white", and ```"#00FFFF"``` is cyan (mixed green and blue).

### Updating aesthetic labels

