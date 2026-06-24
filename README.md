### ¿Como usar Auri.exe?:
1. Asegurarse de tener un micrófono y parlante predeterminado en la computadora.
2. Descargar y abrir **Auri.exe**
3. Decir "Auri" y esperar el sonido de activación.
4. Realizar cualquier consulta.

------------------------------------------------------------------------------------------------------------------------------------------------------

**Auri** fue un proyecto de egreso para la **Escuela Técnica El Pinar (UTU)** en mi segundo año de bachillerato. Era un asistente virtual, diseñado para interactuar mediante voz y funcionar tanto en un entorno de computadora como en un sistema físico.

El proyecto se estructuró en dos aplicaciones principales: **Auri.py** y **Server.py (Obsoleto)**

### Auri.py
Es una versión de escritorio diseñada para ejecutarse directamente en una computadora. Esta versión tiene captura de audio, procesamiento y reproducción de respuestas en un único entorno, usé librerías como Vosk para reconocimiento de voz, gTTS para síntesis de audio y la API de Mistral para la generación de respuestas mediante un agente personalizado usando inteligencia artificial. También usé sounddevice para la entrada de audio y pygame para la salida.

### Server.py
Fue desarrollado para un sistema físico usando ESP32. En este sistema el ESP32 actúa como cliente capturando audio mediante un micrófono I2S y enviándolo a Server.py a través de una conexión TCP. El servidor procesa el audio detectando palabras clave, este hace una consulta a Mistral y genera una respuesta con el mismo sistema que Auri.py, luego esta respuesta se envia nuevamente al dispositivo en forma de audio y se reproduce mediante un parlante.

Para la comunicación entre el ESP32 y el servidor usé TCP para streaming en tiempo real de audio, UDP para descubrimiento automático del servidor en la red local, y HTTP para la distribución de archivos de audio en formato WAV. Además usé Zeroconf (mDNS) para facilitar la detección del servicio sin configuración manual de IP's.

El sistema final tenía procesamiento de audio en tiempo real y control de estados de interacción mediante señales de audio (sonidos de activación y finalización).

Como parte de distribución del proyecto, la versión de escritorio (Auri.py) la compilé en un archivo ejecutable (.exe) usando PyInstaller el cual se puede seguir usando hoy en día. Hacer esto permite su uso en cualquier computadora de manera intuitiva sin necesidad de instalar dependencias adicionales.

Por último la arquitectura de cliente (ESP32) y el servidor (Server.py) quedó obsoleto por su mayor complejidad, dependencia de red y menor practicidad en comparación con la versión de escritorio, únicamente se usó para la presentación final del proyecto.

### Desarrollo de todo el proyecto: 
~6 meses

### Video demostrativo: 
https://github.com/user-attachments/assets/17aaace7-e226-4a94-91dd-c7959dbb14ec
