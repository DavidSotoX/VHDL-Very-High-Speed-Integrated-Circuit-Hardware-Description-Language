README - PROYECTO CPU EN VHDL (ALU + REGISTRO + CPU)

Descripcion General
Este proyecto implementa un procesador simple en VHDL, formado por tres bloques principales

ALU (Unidad Aritmetico-Lógica)

Banco de Registros

CPU (Integracion del datapath y la unidad de control)

Cada modulo funciona por separado, pero todos forman parte de un mismo proyecto la construccion de un CPU academico.

ALU-main

En esta carpeta se encuentran varias implementaciones de la ALU

ALU_generica version parametrizable mediante un generico T.

ALU_4BITS y ALU_8BITS versiones fijas para practica y pruebas.

bloque_sumador modulo exclusivo para operaciones aritmeticas.

Testbenches para validacion de cada ALU.

Operaciones soportadas segun la ALU

Transferencia de A

Transferencia de B

A AND B

A OR B

A + B

A + 1

A - 1

A - B

Las ALUs se utilizan para realizar operaciones dentro del CPU y tambien para pruebas independientes.

Registro (Banco de Registros)

Este modulo implementa un register file con dos puertos de lectura y un puerto de escritura.

Funciones principales

Lectura combinacional de Aout y Bout.

Escritura sincrona en flanco ascendente del reloj.

Reset global para limpiar todos los registros.

Direcciones independientes AddrA, AddrB, AddrW.

Entrada Din para escribir un valor.

Señal WE (Write Enable).

El banco de registros provee operandos a la ALU y recibe el resultado para guardarlo.

CPU

Este modulo integra

La ALU usada por el procesador.

El Banco de Registros.

Multiplexores internos y buses.

La Unidad de Control encargada de

Seleccionar registros

Definir la operacion de la ALU

Habilitar la escritura

Controlar el flujo de datos del datapath

El flujo de operacion es

Se leen dos registros desde el Banco de Registros.

La ALU ejecuta la operacion correspondiente.

El resultado vuelve hacia el banco de registros para ser almacenado.

Este CPU es de tipo academico, simple, sin pipeline, y ejecuta instrucciones en un unico ciclo.

Resumen del Funcionamiento del Sistema

El CPU usa el Banco de Registros para leer operandos.

La ALU procesa los datos segun el opcode.

El resultado se escribe en el registro destino.

La Unidad de Control determina todas las señales del datapath.

Estructura General del Proyecto

ALU-main implementaciones de la ALU + testbenches
Registro implementacion del banco de registros
CPU integracion de ALU + Registro + control

Todos los modulos trabajan juntos como un proyecto completo.