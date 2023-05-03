add_contract(proton.token proton.token ${CMAKE_CURRENT_SOURCE_DIR}/src/proton.token.cpp)

target_include_directories(proton.token
   PUBLIC
   ${CMAKE_CURRENT_SOURCE_DIR}/include)

set_target_properties(proton.token
   PROPERTIES
   RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")

configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/ricardian/proton.token.contracts.md.in ${CMAKE_CURRENT_BINARY_DIR}/ricardian/proton.token.contracts.md @ONLY )

target_compile_options( proton.token PUBLIC -R${CMAKE_CURRENT_SOURCE_DIR}/ricardian -R${CMAKE_CURRENT_BINARY_DIR}/ricardian )
