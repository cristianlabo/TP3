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
|  boardConfig(); | configura los pines de entrada y salida    |
|  tickConfig( TICKRATE_MS );  | configurar la frecuencia de la interrupciones    |
|  tickCallbackSet( myTickHook, (void*)NULL );  | configura la funcion que se ejecutara con cada interrupcion    |
|  InitTimerTicks(ticks, NOF_TIMERS); | incializa la frecuencia del timer   |
|  prefix_init(&statechart);  | inicializa la maquina de estados    |
|  prefix_enter(&statechart);   |  cambia el estado de la maquina de estados   |
|  UpdateTimers(ticks, NOF_TIMERS);  | actualiza la frecuencia del timer    |
|  prefixIface_raise_evTick(&statechart);| activa el evento etick |
|  IsPendEvent(ticks, NOF_TIMERS, ticks[i].evid)       | devuelve true si se cumplio el tiempo de eventos dado por NOF_TIMERS|
|  prefix_raiseTimeEvent(&statechart, ticks[i].evid);   |  activa el evento etick   |
|  MarkAsAttEvent(ticks, NOF_TIMERS, ticks[i].evid);   |  setea el evento pendiente en false  |
|  prefix_runCycle(&statechart);   | cambia el estado de la maquina de estados  |

![funciones1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/funciones1.png)
![funciones2.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/funciones2.png)

Se pueden visualizar en la siguiente figura las constantes:

| Nombre | Descripción |
| ------ | ----------- |
|  TICKRATE_MS   |  setea la frecuencia de interrupciones   |
|  USE_TIME_EVENTS  | flag utilizado para decididir si se ejecutan eventos por tiempo o no    |
|  NOF_TIMERS  |  constante utilizada para definir el tiempo de cada evento  |
|  SysTick_Time_Flag  |  flag utilizado para saber si se produjo una interrupcion  |


![constantes1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/constantes2.png)
![constantes1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/constantes2.png)



# 2 free rtos examples 1 a 9


## Example 1

Archivo config.h
![Imagen 01_configh.png](https://raw.githubusercontent.com/DarioCapu/workspace-EDU_CIAA_NXP_TP3/master/Imagenes/01_configh.png)
Configurando el debug
![Imagen 02_debug.png](https://raw.githubusercontent.com/DarioCapu/workspace-EDU_CIAA_NXP_TP3/master/Imagenes/02_debug.png)
Corriendo el ejemplo 1
![Imagen 03_example1_debug.png](https://raw.githubusercontent.com/DarioCapu/workspace-EDU_CIAA_NXP_TP3/master/Imagenes/03_example1_debug.png)

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
