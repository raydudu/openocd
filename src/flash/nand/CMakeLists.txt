file(GLOB ocdflashnand_SRCS "*.c" "*.h")
add_library(ocdflashnand ${ocdflashnand_SRCS})
target_link_libraries(ocdflashnand PRIVATE jim)
#[[
        arm_io.c
        at91sam9.c
        core.c
        davinci.c
        driver.c
        ecc.c
        ecc_kw.c
        fileio.c
        lpc3180.c
        lpc32xx.c
        mx3.c
        mxc.c
        nonce.c
        nuc910.c
        orion.c
        s3c2410.c
        s3c2412.c
        s3c2440.c
        s3c2443.c
        s3c24xx.c
        s3c6400.c
        tcl.c)]]
