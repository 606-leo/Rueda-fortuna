# Rueda-fortuna
Rrepositorio proyecto
Pseudocódigo

INICIO

// Estado de la rueda de la fortuna
RUEDA_GIRANDO = FALSO
CABINAS = [VACÍO, VACÍO, VACÍO, ...] // Suponiendo múltiples cabinas

// Función para que un pasajero aborde
FUNCION AbordarCabina()
    SI HAY_CABINA_VACÍA EN CABINAS ENTONCES
        ASIGNAR pasajero A CABINA_VACÍA
        MARCAR CABINA_VACÍA COMO OCUPADA
    FIN_SI
FIN_FUNCION

// Función para iniciar el ciclo de la rueda
FUNCION IniciarCiclo()
    SI RUEDA_GIRANDO ES FALSO Y TODAS_CABINAS_OCUPADAS ENTONCES // O temporizador
        RUEDA_GIRANDO = VERDADERO
        // Lógica para iniciar la rotación de la rueda
    FIN_SI
FIN_FUNCION

// Función para detener el ciclo
FUNCION DetenerCiclo()
    SI RUEDA_GIRANDO ES VERDADERO ENTONCES
        RUEDA_GIRANDO = FALSO
        // Lógica para detener la rotación de la rueda gradualmente
    FIN_SI
FIN_FUNCION

// Función para que un pasajero desaborde
FUNCION DesabordarCabina(cabina)
    MARCAR cabina COMO VACÍA
FIN_FUNCION

// Proceso principal
MIENTRAS haya_pasajeros_esperando O RUEDA_GIRANDO ES VERDADERO
    SI haya_pasajeros_esperando Y haya_cabina_vacía ENTONCES
        AbordarCabina()
    FIN_SI

    SI no haya_cabinas_vacías Y RUEDA_GIRANDO ES FALSO ENTONCES
        IniciarCiclo()
    FIN_SI

    SI ciclo_completo ENTONCES
        DetenerCiclo()
        PARA CADA cabina OCUPADA
            DesabordarCabina(cabina)
        FIN_PARA
    FIN_SI
FIN_MIENTRAS

FIN



propuesta de cómo se vería el diagrama de flujo expandido con la lógica del pseudocódigo:
[Inicio]
    |
    V
[Inicializar: RUEDA_GIRANDO = FALSO, CABINAS = [VACÍO,...]]
    |
    V
[MIENTRAS haya_pasajeros_esperando O RUEDA_GIRANDO ES VERDADERO]
    |
    V
    +-------------------------------------------------------------------+
    |                                                                   |
    |   [SI haya_pasajeros_esperando Y haya_cabina_vacía ENTONCES]        |
    |       |   \
    |      Sí    No
    |       |
    |       V
    |   [Función: AbordarCabina()]
    |       |
    |       V
    +-------+
    |
    V
    +-------------------------------------------------------------------+
    |                                                                   |
    |   [SI no haya_cabinas_vacías Y RUEDA_GIRANDO ES FALSO ENTONCES]     |
    |       |   \
    |      Sí    No
    |       |
    |       V
    |   [Función: IniciarCiclo()]
    |       |
    |       V
    +-------+
    |
    V
    +-------------------------------------------------------------------+
    |                                                                   |
    |   [SI ciclo_completo ENTONCES]                                     |
    |       |   \
    |      Sí    No
    |       |
    |       V
    |   [Función: DetenerCiclo()]
    |       |
    |       V
    |   [PARA CADA cabina OCUPADA]
    |       |
    |       V
    |   [Función: DesabordarCabina(cabina)]
    |       |
    |       V
    +-------+
    |
    V
[Fin del MIENTRAS]
    |
    V
[Fin]


Desglose de los Cambios:
 * Inicio e Inicialización: Se incluye un paso inicial para establecer el estado de la rueda y las cabinas.
 * Bucle Principal (MIENTRAS): El bucle principal del pseudocódigo se representa con un símbolo de proceso que contiene la condición. El flujo regresa al inicio del bucle hasta que la condición sea falsa.
 * Condicionales (SI): Cada estructura SI en el pseudocódigo se convierte en un símbolo de decisión (rombo) con dos posibles salidas ("Sí" y "No") que dirigen el flujo a diferentes procesos.
 * Llamadas a Funciones: Las llamadas a las funciones (AbordarCabina(), IniciarCiclo(), DetenerCiclo(), DesabordarCabina()) se representan con símbolos de proceso.
 * Bucle FOR: El bucle PARA CADA se representa dentro del bloque condicional del SI ciclo_completo.
Este diagrama de flujo ahora visualiza la lógica del pseudocódigo que proporcionaste. Cada estructura de control y llamada a función en el código tiene su representación en el diagrama.
