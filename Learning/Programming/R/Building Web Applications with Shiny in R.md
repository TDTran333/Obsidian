---
aliases: Shiny
tags: R, shiny
---

# Building Web Applications with Shiny in R
## Introduction to Shiny
#### What is a web app?
* Updates based on user input / interaction
* Made up of UI & server

Most web application consist of two parts. The client contains the user interface, that is, buttons and selectors and text boxes and other things that the user can interact with. The server (or backend) is where computation happens, including things like manipulating data and running models.

#### What is Shiny?
Shiny is a R package that allows to make web applications with R.

#### Parts of a Shiny app
* Load shiny
* Create the UI with a HTML function
* Define a custom function to create the server
* Run the app

```R
ui <- fluidPage(
	titlePanel("Baby Name Explorer"),
	sidebarLayout(
 		sidebarPanel(textInput('name', 'Enter Name', 'David')),
		mainPanel(plotOutput('trend'))
 	)
)

server <- function(input, output, session) {
	output$trend <- renderPlot({
		ggplot(subset(babynames, name == input$name)) +
 		geom\_line(aes(year, prop, color = sex))
 		})
}

shinyApp(ui = ui, server = server)
```

##### textInput()
Create an input control for entry of unstructured text values.

##### textOutput()
Render a reactive output variable as text within an application page. textOutput() is usually paired with renderText() and puts regular text in \<div> or \<span>.
	
##### renderText()
Makes a reactive version of the given function that also uses base::cat() to turn its result into a single-element character vector.

#### While building any app, it is critical to begin with the end in mind.
Sketch how the final app will look and how the user will interact with it.

##### titlePanel()
Create a panel containing an application title.

##### sidebarLayout()
Create a layout (sidebarLayout()) with a sidebar (sidebarPanel()) and main area (mainPanel()).

##### sidebarPanel()
The sidebar is displayed with a distinct background color and typically contains input controls. 

##### mainPanel()
The main area occupies 2/3 of the horizontal width and typically contains outputs.

##### renderPlot()
Renders a reactive plot that is suitable for assigning to an output slot.

##### plotOutput()
Create an plot or image output element.

## Inputs, Outputs, and Layouts
#### Inputs functions
Shiny provides a variety of inputs to choose from.
* **text** (`textInput`, `selectInput`)
* **numbers** (`numericInput`, `sliderInput`)
* **booleans** (`checkBoxInput`, `radioInput`)
* **dates** (`dateInput`, `dateRangeInput`)
* and more

All input functions have an inputId as first argument. They need to be unique.
Many inputs have a label as their next argument.
Then it depends on the type of input function for the following arguments

#### Where to use inputs
Adding an input to a shiny app is a two step process, where you first add an `___Input(“x”)` function to the UI and then access its value in the server using `input$x`.

##### selectInput
Create a select list that can be used to choose a single or multiple items from a list of values.

###### parameter: choices
List of values to select from. 

###### parameter: selected	
The initially selected value (or multiple values if multiple = TRUE). 

##### sliderInput()
Constructs a slider widget to select a numeric value from a range.

#### Outputs and render functions
Render functions are used to build outputs in the server based on the inputs.
* renderTable()
* renderImage()
* renderPlot()
* and more

Output functions are used back in the UI to display the outputs buitl in the server with render functions.
* tableOutput() or dataTableOutput()
* imageOutput()
* plotOutput()

1.  Create the output (plot, table, text, etc.).
2.  Render the output object using the appropriate `render___` function.
3.  Assign the rendered object to `output$x`.
4.  Add the output to the UI using the appropriate `___Output` function.

#### Non-Shiny output and render functions
There are multiple `htmlwidgets` packages like `DT`, `leaflet`, `plotly`, etc. that provide highly interactive outputs and can be easily integrated into Shiny apps using almost the same pattern.

#### Layouts and themes
Layout functions allow inputs and outputs to be visually arranged in the UI. A well-chosen layout makes a Shiny app aesthetically more appealing, and also improves the user experience.

Displaying several tables and plots on the same page can lead to visual clutter and distract users of the app. In such cases, the tab layout comes in handy, as it allows different outputs to be displayed as tabs.

* Sidebar layout
* Tab layout
* Theme selector
* shinythemes::themeSelector()
* theme = shinythemes::shinytheme("\<your theme>")

