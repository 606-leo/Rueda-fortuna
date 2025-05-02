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
