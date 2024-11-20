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
