# README: CIRCUITOS SECUENCIALES SÍNCRONOS EN VHDL

## CLASIFICACIÓN GENERAL

Esta sección de código contiene una colección de módulos VHDL cuyo propósito es la implementación de **Circuitos Secuenciales Síncronos** [1, 2]. Estos diseños son fundamentales en la arquitectura de computadores y sistemas digitales [1].

Los módulos se agrupan en las siguientes categorías principales: **Registros de desplazamiento**, **Flip-Flops**, **Contadores**, y **Bancos de pruebas** (Testbenches) [2].

---

## 1. REGISTROS (REGISTERS)

Los registros son circuitos diseñados para almacenar y manipular datos de múltiples bits bajo la sincronización del reloj.

| Código VHDL | Tipo y Función | Detalles Clave |
| :--- | :--- | :--- |
| **Registro4BitsDesplazamiento** | **Registro universal de desplazamiento** (*Shift Register Universal*) [3]. | Posee un **selector S** que permite elegir entre cuatro operaciones esenciales: **desplazar a la derecha**, **desplazar a la izquierda**, **cargar en paralelo** o **mantener el valor** [3]. |
| **RegistroSerie** | **Registro de corrimiento con realimentación lógica** [3]. | Se **desplaza en cada flanco de reloj** [3]. Calcula una nueva entrada basada en una operación lógica **OR** [3]. Se utiliza para **generar secuencias periódicas** [3]. (Es la intención de un *shift register* con lógica combinacional de realimentación, aunque la fuente lo describe como "improvisado") [4]. |

## 2. FLIP-FLOPS (UNIDADES BÁSICAS DE MEMORIA)

Los Flip-Flops son las unidades más básicas de almacenamiento de 1 bit en los circuitos secuenciales [4].

| Código VHDL | Tipo y Función | Uso Típico / Implementación |
| :--- | :--- | :--- |
| **flipflopT** | **Flip-Flop T** (*Toggle Flip-Flop*) [4]. | Se utiliza típicamente en **contadores toggle**, **divisores de frecuencia** y la generación de **secuencias binarias** [4]. |
| **flipFlopJk** | **Flip-Flop JK síncrono** [4]. | Implementa la tabla de verdad estándar de JK [4]: $JK=00$ para **mantener** el valor, $JK=11$ para **toggle** (conmutar), $JK=01$ para **reset**, y $JK=10$ para **set** [4]. |

## 3. CONTADORES (COUNTERS)

Los contadores son registros especializados en la secuenciación, capaces de incrementar o decrementar su valor en cada ciclo de reloj [5].

| Código VHDL | Tipo y Función | Notas de Implementación |
| :--- | :--- | :--- |
| **contadorEnBajo** (versión correcta) | **Contador ascendente parametrizable** [5]. | Es una **implementación estándar de contadores binarios** [5]. Cuenta +1 por ciclo cuando la señal *enable* está activa (enable=1) [5]. Es **parametrizable por ancho** [5]. |
| **contador** (con clk1) | **Contador bidireccional** (*up/down*) **con divisor de reloj interno** [5]. | Utiliza un registro (*prescaler*) para **dividir el reloj** (`clk1`) [5]. Controla la dirección de la cuenta (hacia arriba o hacia abajo) mediante la señal `sentido` [5]. |
| **segunda versión incorrecta de contadorEnBajo** | **Contador ascendente (mal implementado)** [6]. | Intenta ser un contador síncrono, pero la implementación contiene fallas o errores de diseño [6]. |

## 4. TESTBENCHES (BANCOS DE PRUEBAS)

Los bancos de pruebas se utilizan para verificar y simular el funcionamiento de los componentes diseñados [7].

| Código VHDL | Tipo y Función | Notas de Implementación |
| :--- | :--- | :--- |
| **Testbench** (en el primer archivo) | **Banco de pruebas estructural incompleto** [6]. | Pertenece a la categoría de **bancos de verificación** (*simulation testbenches*) [7]. **Instancia un componente**, **declara señales** y **crea un proceso** (`process tb`) para aplicar estímulos [6]. Sin embargo, **no genera reloj**, por lo que es una plantilla básica [6]. |

---

## RESUMEN DE MÓDULOS

A continuación, se presenta un resumen de los códigos y su clasificación de módulo secuencial [7]:

| Código | Tipo de Módulo Secuencial |
| :--- | :--- |
| RegistroSerie | Registro de desplazamiento con realimentación [7] |
| Registro4BitsDesplazamiento | Registro universal de desplazamiento [7] |
| flipflopT | Flip-Flop T [7] |
| flipFlopJk | Flip-Flop JK [7] |
| contadorEnBajo (correcto) | Contador ascendente parametrizable [7] |
| contador (con clk1) | Contador *up/down* con divisor de frecuencia [7] |
| contadorEnBajo (incorrecto) | Contador ascendente (mal implementado) [7] |
| Testbench | Banco de pruebas [7] |