find_package(CUDA REQUIRED)

set(LBSWIMMERS_NVCC_ARCH_FLAGS "-arch=compute_35 -code=sm_35,sm_37"
  CACHE string "CUDA architecture flags")

set(CUDA_NVCC_FLAGS "${LBSWIMMERS_NVCC_ARCH_FLAGS}"
  CACHE INTERNAL "Do not edit" FORCE)

cuda_add_library(lbswim SHARED lbswim.cu)

#add_executable(main main.cpp)
#target_link_libraries(main lbswim)

install(TARGETS lbswim DESTINATION ${_INST_DIR})
