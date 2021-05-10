# shiny
this is the first project
mtcarsDf <- client %>%
    mutate(car_name = row.names(client)) %>%
    select(car_name, AGE, pro, com,....)
## the way to use multiple filter in shiny  app
conditional <- function(condition, success) {
    if (condition) success else TRUE
}

reactiveDf <- reactive({
  mtcarsDf %>%
    filter(
      conditional(input$name != "", grepl(input$name, car_name, ignore.case = TRUE)),
      conditional(input$AGE != "", AGE == input$age),
      conditional(input$Pro != "", Pro == input$Pro)
    )
})
