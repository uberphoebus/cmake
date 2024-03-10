cmake_minimum_required(VERSION 3.0.0)

# if-else
set(VAR YES)

if(VAR)
    message("If block")
else()
    message("Else block")
endif()

set(VAR OFF)

if(VAR)
    message("If block")
else()
    message("Else block")
endif()

set(Name Alice)
if(DEFINED Name)
    message("Name : if block")
else()
    message("Name : else block")
endif()

if(COMMAND target_link_library)
    message("target")
endif()

if(EXISTS /workspaces/cmake/module5/CMakeLists.txt)
    message("exist")
endif()


set(Name1 Alice)
set(Name2 Bob)
if (Name1 STRLESS Name2)
    message("less")
elseif(Name1 STRGREATER Name2)
    message("great")
endif()


# loop
set(VAR a)
while(NOT VAR STREQUAL "aaaaa")
    set(VAR ${VAR}a)
    message(${VAR})
endwhile()

foreach(Name Alice Bob Charlie)
    message(${Name})
endforeach()

foreach(x RANGE 10 20 3)
    message(${x})
endforeach()

set(VAR1 0;1)
set(VAR2 2 3)
set(VAR3 "4 5")
foreach(x IN LISTS VAR1 VAR2 VAR3)
    message("x = ${x}")
endforeach()


# function
function(print_detail name_var)
    message("1. my name is ${${name_var}}")
endfunction()
function(print_detail name_var)
    message("2. my name is ${${name_var}}")
endfunction()
function(print_detail name_var)
    message("3. my name is ${${name_var}}")
endfunction()

set(Name Charlie)
print_detail(Name)
_print_detail(Name)

function(print_detail_argv name_var)
    message("1. my name is ${${name_var}}")
    
    if(DEFINED ARGV1)
        message("my name is ${ARGV1}")
    endif()

    message("ARGC = ${ARGC}")
    message("ARGV = ${ARGV}")
    message("ARGN = ${ARGN}")

    if(DEFINED ARGV0)
        message("ARGV0 = ${ARGV0}")
    endif()
    if(DEFINED ARGV1)
        message("ARGV1 = ${ARGV1}")
    endif()
    if(DEFINED ARGV2)
        message("ARGV2 = ${ARGV2}")
    endif()
    if(DEFINED ARGV3)
        message("ARGV3 = ${ARGV3}")
    endif()

endfunction()

set(Name Charlie)
print_detail_argv(Name Bob Alice)

# scope
set(Name Charlie)
function(print_detail_scope)
    message("before change ${Name}")
    # set(Name Bob)
    set(Name Bob PARENT_SCOPE)
    message("after change ${Name}")
endfunction()
message("outside before ${Name}")
print_detail_scope()
message("outside before ${Name}")

set(Name Charlie)
message("Root dir   : before adding subdir ${Name}")
add_subdirectory(demo_subdirectory_scope)
message("Root dir   : after adding subdir ${Name}")