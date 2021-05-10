# shiny
this is the first project
## the way to use multiple filter in shiny  app
conditional <- function(condition, success) {
    if (condition) success else TRUE
}

reactiveDf <- reactive({
  mtcarsDf %>%
    filter(
      conditional(input$name != "", grepl(input$name, car_name, ignore.case = TRUE)),
      conditional(input$gear != "", gear == input$gear),
      conditional(input$cyl != "", cyl == input$cyl)
    )
})
