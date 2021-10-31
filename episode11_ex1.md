## Reverse author names

You may already have done the boolean exercise and have a facet containing the names in natural order. In this case, select the ‘true’ facet and start with the step **“1. On the ```Authors``` column use…“**

In this exercise we are going to use both the Boolean and Array data types. If you look at the Authors column, you can see that most of the author names are written in the natural order. However, a few have been reversed to put the family name first.

We can do a crude test for reversed author names by looking for those that contain a comma:

1. Make sure you have already split the author names into individual cells using ```Edit cells->Split multi-valued cells``` (you should have done this in the Clustering lesson)
1. On the Authors column, use the dropdown menu and select ```Facet->Custom text facet...```
1. The ```Custom text``` facet function allows you to write GREL functions to create a facet
1. In the Expression box type ```value.contains(",").toString()```
1. Click ```OK```
1. Since the ```contains``` function outputs a Boolean value, you should see a facet that contains ‘false’ and ‘true’. These represent the outcome of the expression, i.e. true = values containing a comma; false = values not containing a comma
1. In this facet select ‘true’ to narrow down to the author names that contain a comma

Now we have narrowed down to the lines with a comma in a name, we can use the ```match``` function. The match function allows you to use regular expressions, and output the capture groups as an array, which you can then manipulate.

1. On the ```Authors``` column use the dropdown menu and select ```Edit cells->Transform```
1. In the Expression box type ```value.match(/(.*),(.*)/)``` The /, means you are using a regular expression inside a GREL expression. The parentheses indicate you are going to match a group of characters. The ```.*``` expression will match any character(s) appearing 0, 1 or more times. So here we are matching any number of characters, a comma, and another set of any number of characters.
1. See how this creates an array with two members in each row in the Preview column

To get the author name in the natural order you can reverse the array and join it back together with a space to create the string you need:

1. In the Expression box, add to the existing expression until it reads ```value.match(/(.*),(.*)/).reverse().join(" ")```
1. In the Preview view you should be able see this has reversed the array, and joined it back into a string
    - Click ```OK```

[Episode 11 Key Points](episode11_kp.md)
