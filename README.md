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


## Example 1 Creating tasks

En la siguiente figura se puede ver el diagrama temporal de la distribución del tiempo de CPU entre tareas, Kernel,
Interrupciones:

Se puede  configurar el time slice desde freertos_examples_1_to_9/example/inc/FreeRTOSConfig.h como se puede ver en la figura:

![Imagen 01_configh.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/01_configh.png)

Modificando el valor de este parametro para los diferentes casos (1000mS/100mS/10mS/1mS) se obtuvo que cuanto menor sea este valor las tareas manejadas por el Scheduler iran iterando cada vez mas rapido debido a que tienen la misma prioridad.
Este parametro permite que las tareas programadas terminen en su totalidad si estas son de menor tiempo que este parametro.
Se puede observar que las tareas se interrumpen debido a que tienen el mismo nivel de prioridad.En la siguiente figura se puede ver como las tareas no llegan a terminar de imprimir el mensaje por el usart si el perido de interrupcion es demasiado corto( f=1000 Hz => T=1ms):

![observacion_tarea1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/observacion_tarea1.png)

## Example 2 Using the task parameter

En la siguiente figura se puede ver el diagrama temporal de la distribución del tiempo de CPU entre tareas, Kernel,
Interrupciones:

Se puede  configurar el time slice desde freertos_examples_1_to_9/example/inc/FreeRTOSConfig.h como se mostro en ejemplo anterior.
La diferencia primordial respecto del ejemplo anterior es que las tareas estan creadas con parametros distintos.
En este caso la funcion toggle permite que cambie de estado el led provocando que se visualice un parpadeo intermitente cuanto mayor sea la frecuencia de interrupcion de cada tarea.
Se puede observar que las tareas se interrumpen debido a que tienen el mismo nivel de prioridad.En la siguiente figura se puede ver como las tareas no llegan a terminar de imprimir el mensaje por el usart si el perido de interrupcion es demasiado corto( f=1000 Hz => T=1ms).:

![observacion_tarea1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/observacion_tarea1.png)

## Example 3 Experimenting with priorities

## Example 4 Using the Blocked state to create delay

## Example 5 Converting the example tasks to use vTaskDelayUntil

## Example 6 Combining blocking and non-blocking tasks

## Example 7 Defining an idle task hook function

## Example 8 Changing task priorities

## Example 9 Deleting tasks


# 3 free rtos examples 10 a 16


## Example 10 Blocking when receiving from a queue

En la siguiente figura se puede ver el diagrama temporal de la distribución del tiempo de CPU entre tareas, Kernel,
Interrupciones:

Se puede  configurar el time slice desde freertos_examples_1_to_9/example/inc/FreeRTOSConfig.h como se puede ver en la figura:


Se puede observar que las tareas se interrumpen debido a que tienen el mismo nivel de prioridad.En la siguiente figura se puede ver como las tareas no llegan a terminar de imprimir el mensaje por el usart si el perido de interrupcion es demasiado corto( f=1000 Hz => T=1ms):

![observacion_tarea1.png](https://raw.githubusercontent.com/cristianlabo/TP3/master/Imagenes/observacion_tarea1.png)

## Example 11 Blocking when sending to a queue or sending structures on a queue 

En la siguiente figura se puede ver el diagrama temporal de la distribución del tiempo de CPU entre tareas, Kernel,
Interrupciones:

Se puede  configurar el time slice desde freertos_examples_1_to_9/example/inc/FreeRTOSConfig.h como se puede ver en la figura:


Se puede observar que 

## Example 12 Using a binary semaphore to synchronize a task with an interrupt 

## Example 13 Using a counting semaphore to synchronize a task with an interrupt 

## Example 14 Sending and receiving on a queue from within an interrupt 

## Example 15 Re-writing vPrintString() to use a semaphore

## Example 16 Re-writing vPrintString() to use a gatekeeper task


# 4 Implementacion 1


# 5 Implementacion 2


# 6 Implementacion 3


# 7 Hoja de ruta
