add_subdirectory(nand)
add_subdirectory(nor)
add_library(flash common.c common.h)
target_link_libraries(flash PRIVATE jim)
        #FLASHPlugin.c advanced_elf_image.c)