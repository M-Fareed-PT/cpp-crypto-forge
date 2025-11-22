cmake_minimum_required(VERSION 3.10)
project(CryptoForge)

set(CMAKE_CXX_STANDARD 17)

# Include folder
include_directories(include)

# Find OpenSSL
find_package(OpenSSL REQUIRED)

# Source files
set(SOURCES
    src/main.cpp
    src/cli.cpp
    src/aes.cpp
    src/rsa.cpp
    src/ecc.cpp
    src/sha.cpp
    src/utils.cpp
)

# Build executable
add_executable(CryptoForge ${SOURCES})

# Link OpenSSL
target_link_libraries(CryptoForge OpenSSL::Crypto)
