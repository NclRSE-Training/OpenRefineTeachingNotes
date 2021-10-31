## Find Reversed Author Names

In this exercise we are going to use the Boolean data type. If you look at the Authors column, you can see that most of the author names are written in the natural order. However, a few have been reversed to put the family name first.

We can do a crude test for reversed author names by looking for those that contain a comma:

1. Make sure you have already split the author names into individual cells using Edit cells->Split multi-valued cells (you should have done this in exercise 5)
1. On the Authors column, use the dropdown menu and select Facet->Custom text facet...
1. The Custom text facet function allows you to write GREL functions to create a facet
1. In the Expression box type value.contains(",").toString()
    - Click OK
    - Since the ‘contains’ function outputs a Boolean value, you should see a facet that contains ‘false’ and ‘true’. These represent the outcome of the expression, i.e. true = values containing a comma; false = values not containing a comma
    - In order to change the names to natural order, see the Arrays lesson.

[Episode 10 Key Points](episode10_kp.md)
