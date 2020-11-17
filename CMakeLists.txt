cmake_minimum_required(VERSION 2.8)

project(LIBANTLR4)

set(
        ANTLR4_INCLUDES

        ${PROJECT_SOURCE_DIR}/src
        ${PROJECT_SOURCE_DIR}/src/atn
        ${PROJECT_SOURCE_DIR}/src/dfa
        ${PROJECT_SOURCE_DIR}/src/misc
        ${PROJECT_SOURCE_DIR}/src/support
        ${PROJECT_SOURCE_DIR}/src/tree
        ${PROJECT_SOURCE_DIR}/src/tree/pattern
        ${PROJECT_SOURCE_DIR}/src/tree/xpath
)


file(GLOB libantlrcpp_SRC
        "${PROJECT_SOURCE_DIR}/src/*.cpp"
        "${PROJECT_SOURCE_DIR}/src/atn/*.cpp"
        "${PROJECT_SOURCE_DIR}/src/dfa/*.cpp"
        "${PROJECT_SOURCE_DIR}/src/misc/*.cpp"
        "${PROJECT_SOURCE_DIR}/src/support/*.cpp"
        "${PROJECT_SOURCE_DIR}/src/tree/*.cpp"
        "${PROJECT_SOURCE_DIR}/src/tree/pattern/*.cpp"
        "${PROJECT_SOURCE_DIR}/src/tree/xpath/*.cpp"
        )

include_directories(${ANTLR4_INCLUDES})

add_library(antlr4_shared SHARED ${libantlrcpp_SRC})
add_library(antlr4_static STATIC ${libantlrcpp_SRC})
