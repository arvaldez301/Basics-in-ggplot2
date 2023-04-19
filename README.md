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
Add geom_point() with +. To add another line to a ggplot command a ```+``` has to go immediatly after the previous line is written, indicating that the command (or plot) is not done being created.
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
