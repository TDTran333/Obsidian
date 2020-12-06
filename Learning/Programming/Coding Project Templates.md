Thoughts: https://chendaniely.github.io/2017/05/30/project-templates/
RStudio: https://support.rstudio.com/hc/en-us/articles/200526207

---

### Sample template
```R
project
|
|- data             # raw and primary data, are not changed once created
|  |
|  |- project_data  # subfolder that links to an encrypted data storage container
|  |  |
|  |  |- original   # raw data, will not be altered
|  |  |- working    # intermediate datasets from src code
|  +  +- final      # datasets used in analysis
|
|- src /            # any programmatic code
|  |- user1         # user1 assigned to the project
|  +- user2         # user2 assigned to the project
|
|- output           # all output and results from workflows and analyses
|  |- figures/      # graphs, likely designated for manuscript figures
|  |- pictures/     # diagrams, images, and other non-graph graphics
|  +- analysis/     # generated reports for (e.g. rmarkdown output)
|
|- README.md        # the top level description of content
|
|- Makefile         # Makefile, if applicable
|- .gitignore       # git ignore file
+- project.Rproj    # RStudio project
```