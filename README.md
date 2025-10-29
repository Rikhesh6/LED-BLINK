# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
 <img width="1919" height="1142" alt="image" src="https://github.com/user-attachments/assets/c0ac0efc-e1c3-408e-be5c-03c84f89ae15" />

2. Click **File → New STM32 Project**.
   <img width="1909" height="1132" alt="image" src="https://github.com/user-attachments/assets/36b1e88f-9d9b-4511-b671-cbc11a221805" />


3. Select the **target microcontroller** or board and click **Next**.
<img width="1919" height="1113" alt="image" src="https://github.com/user-attachments/assets/bef71d87-5665-405d-ad47-b3f09b8665f7" />


4. Name the project.
  <img width="1919" height="1120" alt="image" src="https://github.com/user-attachments/assets/c626fc85-3318-4351-b8e3-ca584de8d2ae" />


5. The corresponding `.ioc` file will be generated automatically.
 <img width="1918" height="1118" alt="image" src="https://github.com/user-attachments/assets/dc8ab870-cca1-49f7-a1e0-d284b09aa56b" />


6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.
  <img width="1918" height="1107" alt="image" src="https://github.com/user-attachments/assets/e1294b86-956c-455c-99ce-0e9e3549297f" />


7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically.
   
 
8. Edit the generated main program as required.
   

9. Click **Project → Build All**.
  
10. Link the **HEX file** using the post-build process.
    
11. Click **Debug** and connect the **STM Nucleo Board**.
   
13. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 

CASE 2: LED OFF

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.
