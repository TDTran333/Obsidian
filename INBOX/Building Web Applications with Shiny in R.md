---
aliases: Shiny
tags: R, shiny
---

# Building Web Applications with Shiny in R
### Introduction to Shiny
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

#### Steps to build the Shiny app
* Add inputs (UI)
* Add outputs (UI / server)
* Update layout (UI)
* Update output (server)

##### titlePanel()
Create a panel containing an application title.

##### sidebarLayout()
Create a layout (sidebarLayout()) with a sidebar (sidebarPanel()) and main area (mainPanel()).

##### sidebarPanel()
The sidebar is displayed with a distinct background color and typically contains input controls. 

##### mainPanel()
The main area occupies 2/3 of the horizontal width and typically contains outputs.

##### renderPlot(0)
Renders a reactive plot that is suitable for assigning to an output slot.

##### plotOutput()
Create an plot or image output element.

### Inputs, Outputs, and Layouts
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

#### Non-Shiny output and render functions
DT, leaflet, plotly

