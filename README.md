# shiny.slider

An answer to a stackoverflow question: https://stackoverflow.com/questions/53881741/swipe-effect-for-images-in-shiny-r.

![Slidy_Polars](ezgif-2-c608fe83aa14.gif)

Usage: run app.R

or

```

# runApp("C:/R/shiny.slider/R")
library(shiny)

ui <- fluidPage(
  
  tags$script(src = "jquery-1.6.1.min.js"),
  tags$script(src = "jquery-ui-1.8.13.custom.min.js"),
  tags$script(src = "jquery.beforeafter-1.4.min.js"),
  
  tags$script("
            $(function() {
                $('#slider').beforeAfter({
                    introDelay: 2000,
                    imagePath: 'img/',
                    introDuration: 500,
                    showFullLinks: false
                })
              });
  "),
  
  mainPanel(
    
    tags$div(
      id = "slider",
      img(
        src = "img/Polar-Bear-SliderTest1.jpg", 
        width = 800, 
        height = 533
      ),
      
      img(
        src = "img/Polar-Bear-SliderTest2.jpg", 
        width = 800, 
        height = 533
      )
    )
  )
  
)

server <- function(input, output, session){}

shinyApp(ui, server)

```

(This project is part of my life long application to RStudio :))
