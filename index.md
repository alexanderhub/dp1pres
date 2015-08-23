---
title       : Girth or Height by Volume for Black Cherry Trees
subtitle    : Because your boss always wanted to know that, right?
author      : Alexander Dolinin
job         : for Coursera's class project
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---


## Slide 1

Imagine you're working for US Forest Service, and your boss wants a "dashboard" about Black Cherry Trees, perhaps because that's what his boss is asking. No actual business questions are asked, he "just needs a dashboard". What do you do?

Hint - see next slide.

--- .class #id 


## Slide 2

Solution to your headache - you create a very usefull application to calculate the ratio of volume of the trees by either their height or girth. Because it sounds very impressive and will get your boss off your back.

--- .class #id 


## Slide 3

You can see a sample of such application at https://esherpadotnet.shinyapps.io/DDPproject1 

--- .class #id 


## Slide 4

Example of the code it runs, to make Coursera happy :)

```r
library(shiny)
# Relys on the 'trees' dataset in the datasets package (which generally comes preloaded).
library(datasets)

# Define a server for the Shiny app
shinyServer(function(input, output) {       
        # Fill in the spot we created for a plot
        output$myPlot <- renderPlot({              
                # Render a barplot
                barplot(trees[,input$options_selector] / trees$Volume, #dataset and calcualtions here 
                        main=c(input$options_selector, " by Volume"),
                        ylab="Y",
                        xlab="X")
        })
})
```

--- .class #id 


## Slide 5

Conclusion - your boss is happy, impressed by your mad skills and you get a raise.

--- .class #id
