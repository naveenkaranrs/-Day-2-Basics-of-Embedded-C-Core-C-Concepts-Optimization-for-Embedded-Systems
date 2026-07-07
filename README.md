# 🚀 Day 2 – Basics of Embedded C | Core C Concepts & Optimization for Embedded Systems

> **30 Days of Embedded Systems**  
> **Board:** STM32 Nucleo-F103RB  
> **Language:** Embedded C  
> **Author:** Naveen Karan R S

---

## 📖 Overview

Embedded C is a specialized version of the C programming language used to develop firmware for microcontrollers and embedded systems. Unlike desktop applications, embedded software directly interacts with hardware such as GPIOs, timers, UART, SPI, I2C, ADC, and interrupts.

In this session, we learn the fundamental C concepts required for embedded programming and understand how to write optimized, readable, and efficient code for resource-constrained systems.

---

# 🎯 Learning Objectives

After completing Day 2, you will be able to:

- Understand the difference between C and Embedded C
- Use variables and different data types
- Apply arithmetic, logical, relational, and bitwise operators
- Write decision-making statements and loops
- Create reusable functions
- Work with arrays and pointers
- Understand structures and enumerations
- Use macros and header files
- Learn the purpose of `const` and `volatile`
- Write optimized Embedded C code
- Follow good coding practices

---

# 📚 Topics Covered

## 1️⃣ Embedded C vs Standard C

| Standard C | Embedded C |
|------------|------------|
| Runs on Computers | Runs on Microcontrollers |
| Uses Operating System | Mostly Bare Metal |
| Large Memory | Limited Memory |
| No Hardware Access | Direct Register Access |
| Performance Less Critical | Real-Time Performance |

---

## 2️⃣ Variables

Variables store data in memory.

```c
int speed = 100;
char state = 'A';
float voltage = 3.3;
```

---

## 3️⃣ Data Types

| Type | Size (STM32) | Example |
|------|------|---------|
| char | 1 Byte | 'A' |
| int | 4 Bytes | 100 |
| float | 4 Bytes | 3.14 |
| double | 8 Bytes | 6.283 |
| uint8_t | 1 Byte | 255 |
| uint16_t | 2 Bytes | 65535 |
| uint32_t | 4 Bytes | 4294967295 |

---

## 4️⃣ Operators

### Arithmetic

```c
+
-
*
/
%
```

### Relational

```c
==
!=
>
<
>=
<=
```

### Logical

```c
&&
||
!
```

### Bitwise

```c
&
|
^
~
<<
>>
```

---

## 5️⃣ Conditional Statements

```c
if(button == 1)
{
    LED_ON();
}
else
{
    LED_OFF();
}
```

Switch Statement

```c
switch(mode)
{
case 0:
    break;

case 1:
    break;

default:
    break;
}
```

---

## 6️⃣ Loops

### for Loop

```c
for(int i=0;i<10;i++)
{
}
```

### while Loop

```c
while(1)
{
    LED_Toggle();
}
```

### do-while Loop

```c
do
{
}while(condition);
```

---

## 7️⃣ Functions

```c
void LED_ON(void)
{

}

void LED_OFF(void)
{

}
```

Advantages

- Reusable
- Easy Debugging
- Modular Programming

---

## 8️⃣ Arrays

```c
int sensor[5];
```

Applications

- ADC Samples
- UART Buffer
- Sensor Values
- Data Logging

---

## 9️⃣ Pointers

```c
int value = 10;

int *ptr = &value;
```

Access Value

```c
*ptr = 20;
```

Pointers are used for

- Register Access
- DMA
- Drivers
- Buffers
- Peripheral Programming

---

## 🔟 Structures

```c
typedef struct
{
    uint8_t id;
    uint16_t speed;
}Motor;
```

Usage

```c
Motor M1;

M1.id = 1;
M1.speed = 200;
```

---

## 1️⃣1️⃣ Enumerations

```c
typedef enum
{
    OFF,
    ON
}LED_STATE;
```

---

## 1️⃣2️⃣ typedef

```c
typedef unsigned char uint8;
typedef unsigned int uint32;
```

Makes code easier to read.

