# ----------------------------- Environment --------------------------------- #
if (!Sys.info()[['sysname']] == 'Darwin'){
  # If running on shinyapps.io, set the RETICULATE_PYTHON evironment variable accordingly
  Sys.setenv(RETICULATE_PYTHON = '/home/shiny/.virtualenvs/python35_env/bin/python')
  # Set local debug to false
  Sys.setenv(DEBUG = FALSE) 
} else{
  # Running locally, use the local virtualenv
  options(shiny.port = 7450)
  reticulate::use_virtualenv('python35_env', required = T)
  Sys.setenv(DEBUG = TRUE)
}
