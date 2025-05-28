cmake_minimum_required(VERSION 3.22)

project(stm32cubemx)
add_library(stm32cubemx INTERFACE)

# Enable CMake support for ASM and C languages
enable_language(C ASM)

target_compile_definitions(stm32cubemx INTERFACE 
	USE_FULL_LL_DRIVER 
	USE_HAL_DRIVER 
	STM32G431xx
    $<$<CONFIG:Debug>:DEBUG>
)

target_include_directories(stm32cubemx INTERFACE
    ../../Inc
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Inc
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Inc/Legacy
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/include
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/CMSIS_RTOS_V2
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/portable/GCC/ARM_CM4F
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/CMSIS/Device/ST/STM32G4xx/Include
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/CMSIS/Include
)

target_sources(stm32cubemx INTERFACE
    ../../Src/main.c
    ../../Src/app_freertos.c
    ../../Src/stm32g4xx_it.c
    ../../Src/stm32g4xx_hal_msp.c
    ../../Src/stm32g4xx_hal_timebase_tim.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_ll_utils.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_ll_exti.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_ll_gpio.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_ll_adc.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_ll_dma.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_rcc.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_rcc_ex.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_flash.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_flash_ex.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_flash_ramfunc.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_gpio.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_exti.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_dma.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_dma_ex.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_pwr.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_pwr_ex.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_cortex.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_uart.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_uart_ex.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_tim.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_hal_tim_ex.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Drivers/STM32G4xx_HAL_Driver/Src/stm32g4xx_ll_ucpd.c
    ../../Src/system_stm32g4xx.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/croutine.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/event_groups.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/list.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/queue.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/stream_buffer.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/tasks.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/timers.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/CMSIS_RTOS_V2/cmsis_os2.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/portable/MemMang/heap_4.c
    /home/evan/STM32Cube/Repository/STM32Cube_FW_G4_V1.6.0/Middlewares/Third_Party/FreeRTOS/Source/portable/GCC/ARM_CM4F/port.c
    ../../Src/sysmem.c
    ../../Src/syscalls.c
    ../../startup_stm32g431xx.s
)

target_link_directories(stm32cubemx INTERFACE
)

target_link_libraries(stm32cubemx INTERFACE
)

# Validate that STM32CubeMX code is compatible with C standard
if(CMAKE_C_STANDARD LESS 11)
    message(ERROR "Generated code requires C11 or higher")
endif()


