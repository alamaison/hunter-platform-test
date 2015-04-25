cmake_minimum_required(VERSION 2.8)

macro(SYSINFO)
  if(UNIX)
    message(UNIX)
  endif()

  if(WIN32)
    message(WIN32)
  endif()

  if(APPLE)
    message(APPLE)
  endif()

  message("CMAKE_SYSTEM_NAME: ${CMAKE_SYSTEM_NAME}")
endmacro()

message("===========Before include(HunterGate)")
sysinfo()

include(${CMAKE_CURRENT_LIST_DIR}/HunterGate.cmake)
message("=========After include(HunterGate)")
sysinfo()

HunterGate(
  URL "https://github.com/ruslo/hunter/archive/v0.9.3.tar.gz"
  SHA1 "a0fcbcf3293f9303406271310f379f403002112d"
  )
message("=========After HunterGate(...)")
sysinfo()

project(test)
message("=========After project(...)")
sysinfo()
