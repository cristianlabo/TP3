**66.48 SEMINARIO DE SISTEMAS EMBEBIDOS - FIUBA**

- Darío Capucchio 85119
- Cristian García 89040

# workspace-EDU_CIAA_NXP_TP3

LPC43xx Entradas y Salidas (Digitales) de Propósito General (GPIO) - FreeRTOS

# Objetivo
- Uso del IDE
- Uso de GPIO & FreeRTOS
- Documentación

# Contenidos
- [1 Uso del IDE](#1-Uso-del-IDE)
- [2 free rtos examples 1 a 9](#2-free-rtos-examples-1-a-9)
- [3 free rtos examples 10 a 16](#3-free-rtos-examples-10-a-16)
- [4 Implementacion 1](#4-Implementacion-1)
- [5 Implementacion 2](#5-Implementacion-2)
- [6 Implementacion 3](#6-Implementacion-3)
- [7 Hoja de ruta](#7-hoja-de-ruta)


# 1 Uso del IDE

Utilizando el IDE LPCXpresso IDE v8.2.0 se creo el workspace "workspace-EDU_CIAA_NXP_TP3"  como se muestra en la figura:

![Imagen 00_workspace.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/00_workspace.png)

Luego se importo el proyecto LPCXpresso-FreeRTOS-Examples.zip y se configuro el DEBUG como se muestra en la figura:

![debug1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/debug1.png)
![debug2.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/debug2.png)


Luego desde el archivo freertos_examples_1_to_9/example/freertos_examples_1_to_9.c se configuro el example 1 como se ve en la siguiente figura:

![definiciones.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/definiciones.png)
![definiciones2.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/definiciones2.png)

Se pueden visualizar en la siguiente figura las funciones:


| Nombre | Descripción |
| ------ | ----------- |
| Board_LED_Set(LED3, LED_ON);| enciende le led 3   |
|  DEBUGOUT(pcTaskName);  | muestra por el usart el mensaje  guardado en pcTaskName |
|  prvSetupHardware();  | setea las variables del sistema   |
|  xTaskCreate(vTask2, (char *) "Task2", configMINIMAL_STACK_SIZE,NULL, (tskIDLE_PRIORITY + 1UL), (xTaskHandle *) NULL);|crea la tarea2|
| vTaskStartScheduler(); | activa el manejador de tareas |


![funciones1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/funciones1.png)
![funciones2.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/funciones2.png)

Se pueden visualizar en la siguiente figura las constantes:

| Nombre | Descripción |
| ------ | ----------- |
| LED3   |  constante que indica la posicion fisica dl pin del led 3  |
|  LED_ON  | constante que indica el estado encendido de un led   |
|  *pcTaskName   |  cadena de texto usada para guardar el nombre de la tarea  |
|  ul |  variable de iteracion volatile  |
|  mainDELAY_LOOP_COUNT |  constante utilizada para indicar el maximo de delay de la tarea  |
|  configMINIMAL_STACK_SIZE |  constante que indica el minimo de espacion en memoria de stack  |
| tskIDLE_PRIORITY + 1UL|  constante que indica la prioridad de la tarea  |


![constantes1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/constantes2.png)
![constantes1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/constantes2.png)



# 2 free rtos examples 1 a 9


## Example 1

Archivo config.h
![Imagen 01_configh.png](https://raw.githubusercontent.com/DarioCapu/workspace-EDU_CIAA_NXP_TP3/master/Imagenes/01_configh.png)
Configurando el debug

## Example 2

## Example 3

## Example 4

## Example 5

## Example 6

## Example 7

## Example 8

## Example 9


# 3 free rtos examples 10 a 16


## Example 10

## Example 11

## Example 12

## Example 13

## Example 14

## Example 15

## Example 16


# 4 Implementacion 1


# 5 Implementacion 2


# 6 Implementacion 3


# 7 Hoja de ruta
