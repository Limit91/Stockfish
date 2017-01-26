mum_required (VERSION 3.0) 
project (stockfish)

find_package (Threads)

add_executable(stockfish benchmark.cpp bitbase.cpp bitboard.cpp endgame.cpp evaluate.cpp main.cpp material.cpp misc.cpp movegen.cpp movepick.cpp pawns.cpp position.cpp psqt.cpp search.cpp thread.cpp timeman.cpp tt.cpp uci.cpp ucioption.cpp syzygy/tbprobe.cpp) 

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/src)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++1y")

target_link_libraries (stockfish ${CMAKE_THREAD_LIBS_INIT})  

install(TARGETS stockfish DESTINATION /usr/games)
