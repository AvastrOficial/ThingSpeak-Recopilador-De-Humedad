# Proyecto de Sensores IoT con ThingSpeak y ESP32

Este proyecto utiliza un ESP32 para leer datos de temperatura, humedad y presión de los sensores DHT22 y BMP280. Los datos se envían a la plataforma en la nube **ThingSpeak**, y un **buzzer** se activa si se detectan condiciones de alerta (temperatura o humedad excesivas).

## Componentes Utilizados

- **ESP32**: Microcontrolador con WiFi integrado.
- **Sensor DHT22**: Sensor de temperatura y humedad.
- **Sensor BMP280**: Sensor de presión barométrica.
- **Buzzer**: Genera una señal sonora cuando las condiciones de temperatura o humedad exceden ciertos umbrales.
- **ThingSpeak**: Plataforma para almacenar y visualizar los datos de sensores en tiempo real.

## Funcionamiento

1. **Conexión Wi-Fi**: El ESP32 se conecta a la red Wi-Fi configurada en el código.
2. **Lectura de Sensores**: Se leen cada 2 segundos los valores de temperatura, humedad y presión.
3. **Activación de Alerta**: Si la temperatura es mayor o igual a 27°C o la humedad es mayor o igual a 75%, se activa el buzzer y se muestra una alerta en la consola serial.
4. **Envío de Datos a ThingSpeak**: Los datos se envían a la plataforma ThingSpeak cada 14 segundos.

## Requisitos

- **Bibliotecas necesarias**:
  - `ThingSpeak` (para enviar datos a ThingSpeak)
  - `WiFi` (para conectarse a la red Wi-Fi)
  - `DHT` (para trabajar con el sensor DHT22)
  - `Adafruit_BMP280` (para trabajar con el sensor BMP280)
  - `Wire` (para la comunicación I2C con el BMP280)

## Conexión de los Componentes

- **DHT22**:
  - Pin de datos: Pin 32 (configurado como `pin2` en el código)
  
- **BMP280**:
  - SDA: Pin 21
  - SCL: Pin 22

- **Buzzer**:
  - Pin: Pin 19

## Configuración de ThingSpeak

1. Crea una cuenta en [ThingSpeak](https://thingspeak.com/).
2. Crea un nuevo canal y copia el `Channel ID` y el `Write API Key`.
3. Reemplaza los valores de `channelID` y `WriteAPIKey` en el código con tus credenciales de ThingSpeak.
![image](https://github.com/user-attachments/assets/35a25bac-58af-4668-91e9-289e4bec4e59)

![image](https://github.com/user-attachments/assets/63c1b395-908c-4f75-afbf-c2dcdb990c3e)

