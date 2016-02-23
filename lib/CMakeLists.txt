SET(lbfgsinclude_HEADERS ../include/lbfgs.h)

SET(lbfgs_SOURCES arithmetic_ansi.h 
        arithmetic_sse_double.h 
        arithmetic_sse_float.h 
        ../include/lbfgs.h 
        lbfgs.c )


ADD_LIBRARY(lbfgs ${lbfgs_SOURCES})


IF(HAVE_LIBM)
  TARGET_LINK_LIBRARIES(lbfgs m) 
ENDIF(HAVE_LIBM)


INSTALL(
  TARGETS 
    lbfgs
  EXPORT
    lbfgs
  LIBRARY DESTINATION ${INSTALL_LIB_DIR} COMPONENT libraries
  ARCHIVE DESTINATION ${INSTALL_LIB_DIR} COMPONENT libraries
  RUNTIME DESTINATION ${INSTALL_LIB_DIR} COMPONENT libraries
)
