message("inside subdir   : before change ${Name}")
set(Name Bob PARENT_SCOPE)
message("inside subdir   : after change ${Name}")