---

## 1️⃣3️⃣ Macros

```c
#define LED_PIN 5
#define PI 3.14159
```

Function Macro

```c
#define MAX(a,b) ((a>b)?a:b)
```

---

## 1️⃣4️⃣ Header Files

Example

```
main.c

gpio.c

gpio.h

uart.c

uart.h
```

Benefits

- Reusable Code
- Easy Maintenance
- Modular Design

---

## 1️⃣5️⃣ Storage Classes

```c
auto
register
static
extern
```

Example

```c
static int counter;
```

---

## 1️⃣6️⃣ const Keyword

```c
const int MAX_SPEED = 100;
```

Used for

- Fixed Values
- Lookup Tables
- Configuration Data

---

## 1️⃣7️⃣ volatile Keyword

```c
volatile uint32_t *GPIOA_ODR;
```

Used for

- Hardware Registers
- Interrupt Variables
- Shared Flags

Without `volatile`, the compiler may optimize away important register accesses.

---

## 1️⃣8️⃣ Bit Manipulation

Set Bit

```c
GPIOA->ODR |= (1 << 5);
```

Clear Bit

```c
GPIOA->ODR &= ~(1 << 5);
```

Toggle Bit

```c
GPIOA->ODR ^= (1 << 5);
```

Read Bit

```c
if(GPIOA->IDR & (1 << 13))
{

}
```

Bit manipulation is one of the most important concepts in Embedded C.

---

## 1️⃣9️⃣ Optimization Techniques

- Use `uint8_t` instead of `int` whenever possible
- Avoid unnecessary global variables
- Keep Interrupt Service Routines (ISR) short
- Use bitwise operations instead of multiplication/division when appropriate
- Store constant data using `const`
- Use `volatile` only when required
- Avoid floating-point calculations if the MCU has no FPU
- Write modular functions
- Reduce RAM usage

---

## 2️⃣0️⃣ Embedded Coding Standards

✔ Meaningful Variable Names

✔ Proper Indentation

✔ Modular Programming

✔ Header Files

✔ Avoid Magic Numbers

✔ Reusable Functions

✔ Comment Important Logic

✔ Consistent Naming Convention

Example

```c
uint8_t ledState;

void LED_Init(void);
void LED_ON(void);
void LED_OFF(void);
```

---

# 📂 Folder Structure

```
Day-02/
│
├── README.md
├── Examples/
│   ├── Variables.c
│   ├── Operators.c
│   ├── Functions.c
│   ├── Arrays.c
│   ├── Pointers.c
│   ├── Structures.c
│   ├── Bitwise.c
│   └── Optimization.c
│
└── Notes/
    └── Embedded_C_Notes.pdf
```

---

# 🧠 Key Takeaways

- Embedded C is the foundation of firmware development.
- Bitwise operations are essential for register programming.
- Pointers allow direct access to memory and hardware registers.
- `volatile` prevents compiler optimization on hardware registers.
- `const` protects fixed data and can save RAM.
- Modular programming improves readability and maintenance.
- Efficient code is critical because embedded systems have limited resources.

---

# 🛠 Tools Used

- STM32 Nucleo-F103RB
- STM32CubeIDE
- Embedded C
- GCC ARM Compiler
- Git
- GitHub
- Wokwi

---

# 📅 Progress

| Day | Topic | Status |
|------|------------------------------|---------|
| ✅ Day 1 | STM32 Introduction & Development Setup | Completed |
| ✅ Day 2 | Embedded C Basics & Core Concepts | Completed |
| ⏳ Day 3 | GPIO Programming | Coming Soon |

---

# 📌 Next Day

**Day 3 – GPIO Programming**

- GPIO Architecture
- GPIO Registers
- Input Mode
- Output Mode
- Pull-up & Pull-down
- Push-Pull vs Open-Drain
- LED Blinking (HAL)
- LED Blinking (Register Level)
- Push Button Interface
- GPIO Mini Projects

---

## ⭐ Connect With Me

**LinkedIn:**  
https://www.linkedin.com/in/naveenkaran2005

If you found this repository helpful, don't forget to ⭐ star the repository and follow the series!
