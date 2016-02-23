ADD_EXECUTABLE(sample_lbfgs_c sample.c)
ADD_EXECUTABLE(sample_lbfgs_cpp sample.cpp)

target_link_libraries(sample_lbfgs_c   lbfgs)
target_link_libraries(sample_lbfgs_cpp lbfgs)

