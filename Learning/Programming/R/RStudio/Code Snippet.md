https://support.rstudio.com/hc/en-us/articles/204463668-Code-Snippets

Code snippets are text macros that are used for quickly inserting common snippets of code. 


https://community.rstudio.com/t/can-you-change-the-directory-the-rstudio-looks-for-the-r-snippets-file/18218

    Put you existing r.snippets file in the new directory on the shared drive. I called mine 'snippet files'
    Delete the snippets directory which is inside the .R directory
    Run cdm as an administrator.
    Enter the command mklink /D "C:\Users\name.surname\Documents\.R\snippets" "T:\shared directory\snippet files"
    Restart Rstudio.
