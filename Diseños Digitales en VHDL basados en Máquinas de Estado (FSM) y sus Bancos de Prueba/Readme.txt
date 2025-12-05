README – Proyecto de Máquinas de Estado y Testbenches en VHDL

Descripción General del Proyecto
Este proyecto contiene varios diseños digitales desarrollados en VHDL. Todos se basan en Máquinas de Estados Finitos (FSM) y se acompañan de sus respectivos bancos de prueba (testbenches) para simulación. El objetivo principal es modelar, controlar y verificar comportamientos secuenciales mediante lógica digital.

Los códigos se agrupan en dos grandes categorías:
• Módulos sintetizables: Implementan la lógica real de máquinas de estado.
• Testbenches: Se usan exclusivamente para simulación y no son sintetizables.

El proyecto incluye ejemplos de control secuencial, procesos de decisión por estados y verificación temporal mediante estímulos.

Componentes del Proyecto

A) Máquinas de Estado (FSM) – Códigos sintetizables
Estos módulos representan diseños que pueden implementarse en hardware FPGA.

Módulo "Vida"
• Implementa una máquina de estados tipo Moore.
• Contiene 8 estados: A, B, C, D, E, F, G, H.
• Gestiona señales de entrada como DEBER, DM1, SUBIRO_O_CAMBIAR, SUBIDOEXITOSAMENTE y CAMBIADOEXITOSAMENTE.
• Genera salidas de control: LIMPIA, SUBIDO, CAMBIO, INGRESADEBER, DEBERENTREGADO, y la codificación del estado mediante Q2, Q1, Q0.
• Usa dos procesos: uno para la transición de estados y otro para el registro del estado con reloj.

Módulo "MooreCartaASM"
• No se muestra la lógica interna aquí, pero por su nombre corresponde a una máquina de estado tipo Moore basada en diagramas ASM (Algorithmic State Machine).
• Es un controlador secuencial que depende de entradas como tiempo, sensor y señales de control.

Módulo "alarma"
• Es un tercer módulo secuencial (FSM o lógica combinacional/secuencial).
• Sus detalles no están incluidos pero se proporciona testbench para verificación.

B) Testbenches (Códigos de simulación no sintetizables)
Los testbenches sirven para verificar el funcionamiento de los módulos sintetizables mediante estímulos temporales.

Testbench para "alarma"
• Genera un reloj.
• Instancia el módulo "alarma".
• Permite aplicar estímulos manuales en la fase "stimulus process".

Testbench para "MooreCartaASM"
• Crea señales de prueba: tiempo, sensor, Sp, clk.
• Permite observar salidas como PA, PC, PARO, AVANCE.
• Incluye señales bidireccionales Q1 y Q0 que representan la codificación del estado.

Testbench para "Vida"
• Genera un reloj y aplica estímulos en tiempos específicos mediante la cláusula "after".
• Prueba las secuencias completas del funcionamiento de la máquina de estado "Vida".
• Permite observar comportamientos de limpieza, subida, cambio e ingreso de deberes.

Objetivo Académico y Técnico
Este conjunto de códigos permite estudiar y practicar:
• Diseño de máquinas de estados Moore.
• Implementación de controladores secuenciales sintetizables en FPGA.
• Simulación y verificación mediante testbenches.
• Manejo de señales temporales, procesos de reloj y transición de estados.
• Codificación binaria de estados.
• Relación entre entradas, estados y salidas.

Es un proyecto ideal para cursos de sistemas digitales, electrónica digital e introducción a diseño con HDL.

Estructura del Proyecto
• /Vida/ → Contiene el módulo FSM "Vida" y su testbench.
• /MooreCartaASM/ → Testbench y componente declarado para simulación.
• /alarma/ → Testbench para el módulo "alarma".

Cada carpeta incluye:
• Entidad VHDL
• Arquitectura
• Testbench correspondiente (si aplica)

Uso del Proyecto

Abrir cada archivo en el entorno Xilinx ISE o ModelSim.

Para simular:
– Seleccionar el archivo Testbench.
– Compilar el módulo y el testbench asociados.
– Ejecutar la simulación temporal.

Verificar los cambios de estado, las salidas y el comportamiento esperado del sistema.

Ajustar tiempos o estímulos según sea necesario.
