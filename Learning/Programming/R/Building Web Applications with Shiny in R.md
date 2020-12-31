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
