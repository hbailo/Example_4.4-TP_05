# Teclado matricial

## Pines utilizados
Para la lectura de las teclas del teclado se utilizan las siguientes salidas digitales para el manejo de las filas

```cpp
    DigitalOut keypadRowPins[KEYPAD_NUMBER_OF_ROWS] = {PB_3, PB_5, PC_7, PA_15};
```


y las siguientes entradas digitales para el manejo de las columnas

```cpp
    DigitalIn keypadColPins[KEYPAD_NUMBER_OF_COLS]  = {PB_12, PB_13, PB_15, PC_6};
```

## Actualización de la máquina de estados
La máquina de estados para el debouncing de las teclas del teclado se actualiza una vez por ciclo en la llamada a la función `matrixKeypadUpdate` en `alarmDeactivationUpdate`.

## Utilización de la clase Vector de la librería estándar
El cambio a realizar es:

```cpp

    # include <vector>
    std::vector<DigitalOut> keypadRowPins = {PB_3, PB_5, PC_7, PA_15};
    std::vector<DigitalIn> keypadColPins  = {PB_12, PB_13, PB_15, PC_6};
```

# RTC
De acuerdo a la documentación en la placa NUCLEO-F429ZI viene un cristal conectado por al pin Low-Speed Clock (LSE) PC14 y PC15.
Mbed utiliza esta entrada para el manejo del RTC.

El reloj se inicializa con el comando 's' o 'S' enviado por UART desde la PC y se verifica con el comando 't' o 'T'.

Para conservar la cuenta del reloj se debe conectar una batería al pin VBAT.