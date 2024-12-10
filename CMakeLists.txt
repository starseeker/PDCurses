# Minimum required version of CMake
cmake_minimum_required(VERSION 3.18)

# Set CMake project name
project(PDCURSES)

include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}/pdcurses
  ${CMAKE_CURRENT_SOURCE_DIR}/wincon
  ${CMAKE_CURRENT_BINARY_DIR}
)

set(PD_SRCS
  pdcurses/addch.c 
  pdcurses/addchstr.c 
  pdcurses/addstr.c 
  pdcurses/attr.c 
  pdcurses/beep.c 
  pdcurses/bkgd.c 
  pdcurses/border.c 
  pdcurses/clear.c 
  pdcurses/color.c 
  pdcurses/delch.c 
  pdcurses/deleteln.c 
  pdcurses/getch.c 
  pdcurses/getstr.c 
  pdcurses/getyx.c 
  pdcurses/inch.c 
  pdcurses/inchstr.c 
  pdcurses/initscr.c 
  pdcurses/inopts.c 
  pdcurses/insch.c 
  pdcurses/insstr.c 
  pdcurses/instr.c 
  pdcurses/kernel.c 
  pdcurses/keyname.c 
  pdcurses/mouse.c 
  pdcurses/move.c 
  pdcurses/outopts.c 
  pdcurses/overlay.c 
  pdcurses/pad.c 
  pdcurses/panel.c 
  pdcurses/printw.c 
  pdcurses/refresh.c 
  pdcurses/scanw.c 
  pdcurses/scr_dump.c 
  pdcurses/scroll.c 
  pdcurses/slk.c 
  pdcurses/termattr.c 
  pdcurses/touch.c 
  pdcurses/util.c 
  pdcurses/window.c 
  pdcurses/debug.c
  wincon/pdcclip.c 
  wincon/pdcdisp.c 
  wincon/pdcgetsc.c 
  wincon/pdckbd.c 
  wincon/pdcscrn.c 
  wincon/pdcsetsc.c 
  wincon/pdcutil.c
)

if (NOT DEFINED BIN_DIR)
  set (BIN_DIR bin)
endif (NOT DEFINED BIN_DIR)

if (NOT DEFINED LIB_DIR)
  set (LIB_DIR lib)
endif (NOT DEFINED LIB_DIR)

add_library(pdcurses ${PD_SRCS})
install(TARGETS pdcurses
  RUNTIME DESTINATION ${BIN_DIR}
  LIBRARY DESTINATION ${LIB_DIR}
  ARCHIVE DESTINATION ${LIB_DIR}
  )

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8

