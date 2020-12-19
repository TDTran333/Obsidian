---
aliases: tidytuesdayR
tags: R
---
Link: [Website](https://thebioengineer.github.io/tidytuesdayR/reference/index.html)

# tidytuesdayR package
tidytuesdayR has the main goal to make it easy to participate in the weekly #TidyTuesday project. 

## Functions

| Function                                                     | Definition                                                  |
|:------------------------------------------------------------ |:----------------------------------------------------------- |
| tt_available() tt_datasets()                                 | Listing all available TidyTuesdays                          |
| print(<tt_dataset_table>)<br/>print(<tt_dataset_table_list>) | Printing Utilities for Listing Available Datasets           |
| github_pat()                                                 | Return the local user's GitHub Personal Access Token        |
| last_tuesday()                                               | Find the most recent tuesday                                |
| print(<tt_data>) <br/> print(\<tt>)                          | print methods of the tt objects                             |
| rate_limit_check()                                           | Get Rate limit left for GitHub Calls                        |
| readme()                                                     | Readme HTML maker and Viewer                                |
| tt_date()                                                    | Get date of TidyTuesday, given the year and week            |
| tt_download()                                                | Download all or specific files identified in the tt dataset |
| tt_download_file()                                           | Reads in TidyTuesday datasets from Github repo              |
| tt_load()                                                    | Load TidyTuesday data from Github                           |
| tt_load_gh()                                                 | Load TidyTuesday data from Github                           |
| use_tidytemplate()                                           | Call and open the tidytemplate                              |