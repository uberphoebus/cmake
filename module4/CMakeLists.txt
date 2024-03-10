cmake_minimum_required(VERSION 3.0.0)

message("Hello World")

set(NAME BOB)
set(HEIGHT 190)
message("my nsmae is ${NAME}, height is ${HEIGHT}")

set(NAME Alice)
set(Alice Bob)
message(NAME ${NAME} ${${NAME}})
message("NAME ${NAME} ${${NAME}}")

set(VAR a b c;d "e;f" 2.7 "Hello There")
list(APPEND VAR 1.6 XX)
message(${VAR})

list(REMOVE_AT VAR 2 -3)
message(${VAR})

list(REMOVE_ITEM VAR a 2.7)
message(${VAR})

list(INSERT VAR 2 XX 2.7)
message(${VAR})

list(REVERSE VAR)
message(${VAR})

list(REMOVE_DUPLICATES VAR)
message(${VAR})

list(SORT VAR)
message(${VAR})
