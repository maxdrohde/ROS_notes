# Preface

## What is Shiny?

If you've never used Shiny before, welcome!
Shiny is an R package that allows you to easily create rich, interactive web apps.
Shiny allows you to take your work in R and expose it via a web browser so that anyone can use it.
Shiny makes you look awesome by making it easy to produce polished web apps with a minimum amount of pain.

In the past, creating web apps was hard for most R users because:

-   You need a deep knowledge of web technologies like HTML, CSS and JavaScript.

-   Making complex interactive apps requires careful analysis of interaction flows to make sure that when an input changes, only the related outputs are updated.

Shiny makes it significantly easier for the R programmer to create web apps by:

-   Providing a carefully curated set of user interface (**UI** for short) functions that generate the HTML, CSS, and JavaScript needed for common tasks.
    This means that you don't need to know the details of HTML/CSS/JS until you want to go beyond the basics that Shiny provides for you.

-   Introducing a new style of programming called **reactive programming** which automatically tracks the dependencies of a code chunk.
    This means that whenever an input changes, Shiny can automatically figure out how to do the smallest amount of work to update all the related outputs.

People use Shiny to:

-   Create dashboards that track important performance indicators, and facilitate drill down into surprising results.

-   Replace hundreds of pages of PDFs with interactive apps that allow the user to jump to the exact slice of the results that they care about.

-   Communicate complex models to a non-technical audience with informative visualisations and interactive sensitivity analysis.

-   Provide self-service data analysis for common workflows such as replacing email requests with a Shiny app that allows people to upload their own data and perform standard analyses.

-   Create interactive demos for teaching statistics and data science concepts that allow learners to tweak inputs and observe the downstream effects of those changes in an analysis.

-   Leverage automation processes by making them usable by users with no programming skills.

-   Create prototypes of web applications, as the development in R is often much faster but difficult to scale.

In short, Shiny gives you the ability to pass on some of your R superpowers to anyone who can use the web.

## Who should read this book?

This book is aimed at two main audiences:

-   R users who are interested in learning about Shiny in order to turn their analyses into interactive web apps.
    To get the most out of this book, you should be comfortable using R to do data analysis, and should have written at least a few functions.

-   Existing Shiny users who want to improve their knowledge of the theory underlying Shiny in order to write higher-quality apps faster and more easily.
    You should find this book particularly helpful if your apps are starting to get bigger and you're starting to have problems managing the complexity.

## What will you learn?

The book is divided into five parts:

1.  In "Getting started", you'll learn the basics of Shiny so you can get up and running as quickly as possible.
    You'll learn about the basics of app structure, useful UI components, and the foundations of reactive programming.

2.  "Shiny in action" builds on the basics to help you solve common problems including giving feedback to the user, uploading and downloading data, generating UI with code, reducing code duplication, and using Shiny to program the tidyverse.

3.  In "Mastering reactivity", you'll go deep into the theory and practice of reactive programming, the programming paradigm that underlies Shiny.
    If you're an existing Shiny user, you'll get the most value out of this chapter as it will give you a solid theoretical underpinning that will allow you to create new tools specifically tailored for your problems.

4.  Finally, in "Best practices" we'll finish up with a survey of useful techniques for making your Shiny apps work well in production.
    You'll learn how to decompose complex apps into functions and modules, how to use packages to organise your code, how to test your code to ensure it's correct, and how to measure and improve performance.

## What won't you learn?

The focus of this book is making effective Shiny apps and understanding the underlying theory of reactivity.
I'll do my best to showcase best practices for data science, R programming, and software engineering, but you'll need other references to master these important skills.
If you enjoy my writing in this book, you might enjoy my other books on these topics: [R for Data Science](http://r4ds.had.co.nz/), [Advanced R](http://adv-r.hadley.nz/), and [R packages](http://r-pkgs.org/).

There are also a number of important topics specific to Shiny that I don't cover:

-   This book only covers the built-in user interface toolkit.
    There are a number of other packages that provide alternative front ends like [shinydashboard](https://rstudio.github.io/shinydashboard/), [shinymaterial](https://ericrayanderson.github.io/shinymaterial/), [shiny.semantic](https://appsilon.github.io/shiny.semantic/), or the collection of packages by [RinterRface](https://github.com/RinteRface).
    Nan Xiao maintains a list of many extensions at <https://github.com/nanxstats/awesome-shiny-extensions>.

-   Deployment of Shiny apps.
    Putting Shiny "into production" is outside the scope of this book because it hugely varies from company to company, and much of it is unrelated to R (the majority of challenges tend to be cultural or organisational, not technical).
    If you're new to Shiny in production, I recommend by starting with Joe Cheng's 2019 rstudio::conf keynote: <https://rstudio.com/resources/rstudioconf-2019/shiny-in-production-principles-practices-and-tools/>.
    That will give you the lay of the land, discussing broadly what putting Shiny into production entails and how to overcome some of the challenges that you're likely to face.
    Once you've done that, see [the Shiny website](https://shiny.rstudio.com/articles/#deployment) for more details of specific deployment scenarios.
