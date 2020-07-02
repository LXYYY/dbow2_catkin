cmake_minimum_required(VERSION 2.8)
project(dbow2_catkin)
find_package(catkin_simple 0.1.0 REQUIRED)
catkin_simple()
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS}  -Wall  -O3 -march=native ")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall  -O3 -march=native")
include_directories(include/DBoW2/
  include/DUtils/)
set(HDRS_DBOW2
  include/DBoW2/BowVector.h
  include/DBoW2/FORB.h 
  include/DBoW2/FClass.h       
  include/DBoW2/FeatureVector.h
  include/DBoW2/ScoringObject.h   
  include/DBoW2/TemplatedVocabulary.h)
set(SRCS_DBOW2
  src/BowVector.cpp
  src/FORB.cpp      
  src/FeatureVector.cpp
  src/ScoringObject.cpp)

set(HDRS_DUTILS
  include/DUtils/Random.h
  include/DUtils/Timestamp.h)
set(SRCS_DUTILS
  src/Random.cpp
  src/Timestamp.cpp)

cs_add_library(DBoW2 SHARED ${SRCS_DBOW2} ${SRCS_DUTILS})

cs_install()
cs_export()
