# BitSlice CPU – Diseño de Procesador Académico en VHDL

## Descripción General
Este repositorio contiene el diseño completo de un procesador académico basado en arquitectura BitSlice, implementado íntegramente en VHDL. La estructura incluye módulos combinacionales y secuenciales, una Unidad Aritmético-Lógica (ALU) modular, un Banco de Registros estilo RISC y un conjunto de máquinas de estados finitos (FSM), junto con sus bancos de pruebas (testbenches) para verificación funcional.  
El proyecto está orientado a prácticas de Arquitectura de Computadores y Diseño Digital, permitiendo estudiar el datapath, la unidad de control, memoria interna, registros y mecanismos de secuenciación mediante circuitos síncronos.

## Contenido del Proyecto
El repositorio se organiza en tres grandes grupos funcionales:

### 1. Módulos de la CPU
Incluyen los componentes sintetizables que conforman el procesador académico.
• ALU genérica parametrizable capaz de operar con diferentes anchos de palabra.  
• ALU de 4 bits y ALU de 8 bits diseñadas para pruebas específicas.  
• Bloque sumador independiente para integración modular en datapaths.  
• Banco de registros con dos lecturas combinacionales y una escritura síncrona.  
• Módulos secuenciales tales como registros universales, registros en serie, flip-flops T y JK, contadores ascendentes y bidireccionales, todos esenciales para construir módulos internos de la CPU.  

### 2. Máquinas de Estado Finito (FSM)
Incluyen diseños Moore utilizados para implementar controladores secuenciales internos.  
• Módulo Vida: FSM Moore de ocho estados empleada como práctica de control secuencial.  
• MooreCartaASM: Controlador tipo Moore con representación ASM para flujos de validación, carga, confirmación y limpieza.  

### 3. Testbenches
Conjunto de bancos de pruebas no sintetizables usados para verificar componentes.  
• Testbench para ALU de 4 bits con generación automática de estímulos.  
• Testbench para ALU de 8 bits.  
• Testbenches de módulos secuenciales como contadores y registros.  
• Testbench para FSM, diseñado para evaluar transiciones y respuestas.  

## Tecnologías Utilizadas
• Lenguaje VHDL para diseño digital.  
• Arquitectura BitSlice como base del diseño de la ALU y módulos asociados.  
• Modelado funcional, estructural y comportamental.  
• Simulaciones construidas en entornos compatibles con ISE/Xilinx.  

## Instalación
El proyecto puede ejecutarse en cualquier entorno de diseño VHDL.  
Para instalarlo:  
1. Clonar el repositorio utilizando el comando clásico de clonación de repositorios GitHub.  
2. Abrir los archivos VHDL en un entorno compatible como ISE, Vivado o ModelSim.  
3. Importar las carpetas ALU-main y CPU según la estructura mostrada más abajo.  
4. Ejecutar los testbenches para validar el funcionamiento antes de sintetizar.  

## Uso
Para utilizar el proyecto:
1. Seleccionar el módulo a estudiar (ALU, registro, FSM, contador).  
2. Asociarlo a su testbench correspondiente para ver comportamiento.  
3. Ajustar parámetros como el ancho de palabra en la ALU genérica.  
4. Integrar los módulos en un diseño mayor para estudiar datapaths o controladores.  

## Comandos Disponibles
Los comandos típicos de uso en entornos Git y GitHub se aplican para gestionar el repositorio.  
• La clonación se realiza mediante el comando de clonado estándar.  
• La actualización del repositorio usa la función de envío a remoto.  
• Las ramas pueden crearse mediante el comando habitual de creación de ramas.  
• El historial puede revisarse con los comandos de consulta de registros.  
• El etiquetado de versiones se realiza usando las funciones estándar de marcación.  
(Ver guía interna de Git incluida en el proyecto. :contentReference[oaicite:0]{index=0})

## Ejemplos de Aplicación
• Uso de la ALU genérica para probar operaciones aritméticas y lógicas variando el opcode.  
• Construcción de pequeñas arquitecturas RISC combinando Banco de Registros + ALU.  
• Diseño de controladores secuenciales basados en FSM para distintos flujos de tareas.  
• Validación de contadores ascendentes, descendentes y bidireccionales.  
• Integración de registros universales para estudiar el flujo de datos dentro de la CPU.  

## Estructura del Repositorio
La estructura sugerida del repositorio es la siguiente:

## Roadmap
• Añadir una Unidad de Control microprogramada.  
• Crear visualizaciones gráficas del datapath.  
• Implementar un ensamblador simple para generar instrucciones.  
• Extender la ALU con operaciones multiplicativas y desplazamientos.  
• Añadir soporte para interrupciones internas.  

## Contribuciones
Las contribuciones son bienvenidas. Para colaborar:  
1. Clonar el repositorio.  
2. Crear una nueva rama para la funcionalidad deseada.  
3. Documentar claramente los cambios.  
4. Enviar un Pull Request para revisión.  
Pautas extensas de documentación y contribución se describen en la guía incluida. :contentReference[oaicite:1]{index=1}

## Licencia
El proyecto puede distribuirse bajo la licencia elegida por el autor.  
Asegúrate de incluir un archivo de licencia adecuado en el repositorio.

## Autor
Proyecto desarrollado como parte de prácticas de Arquitectura de Computadores y Diseño Digital. El autor mantiene y actualiza el contenido con fines educativos y académicos.