#### Adding a theme
Shiny makes it easy to customize the theme of an app. The UI functions in Shiny make use of [Twitter Bootstrap](https://getbootstrap.com/docs/3.4/), a popular framework for building web applications. [Bootswatch](https://bootswatch.com/) extends Bootstrap by making it really easy to skin an application with minimal code changes.

##### tabsetPanel()
Create a tabset that contains tabPanel() elements. Tabsets are useful for dividing output into multiple independently viewable sections.

##### tabPanel()
Create a tab panel.

```R
ui <- fluidPage(
  titlePanel("Popular Baby Names"),
  # shinythemes::themeSelector(),
  theme = shinythemes::shinytheme("superhero"),
  sidebarLayout(
    sidebarPanel(
      selectInput('name', 'Select Name', top_trendy_names$name)
    ),
    mainPanel(
      tabsetPanel(
        tabPanel("Plot", plotly::plotlyOutput('plot_trendy_names')),
        tabPanel("Table", DT::DTOutput('table_trendy_names'))
      )
    )
  )
)
server <- function(input, output, session){
  plot_trends <- function(){
    babynames %>% 
      filter(name == input$name) %>% 
      ggplot(aes(x = year, y = n)) +
      geom_col()
  }
  output$plot_trendy_names <- plotly::renderPlotly({
    plot_trends()
  })
    output$table_trendy_names <- DT::renderDT({
    babynames %>% 
      filter(name == input$name)
  })
}
shinyApp(ui = ui, server = server)
```

#### Building Shiny apps: 4 steps
Building a Shiny app is a modular process. You start with the UI, then you work on the server code, building outputs based on the user inputs. The more you practice this approach deliberately, the easier it will become to build good apps.

1. Add inputs (UI)
2. Add outputs (UI / server)
3. Update layout (UI)
4. Update output (server)

Run app at each step to insure everything works as intended.

## Reactivity 101
Essentially, the output is notified whenever any of its dependencies change, and it updates in response to that.
The two fundamental components in reactive programming are reactive sources, and endpoints.

#### Reactive Source
User input that typically comes through a browser interface.
Reactive sources are accessible through any input$x.
A reactive source can be connected to multiple endpoints, and vice versa.

#### Reactive Endpoint
Output that typically appears in the browser window, such as a plot or a table of values.
Endpoints are notified when one of the source dependencies change, and it updates in response to this signal.

An example of reactive endpoints is observers. For example, an output object is a reactive observer. Under the hood, a render function returns a reactive expression, and when you assign this reactive expression to an output$value, Shiny automatically creates an observer that uses the reactive expression.

#### Reactive Conductor
An intermediate that depends on reactive sources, and/or updates reactive endpoints. 
It is often used to encapsulate repeated computations, that can be expensive.

#### Reactive Expressions
A reactive expression is an R expression that uses widget input and returns a value. The reactive expression will update this value whenever the original widget changes.
Reactive endpoints are accessible through any output$y.
Reactive expressions are **lazy** and **cached**.
1.  Lazy: Evaluated only when it is called, typically by a reactive endpoint.
2.  Cached: Evaluated only when the value of one of its underlying dependencies changes.

Codes inside reactive needs to be wrapped inside curly braces.

##### reactive()
Wraps a normal expression to create a reactive expression. Conceptually, a reactive expression is a expression whose result will change over time.

#### Observers vs. Reactors
Reactive flow is all about connecting the different reactive components together.
![[Shiny Reactive Flowchart.png]]

A reactive expression can call other reactive expressions. This allows you to modularize computations and ensure that they are NOT executed repeatedly. Mastering the use of reactive expressions is key to building performant Shiny applications.

Observers can access reactive sources and reactive expressions, but they don't return a value. Instead they are used primarily for their side effects, like displaying a plot, table, or text in the browser. By default an observer triggers an action, whenever one of its underlying dependencies change.

**Role**
* reactive() is for calculating values, without side effects.
* observe() is for performing actions, with side effects.

**Differences**
* Return Values: Reactive expression returns values, but observers don't.
* Evaluation: Observers eagerly respond to changes in their dependencies, while reactive expressions are lazy.
* Side effects: Observers are primarily useful for their side effects, whereas, reactive expressions must NOT have side effects.

##### observe()
Create a reactive observer.

##### showNotification()
Show or remove a notification.

### Stop - Delay - Trigger
Shiny's reactive programming framework is designed such that any changes to inputs automatically update the outputs that depend on it. 

* Stop with isolate()
* Delay with eventReactive()
* Trigger with observeEvent()

#### Isolating Actions
If we don't want this behavior, we can use the isolate function. The isolate function allows to read a reactive value without triggering re-execution when its value changes.

##### isolate()
Create a non-reactive scope for an expression.

#### Delaying Actions
In some situations, we might want more explicit control over the trigger that causes the update. 

##### eventReactive()
Respond to "event-like" reactive inputs, values, and expressions.

##### actionButton()
Creates an action button or link whose value is initially zero, and increments by one each time it is pressed.

#### Triggering Actions
There are times when you want to perform an action in response to an event.

##### observeEvent()
Respond to "event-like" reactive inputs, values, and expressions.

It accepts two arguments:
1.  The event you want to respond to.
2.  The function that should be called whenever the event occurs.

##### showModal()
This causes a modal dialog to be displayed in the client browser, and is typically used with modalDialog().

##### modalDialog()
This creates the UI for a modal dialog, using Bootstrap's modal class. Modals are typically used for showing important messages, or for presenting UI that requires input from the user, such as a username and password input.

```R
server <- function(input, output, session) {
  observeEvent(input$show_help, {
    showModal(modalDialog(bmi_help_text))
  })
  rv_bmi <- eventReactive(input$show_bmi, {
    input$weight/(input$height^2)
  })
  output$bmi <- renderText({
    bmi <- rv_bmi()
    paste("Hi", input$name, ". Your BMI is", round(bmi, 1))
  })
}
ui <- fluidPage(
  titlePanel('BMI Calculator'),
  sidebarLayout(
    sidebarPanel(
      textInput('name', 'Enter your name'),
      numericInput('height', 'Enter your height in meters', 1.5, 1, 2),
      numericInput('weight', 'Enter your weight in Kilograms', 60, 45, 120),
      actionButton("show_bmi", "Show BMI"),
      actionButton("show_help", "Help")
      
    ),
    mainPanel(
      textOutput("bmi")
    )
  )
)
shinyApp(ui = ui, server = server)
```

## Shiny Apps Practices
##### dateRangeInput()
Creates a pair of text inputs which, when clicked on, bring up calendars that the user can click on to select dates.

### App 1: UFO Sightings Dashboard
```R
ui <- fluidPage(
  titlePanel("UFO Sightings"),
  sidebarLayout(
    sidebarPanel(
      selectInput("state", "Choose a U.S. state:", choices = unique(usa_ufo_sightings$state)),
      dateRangeInput("dates", "Choose a date range:",
                     start = "1920-01-01",
                     end = "2000-01-01")
    ),
    mainPanel(
      tabsetPanel(
        # Add plot output named 'shapes'
        tabPanel("shapes", plotOutput("shapes")),
        # Add table output named 'duration_table'
        tabPanel("duration_table", tableOutput("duration_table"))
      )
    )
  )
)
server <- function(input, output) {
  sightings <- reactive({
    usa_ufo_sightings %>%
      filter(date_sighted >= input$dates[1],
             date_sighted <= input$dates[2],
             state == input$state) 
  })
  output$shapes <- renderPlot({
    df <- sightings()
    ggplot(df, aes(shape)) +
      geom_bar()
  })
    output$duration_table <- renderTable({
    df <- sightings() 
    df %>%
      group_by(shape) %>%
      summarize(number = n(),
                average_min = mean(duration_sec) / 60,
                median_min = median(duration_sec) / 60,
                min_duration_min = min(duration_sec) / 60,
                max_duration_min = max(duration_sec) / 60
      )
  })
}
shinyApp(ui, server)
```

### App 2: Mental Health in Tech Survey
```R
ui <- fluidPage(
  titlePanel("2014 Mental Health in Tech Survey"),
  sidebarPanel(
    sliderTextInput(
      inputId = "work_interfere",
      label = "If you have a mental health condition, do you feel that it interferes with your work?", 
      grid = TRUE,
      force_edges = TRUE,
      choices = c("Never", "Rarely", "Sometimes", "Often")
    ),
    checkboxGroupInput(
      inputId = "mental_health_consequence",
      label = "Do you think that discussing a mental health issue with your employer would have negative consequences?", 
      choices = c("Maybe", "Yes", "No"),
      selected = "Maybe"
    ),
    pickerInput(
      inputId = "mental_vs_physical",
      label = "Do you feel that your employer takes mental health as seriously as physical health?", 
      choices = c("Don't Know", "No", "Yes"),
      multiple = TRUE
    )    
  ),
  mainPanel(
    plotOutput("age")  
  )
)
server <- function(input, output, session) {
  output$age <- renderPlot({
    validate(
      need(input$mental_vs_physical != "", "Please select an input for mental versus physical health.")
    )
    mental_health_survey %>%
      filter(
        work_interfere == input$work_interfere,
        mental_health_consequence %in% input$mental_health_consequence,
        mental_vs_physical %in% input$mental_vs_physical
      ) %>%
      ggplot(aes(Age)) +
      geom_histogram()
  })
}
shinyApp(ui, server)
```

#### Custom Error Messages
##### validate()
For an output rendering function (e.g. renderPlot()), you may need to check that certain input values are available and valid before you can render the output. validate gives you a convenient mechanism for doing so.

##### need()
The need function takes two arguments. The test and the custom error message.

#### shinyWidgets
##### shinyWidgetsGallery()
Opens a pre-built Shiny app that allows you to explore these pre-built inputs **and** gives you the code for implementing them.

##### checkboxGroupInput()
Create a group of checkboxes that can be used to toggle multiple choices independently. The server will receive the input as a character vector of the selected values.

##### pickerInput()
An alternative to selectInput with plenty of options to customize it.

### App 3: Explore Distinctives Ingredients Across Cuisines
```R
ui <- fluidPage(
  titlePanel('Explore Cuisines'),
  sidebarLayout(
    sidebarPanel(
      selectInput('cuisine', 'Select Cuisine', unique(recipes$cuisine)),
      sliderInput('nb_ingredients', 'Select No. of Ingredients', 5, 100, 20),
    ),
    mainPanel(
      tabsetPanel(
        tabPanel('Word Cloud', d3wordcloud::d3wordcloudOutput('wc_ingredients', height = '400')),
        tabPanel('Plot', plotly::plotlyOutput('plot_top_ingredients')),
        tabPanel('Table', DT::DTOutput('dt_top_ingredients'))
      )
    )
  )
)
server <- function(input, output, session){
  output$wc_ingredients <- d3wordcloud::renderD3wordcloud({
    ingredients_df <- rval_top_ingredients()
    d3wordcloud(ingredients_df$ingredient, ingredients_df$nb_recipes, tooltip = TRUE)
  })
  rval_top_ingredients <- reactive({
    recipes_enriched %>% 
      filter(cuisine == input$cuisine) %>% 
      arrange(desc(tf_idf)) %>% 
      head(input$nb_ingredients) %>% 
      mutate(ingredient = forcats::fct_reorder(ingredient, tf_idf))
  })
  output$plot_top_ingredients <- plotly::renderPlotly({
    rval_top_ingredients() %>%
      ggplot(aes(x = ingredient, y = tf_idf)) +
      geom_col() +
      coord_flip()
  })
  output$dt_top_ingredients <- DT::renderDT({
    recipes %>% 
      filter(cuisine == input$cuisine) %>% 
      count(ingredient, name = 'nb_recipes') %>% 
      arrange(desc(nb_recipes)) %>% 
      head(input$nb_ingredients)
  })
}
shinyApp(ui = ui, server= server)
```
##### DT::RenderDT() and DT::DTOuput()
Helper functions for using DT in Shiny. The former is used to create a container for table, and the latter is used in the server logic to render the table.

##### plotly::renderPlotly() and plotly::plotlyOutput()
Output and render functions for using plotly within Shiny applications and interactive Rmd documents.

##### d3wordcloud::renderD3wordcloud() and d3wordcloud::d3wordcloudOutput()
Widget render and output function for use in Shiny.

[http://gallery.htmlwidgets.org/](http://gallery.htmlwidgets.org/).

### App 4: Mass Shootings Analysis
```R
ui <- bootstrapPage(
  theme = shinythemes::shinytheme('simplex'),
  leaflet::leafletOutput('map', width = '100%', height = '100%'),
  absolutePanel(top = 10, right = 10, id = 'controls',
                sliderInput('nb_fatalities', 'Minimum Fatalities', 1, 40, 10),
                dateRangeInput(
                  'date_range', 'Select Date', "2010-01-01", "2019-12-01"
                ),
                actionButton('show_about', 'About')
  ),
  tags$style(type = "text/css", "
    html, body {width:100%;height:100%}     
    #controls{background-color:white;padding:20px;}
  ")
)
server <- function(input, output, session) {
  observeEvent(input$show_about, {
    showModal(modalDialog(text_about, title = 'About'))
  })
  output$map <- leaflet::renderLeaflet({
    mass_shootings %>% 
      filter(
        date >= input$date_range[1],
        date <= input$date_range[2],
        fatalities >= input$nb_fatalities
      ) %>% 
      leaflet() %>% 
      setView( -98.58, 39.82, zoom = 5) %>% 
      addTiles() %>% 
      addCircleMarkers(
        popup = ~ summary, radius = ~ sqrt(fatalities)*3,
        fillColor = 'red', color = 'red', weight = 1
      )
  })
}
shinyApp(ui, server)
```

##### bootstrapPage()
Create a Shiny UI page that loads the CSS and JavaScript for Bootstrap, and has no content in the page body (other than what you provide).

##### absolutePanel()
Creates a panel whose contents are absolutely positioned.

##### leaflet::renderLeaflet() and leaflet::leafletOutput()
Use leafletOutput() to create a UI element, and renderLeaflet() to render the map widget.

##### leaflet()
This function creates a Leaflet map widget using htmlwidgets. The widget can be rendered on HTML pages generated from R Markdown, Shiny, or other applications.

##### tags$style()
Apply CSS with HTML.

##### addCircleMarkers()
Add graphics elements and layers to the map widget.