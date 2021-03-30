https://stackoverflow.com/questions/51734734/cannot-load-rda

load() does not return the object. It produces a side effect where the objects saved in the file are loaded into the environment. Type df and you'll have your data. Use saveRDS() and readRDS() for the behavior you're expecting.