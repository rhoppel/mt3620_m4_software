# Sample: MT3620 M4 real-time application - FreeRTOS SPIM
### Description
This sample demonstrates how to use SPIM on an MT3620 real-time core.
- ISU1 SPIM interface is used to do the SPI master loopback test.
- ISU0 UART interface is used to print the output log.
- Please connect the ISU1_MISO1 to ISU1_MOSI1 for the loopback test.  
(Note, UART port number in main.c could be changed from **OS_HAL_UART_ISU0** to **OS_HAL_UART_PORT0** to use M4 dedicate UART port.)  
Please refer to the [MT3620 M4 API Rerference Manual](https://support.mediatek.com/AzureSphere/mt3620/M4_API_Reference_Manual) for the detailed API description.

### Prerequisites
* **Hardware**
    * [AVNET MT3620 Starter Kit](https://www.avnet.com/shop/us/products/avnet-engineering-services/aes-ms-mt3620-sk-g-3074457345636825680/)
    * or [Seeed MT3620 Development Kit](https://aka.ms/azurespheredevkits)
    * or other hardware that implements the [MT3620 Reference Development Board (RDB)](https://docs.microsoft.com/azure-sphere/hardware/mt3620-reference-board-design) design.
* **Software**
    * Refer to [Azure Sphere software installation guide](https://docs.microsoft.com/en-ca/azure-sphere/install/overview).
    * A terminal emulator (such as Telnet or [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/) to display the output log).

### How to build and run the sample
0. Important Note! To reuse the official GCC Cortex-M4F port, the gcc compiler flag should be modified to use FPU instructions. **Please copy the *AzureSphereRTCoreToolchainVFP.cmake* file into the Azure Sphere SDK install folder.** (Default path is *C:\Program Files (x86)\Microsoft Azure Sphere SDK\CMakeFiles*)
1. Start Visual Studio.  
2. From **File** menu, select **Open > CMake...** and navigate to the folder that contains this sample.  
3. Select **CMakeList.txt** and then click **Open**.  
4. Wait few seconds until Visual Studio finish create the project files.
5. From **Build** menu, select **Build ALL (Ctrl+Shift+B)**.  
6. Click **Select Start Item** and then select **GDB Debugger (RTCore)** as following.  
    ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/select_start_item.jpg)  
7. Press **F5** to start the application with debugging.  

### Hardware configuration
* [AVNET MT3620 Starter Kit](https://www.avnet.com/shop/us/products/avnet-engineering-services/aes-ms-mt3620-sk-g-3074457345636825680/)
    * Connect ISSU1_MISO1 to ISU1_MISO0 for SPI loopback:
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/avnet_spim_loopback.png)  
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/avnet_spim_loopback_connect.png)  
    * Connect PC UART Rx to AVNET MT3620 Starter Kit Click #1 TX (ISU0_UART_TX):
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/avnet.jpg)  
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/avnet_connect.jpg)  
* [Seeed MT3620 Development Kit](https://aka.ms/azurespheredevkits)
    * Connect ISSU1_MISO1 to ISU1_MISO0 for SPI loopback:
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/seeed_spim_loopback.png)  
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/seeed_spim_loopback_connect.png)  
    * Connect PC UART Rx to Seeed MT3620 Development Kit GPIO 26 / TXD0  (ISU0_UART_TX):
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/seeed.jpg)  
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/seeed_connect.jpg)  
	* M4 dedicate UART port is also available on Seeed MT3620 Development Kit:
        ![image](https://raw.githubusercontent.com/MediaTek-Labs/mt3620_m4_software/master/MT3620_M4_Sample_Code/BareMetal/MT3620_RTApp_BareMetal_HelloWorld/pic/seeed_m4_dedicate_uart.jpg)  
