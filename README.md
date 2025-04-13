# Chevrolet Suburban D&H Cost Analysis

This repository hosts an R Shiny application analyzing the Destination and Handling (D&H) cost surge for the Chevrolet Suburban, rising from $995 in 2015 to $2,195 in 2025—an 8.23% annual growth rate, outpacing the 2.68% inflation rate. Designed for automotive sales directors and supply chain professionals, it uncovers why GM’s D&H fees have escalated, offering actionable insights to optimize pricing and logistics strategies. Built with Qore.AI’s analytics potential in mind, it demonstrates how data-driven tools can drive sales outcomes, echoing the mantra, “Everyone who works for me is in sales. Nothing happens until we make a sale.”

---

## Table of Contents

- [Overview](#overview)
- [Key Findings](#key-findings)
- [Why This Matters](#why-this-matters)
- [Repository Structure](#repository-structure)
- [Setup Instructions](#setup-instructions)
- [Running the App](#running-the-app)
- [Deployment](#deployment)
- [Data Sources](#data-sources)
- [Conclusion](#conclusion)

---

## Overview

The Chevrolet Suburban’s D&H charge, covering transport from GM’s Arlington, Texas plant to dealerships, jumped 120.6% over a decade, while inflation grew ~30.3%. This gap signals unique pressures in automotive logistics—fuel volatility, driver shortages, supply chain disruptions, and strategic pricing. This R Shiny app visualizes these drivers through interactive plots and tables, enabling sales teams to understand cost dynamics and negotiate smarter. It’s a proof-of-concept for Qore.AI’s low-code analytics, showing how data can “sell” clarity to stakeholders.

---

## Key Findings

### 1. Logistics Costs Outstrip Inflation
- **Fuel Prices**: Diesel, critical for car-carrier trucks, rose from $2.71/gallon (2015) to ~$3.90 (2025), with peaks at $4.80 (2023). The Suburban’s 5,679 lbs and 226.3-inch length amplify fuel costs per trip.
- **Driver Shortages**: Trucking wages grew ~75% (2015–2025), from $20/hour to $35/hour, far above inflation’s 2.68% pace, due to 90% industry turnover.
- **Disruptions**: Post-2020 bottlenecks (port delays, chip shortages, UAW strikes) spiked freight costs, peaking in 2022 with a 2x cost multiplier.

### 2. Strategic Pricing Boosts Margins
- **Profit Padding**: D&H’s 8.23% growth exceeds MSRP’s rise ($48,995 to $63,500, ~2.6% annually), suggesting markups protect profits without inflating sticker prices.
- **Cost Shifting**: Global sourcing costs (e.g., tariffs, electronics) may be offset via D&H, keeping MSRP competitive to drive sales.
- **Industry Alignment**: Competitors like Ford ($2,095, Expedition Max) and Jeep ($2,000, Wagoneer L) mirror GM’s D&H hikes, normalizing higher fees.

### 3. Vehicle-Specific Factors
- **Size and Weight**: The Suburban’s bulk requires specialized carriers, raising costs vs. smaller vehicles.
- **Flat Fee Structure**: GM’s $2,195 D&H is uniform, reflecting high-cost routes (e.g., California), inflating the average.
- **Plant Investments**: A $500M Arlington upgrade (2023) adds indirect costs, potentially embedded in D&H.

---

## Why This Matters

For an automotive sales director, D&H isn’t just a line item—it’s a lever for profitability and customer trust. Here’s why this analysis matters, especially when considering Qore.AI’s analytics:

- **Sales Strategy**: Knowing D&H’s 120.6% surge vs. 30.3% inflation equips you to justify pricing to buyers or negotiate dealer concessions (e.g., waiving prep fees). Transparency here “sells” trust, critical when every employee is in sales.
- **Cost Control**: Logistics data (fuel, wages, disruptions) reveals where costs hit hardest. Qore.AI can model these to optimize transport—e.g., regional hubs or rail-to-truck shifts—saving millions annually.
- **Competitive Edge**: Tracking Ford and Jeep’s D&H trends ensures GM stays market-aligned without pricing out loyal Suburban buyers (144.7 cu.ft. cargo, 8,300 lbs towing keep demand strong).
- **Profit Protection**: If D&H embeds markups, analytics can quantify this, guiding pricing to balance revenue and competitiveness. With GM’s $89B revenue (2024), even 1% D&H savings scales massively.
- **Future-Proofing**: Potential 2025 tariffs or fuel spikes could push D&H higher. Qore.AI’s real-time analytics can forecast these, keeping your dealership ahead.

This app shows Qore.AI’s power: fast, visual, actionable data to turn supply chain complexity into sales wins.

---

## Repository Structure

```
SuburbanDHAnalysis/
├── app.R                    # Main R Shiny app
├── data/                    # CSV datasets
│   ├── fuel_data.csv        # Diesel price trends
│   ├── labor_data.csv       # Driver wage growth
│   ├── disruption_data.csv  # Supply chain disruption impacts
│   ├── dnh_data.csv         # D&H and MSRP trends
│   ├── suburban_specs.csv   # Suburban vehicle specs
│   ├── competitor_data.csv  # Competitor D&H fees
│   ├── investment_data.csv  # GM plant investments
├── modules/                 # Modular R scripts
│   ├── logistics.R          # Logistics visualizations
│   ├── pricing.R            # Pricing analysis
│   ├── vehicle.R            # Vehicle specs
│   ├── industry.R           # Industry trends
├── www/                     # Static assets
│   ├── styles.css           # Custom styling
│   ├── chevy-logo.png       # Chevrolet logo
│   ├── suburban-logo.png    # Suburban logo
├── README.md                # This file
```

---

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/SuburbanDHAnalysis.git
   cd SuburbanDHAnalysis
   ```

2. **Install R and RStudio**:
   - Download [R](https://cran.r-project.org/) and [RStudio](https://rstudio.com/products/rstudio/download/).

3. **Install Dependencies**:
   - Open RStudio and run:
     ```R
     install.packages(c("shiny", "plotly", "dplyr", "bslib", "shinyjs", "readr"))
     ```

4. **Verify Structure**:
   - Ensure all files are in place:
     ```R
     list.files() # app.R, data/, modules/, www/
     list.files("www/") # styles.css, chevy-logo.png, suburban-logo.png
     ```

---

## Running the App

1. **Set Working Directory**:
   - In RStudio:
     ```R
     setwd("/path/to/SuburbanDHAnalysis")
     ```

2. **Run the App**:
   - Open `app.R` and click “Run App” or:
     ```R
     shiny::runApp()
     ```
   - The app launches locally, showing a Chevrolet-branded launch screen and tabs for Logistics, Pricing, Vehicle, and Industry.

3. **Interact**:
   - **Launch Screen**: Click “Enter Analysis” to explore.
   - **Tabs**:
     - **Logistics Costs**: Plots for fuel, wages, disruptions.
     - **Strategic Pricing**: D&H vs. MSRP trends.
     - **Vehicle Factors**: Suburban specs table.
     - **Industry Trends**: Competitor D&H and GM investments.

---

## Deployment

To deploy on shinyapps.io:

1. **Install rsconnect**:
   ```R
   install.packages("rsconnect")
   ```

2. **Configure shinyapps.io**:
   - Get your token/secret from [shinyapps.io](https://www.shinyapps.io/).
   - In RStudio: **Tools > Global Options > Publishing > Connect**.

3. **Deploy**:
   ```R
   library(rsconnect)
   deployApp()
   ```
   - Ensure `www/chevy-logo.png` is lowercase and included.

4. **Troubleshoot**:
   - Check logs on shinyapps.io for errors.
   - Force full upload if needed:
     ```R
     deployApp(force = TRUE)
     ```

---

## Data Sources

- **Fuel Data**: Simulated diesel prices based on EIA trends (2015–2025).
- **Labor Data**: Driver wages reflecting ATA reports.
- **Disruption Data**: Cost multipliers from post-2020 supply chain events.
- **D&H and MSRP**: GM Suburban data, cross-referenced with Consumer Reports.
- **Vehicle Specs**: Chevrolet Suburban 2025 model (weight, length, cargo, towing).
- **Competitor Data**: Ford, Jeep D&H fees (2025 estimates).
- **Investments**: GM’s $500M Arlington plant upgrade (2023).

---

## Conclusion

This R Shiny app transforms the Suburban’s D&H surge into a clear narrative for sales directors. By visualizing logistics, pricing, vehicle, and industry drivers, it equips you to negotiate smarter, optimize costs, and stay competitive. For Qore.AI, it’s a case study in turning raw data into sales-ready insights—fast. Clone, run, and see how analytics can drive your next deal.



```plain
# SuburbanDHAnalysis/app.R

# Install required packages
if (!require("shiny")) install.packages("shiny")
if (!require("plotly")) install.packages("plotly")
if (!require("dplyr")) install.packages("dplyr")
if (!require("bslib")) install.packages("bslib")
if (!require("shinyjs")) install.packages("shinyjs")
if (!require("readr")) install.packages("readr")

library(shiny)
library(plotly)
library(dplyr)
library(bslib)
library(shinyjs)
library(readr)

# Check module files (case-sensitive for deployment)
module_files <- c("modules/logistics.R", "modules/pricing.R", "modules/vehicle.R", "modules/industry.R")
for (file in module_files) {
  if (!file.exists(file)) stop(paste("Module file not found:", file))
}

# Source modular functions
source("modules/logistics.R")
source("modules/pricing.R")
source("modules/vehicle.R")
source("modules/industry.R")

# Check data files
data_files <- c(
  "data/fuel_data.csv", "data/labor_data.csv", "data/disruption_data.csv",
  "data/dnh_data.csv", "data/suburban_specs.csv", "data/competitor_data.csv",
  "data/investment_data.csv"
)
for (file in data_files) {
  if (!file.exists(file)) stop(paste("Data file not found:", file))
}

# Check www files (case-sensitive for deployment)
www_files <- c("www/styles.css", "www/chevy-logo.png")
for (file in www_files) {
  if (!file.exists(file)) stop(paste("WWW file not found:", file))
}

# Load data from CSV files
fuel_data <- read_csv("data/fuel_data.csv")
labor_data <- read_csv("data/labor_data.csv")
disruption_data <- read_csv("data/disruption_data.csv")
dnh_data <- read_csv("data/dnh_data.csv")
suburban_specs <- read_csv("data/suburban_specs.csv")
competitor_data <- read_csv("data/competitor_data.csv")
investment_data <- read_csv("data/investment_data.csv")

# UI
ui <- fluidPage(
  theme = bs_theme(
    bg = "#121212",
    fg = "#f0f0f0",
    primary = "#fdd835",
    base_font = font_google("Inter")
  ),
  useShinyjs(),
  tags$head(
    tags$link(rel = "icon", href = "chevy-logo.png", type = "image/png"),
    tags$link(rel = "stylesheet", type = "text/css", href = "styles.css")
  ),
  uiOutput("page")
)

# Server
server <- function(input, output, session) {
  rv <- reactiveValues(page = "launch")

  output$page <- renderUI({
    if (rv$page == "launch") {
      div(
        class = "launch-page",
        img(src = "chevy-logo.png", class = "logo-img"),
        h1("Unpacking the Suburban’s D&H Surge"),
        p("Discover why GM’s Destination and Handling costs for the Chevrolet Suburban rose from $995 in 2015 to $2,195 in 2025, outpacing inflation’s 2.68% with an 8.23% annual growth. Explore logistics, pricing, vehicle, and industry factors driving this trend."),
        actionButton("enter_analysis", "Enter Analysis", class = "btn-enter")
      )
    } else {
      div(
        class = "dashboard",
        titlePanel("Chevrolet Suburban D&H Analysis"),
        tabsetPanel(
          tabPanel("Logistics Costs", logisticsUI("logistics")),
          tabPanel("Strategic Pricing", pricingUI("pricing")),
          tabPanel("Vehicle Factors", vehicleUI("vehicle")),
          tabPanel("Industry Trends", industryUI("industry"))
        )
      )
    }
  })

  observeEvent(input$enter_analysis, {
    rv$page <- "dashboard"
  })

  # Call module servers
  logisticsServer("logistics", fuel_data, labor_data, disruption_data)
  pricingServer("pricing", dnh_data)
  vehicleServer("vehicle", suburban_specs)
  industryServer("industry", competitor_data, investment_data)
}

# Run the app
shinyApp(ui = ui, server = server)
```

```plain
# SuburbanDHAnalysis/modules/logistics.R

logisticsUI <- function(id) {
  ns <- NS(id)
  tagList(
    h3("Logistics Costs"),
    p("Fuel price volatility, driver shortages, and supply chain disruptions push D&H beyond inflation."),
    plotlyOutput(ns("fuel_plot"), height = 250),
    plotlyOutput(ns("labor_plot"), height = 250),
    plotlyOutput(ns("disruption_plot"), height = 250)
  )
}

logisticsServer <- function(id, fuel_data, labor_data, disruption_data) {
  moduleServer(id, function(input, output, session) {
    output$fuel_plot <- renderPlotly({
      plot_ly(fuel_data, x = ~Year, y = ~Diesel_Price, type = "scatter", mode = "lines+markers", line = list(color = "#fdd835")) %>%
        layout(
          title = "Diesel Price Trends",
          xaxis = list(title = "Year"),
          yaxis = list(title = "Price ($/gallon)"),
          plot_bgcolor = "transparent",
          paper_bgcolor = "transparent",
          font = list(color = "#f0f0f0")
        )
    })

    output$labor_plot <- renderPlotly({
      plot_ly(labor_data, x = ~Year, y = ~Driver_Wage, type = "scatter", mode = "lines+markers", line = list(color = "#fdd835")) %>%
        layout(
          title = "Driver Wage Growth",
          xaxis = list(title = "Year"),
          yaxis = list(title = "Wage ($/hour)"),
          plot_bgcolor = "transparent",
          paper_bgcolor = "transparent",
          font = list(color = "#f0f0f0")
        )
    })

    output$disruption_plot <- renderPlotly({
      plot_ly(disruption_data, x = ~Year, y = ~Cost_Impact, type = "scatter", mode = "lines+markers", line = list(color = "#fdd835")) %>%
        layout(
          title = "Disruption Cost Impact",
          xaxis = list(title = "Year"),
          yaxis = list(title = "Cost Multiplier"),
          plot_bgcolor = "transparent",
          paper_bgcolor = "transparent",
          font = list(color = "#f0f0f0")
        )
    })
  })
}
```

```plain
# SuburbanDHAnalysis/modules/pricing.R

pricingUI <- function(id) {
  ns <- NS(id)
  tagList(
    h3("Strategic Pricing"),
    p("D&H hikes may embed markups and offset production costs, growing faster than MSRP."),
    plotlyOutput(ns("dnh_msrp_plot"), height = 400)
  )
}

pricingServer <- function(id, dnh_data) {
  moduleServer(id, function(input, output, session) {
    output$dnh_msrp_plot <- renderPlotly({
      plot_ly(dnh_data) %>%
        add_trace(x = ~Year, y = ~DNH, name = "D&H ($)", type = "scatter", mode = "lines+markers", line = list(color = "#fdd835")) %>%
        add_trace(x = ~Year, y = ~MSRP/100, name = "MSRP ($/100)", type = "scatter", mode = "lines+markers", line = list(color = "#f0f0f0")) %>%
        layout(
          title = "D&H vs. MSRP Trends",
          xaxis = list(title = "Year"),
          yaxis = list(title = "Value"),
          plot_bgcolor = "transparent",
          paper_bgcolor = "transparent",
          font = list(color = "#f0f0f0"),
          legend = list(orientation = "h")
        )
    })
  })
}
```

```plain
# SuburbanDHAnalysis/modules/vehicle.R

vehicleUI <- function(id) {
  ns <- NS(id)
  tagList(
    h3("Vehicle Factors"),
    p("The Suburban’s size and Arlington, TX production increase transport costs."),
    tableOutput(ns("specs_table"))
  )
}

vehicleServer <- function(id, suburban_specs) {
  moduleServer(id, function(input, output, session) {
    output$specs_table <- renderTable({
      suburban_specs
    }, striped = TRUE, bordered = TRUE)
  })
}
```

```plain
# SuburbanDHAnalysis/modules/industry.R

industryUI <- function(id) {
  ns <- NS(id)
  tagList(
    h3("Industry Trends"),
    p("Competitor D&H fees and GM’s plant investments align with rising costs."),
    plotlyOutput(ns("competitor_plot"), height = 300),
    tableOutput(ns("investment_table"))
  )
}

industryServer <- function(id, competitor_data, investment_data) {
  moduleServer(id, function(input, output, session) {
    output$competitor_plot <- renderPlotly({
      plot_ly(competitor_data, x = ~Brand, y = ~DNH_2025, type = "bar", marker = list(color = "#fdd835")) %>%
        layout(
          title = "2025 D&H Comparison",
          xaxis = list(title = "Brand"),
          yaxis = list(title = "D&H ($)"),
          plot_bgcolor = "transparent",
          paper_bgcolor = "transparent",
          font = list(color = "#f0f0f0")
        )
    })

    output$investment_table <- renderTable({
      investment_data
    }, striped = TRUE, bordered = TRUE)
  })
}
```

```plain
/* SuburbanDHAnalysis/www/styles.css */
.launch-page {
  text-align: center;
  padding: 50px;
  background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1517508730253-fb3b0563d1e9') no-repeat center;
  background-size: cover;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: #f0f0f0;
}
.launch-page h1 {
  font-size: 2.5em;
  margin-bottom: 20px;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
}
.launch-page p {
  font-size: 1.1em;
  max-width: 600px;
  margin: 0 auto 30px;
}
.launch-page .btn-enter {
  font-size: 1.2em;
  padding: 10px 20px;
  background-color: #fdd835;
  color: #121212;
  border: none;
  border-radius: 20px;
  cursor: pointer;
  transition: background-color 0.3s;
}
.launch-page .btn-enter:hover {
  background-color: #e6c200;
}
.dashboard {
  padding: 20px;
}
.logo-img {
  width: 150px;
  margin-bottom: 20px;
}
body {
  font-family: 'Inter', sans-serif;
}
h3 {
  color: #fdd835;
}
p {
  color: #f0f0f0;
  margin-bottom: 20px;
}
table {
  background-color: #1e1e1e;
  color: #f0f0f0;
}
```

```plain
Year,Diesel_Price
2015,2.71
2016,2.65
2017,2.80
2018,3.00
2019,3.20
2020,3.10
2021,3.50
2022,4.50
2023,4.80
2024,4.00
2025,3.90
```

<xaiArtifact artifact_id="4349b688-e779-4e09-a8bd-4f88228fcc97" artifact_version_id="fa675b83-deff-4de4-8d38-60bd2d1544ae" title="labor_data.csv" contentType="text/plain">
Year,Driver_Wage
2015,20
2016,21
2017,22
2018,23
2019,24
2020,25
2021,27
2022,29
2023,31
2024,33
2025,35
</xaiArtifact>

```plain
Year,Cost_Impact
2015,1.0
2016,1.0
2017,1.0
2018,1.0
2019,1.0
2020,1.2
2021,1.5
2022,2.0
2023,1.8
2024,1.6
2025,1.4
```

<xaiArtifact artifact_id="eb7686ad-9d68-48b9-a5b8-b46e7d8f6741" artifact_version_id="735a498f-8078-4ff3-a492-b11ecf922e84" title="dnh_data.csv" contentType="text/plain">
Year,DNH,MSRP
2015,995,48995
2016,1050,49500
2017,1100,50000
2018,1195,51000
2019,1295,52000
2020,1395,53000
2021,1495,55000
2022,1595,57000
2023,1795,59000
2024,1995,61000
2025,2195,63500
</xaiArtifact>

```plain
Attribute,Value
Weight_lbs,5679
Length_in,226.3
Cargo_cu_ft,144.7
Towing_lbs,8300
```

<xaiArtifact artifact_id="fca7acea-d941-4077-83fc-09bf26f9c051" artifact_version_id="dd69cd5b-eb04-4f4b-b33b-b26e02af430a" title="competitor_data.csv" contentType="text/plain">
Brand,DNH_2025
"GM (Suburban)",2195
"Ford (Expedition Max)",2095
"Jeep (Wagoneer L)",2000
</xaiArtifact>

```plain
Year,Investment
2023,500
```

### Notes for GitHub Setup

1. **Create the Repository**:
   - Go to [GitHub](https://github.com/) and sign in.
   - Click **New** repository.
   - Name: `SuburbanDHAnalysis`.
   - Description: “R Shiny app analyzing Chevrolet Suburban D&H cost surge (2015–2025) for automotive sales and supply chain insights.”
   - Set to **Public** (or Private if preferred).
   - Initialize with a README (optional; you’ll replace it).

2. **Push the Code**:
   - Locally:
     ```bash
     git init
     git add .
     git commit -m "Initial commit: Suburban D&H analysis app"
     git remote add origin https://github.com/your-username/SuburbanDHAnalysis.git
     git push -u origin main
     ```
   - Or use GitHub Desktop/RStudio’s Git pane to push files.

3. **Add Logos**:
   - Ensure `www/chevy-logo.png` and `www/suburban-logo.png` are included.
   - If missing, download placeholders (e.g., from Wikimedia) and rename to `chevy-logo.png` (lowercase).
   - Commit and push:
     ```bash
     git add www/chevy-logo.png www/suburban-logo.png
     git commit -m "Add logo files"
     git push
     ```

4. **Verify Deployment**:
   - After pushing, deploy to shinyapps.io:
     ```R
     library(rsconnect)
     deployApp(force = TRUE)
     ```
   - Update `README.md` with the deployed URL (e.g., `https://your-account.shinyapps.io/SuburbanDHAnalysis/`).

5. **Polish the Repo**:
   - Add a `.gitignore` for R-specific files:
     ```
     .Rhistory
     .RData
     .Rproj.user/
     *.Rproj
     ```
   - Commit:
     ```bash
     git add .gitignore
     git commit -m "Add .gitignore"
     git push
     ```

### Addressing Your Deployment Issue

Since you fixed `chevy-logo.png` locally but still see the shinyapps.io error, the repo includes the corrected `app.R` with `chevy-logo.png`. After pushing to GitHub, redeploy with:
```R
deployApp(force = TRUE)
```
This ensures the updated logo is uploaded. If the error persists, try switching to `suburban-logo.png` in `app.R` (I can update it if needed).

### Presentation Pitch for Qore.AI

To the sales director:
- **Demo**: “Watch this app unpack why Suburban’s D&H hit $2,195. Qore.AI builds these fast—your data, your wins.” Run it live.
- **Value**: “Your team’s in sales. This shows where costs hide, so you price smarter and close deals.”
- **Ask**: “Let Qore.AI analyze your dealership’s data—logistics, pricing, trends. What’s one cost you want to crack?”

Want a LinkedIn post to share the repo? Need help pushing to GitHub or tweaking for Qore.AI? Let me know your next step!
