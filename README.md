## **Introducción**

### *Contexto*
El monitoreo de la calidad del agua es clave para asegurar la sostenibilidad de los recursos hídricos y proteger el medio ambiente y la salud pública. Este sistema está diseñado para capturar parámetros de la calidad del agua de ríos y arroyos, empleando sensores conectados a hardware asequible, como Arduino y Raspberry Pi. El sistema recopilará datos de parámetros fundamentales, como oxígeno disuelto, turbidez, conductividad, total de sólidos disueltos, pH y temperatura, permitiendo el envío de los datos capturados a un servidor remoto para su análisis y visualización.

### *Objetivos del sistema*
- Generar una solución informática que permita recoger los datos obtenidos por una red de sensores, procesarlos y disponerlos para su análisis.
- Permitir la recolección de datos en tiempo real y su transmisión a un servidor remoto para almacenamiento y análisis.
- Facilitar la visualización de los datos recopilados, proporcionando herramientas para el análisis histórico y la toma de decisiones.

### *Propósito del documento*
El propósito de este documento es establecer las especificaciones de requisitos para el desarrollo del sistema de monitoreo de calidad del agua, asegurando que todas las partes interesadas tengan una comprensión clara de las funcionalidades, restricciones y expectativas del sistema. Este documento servirá como base para:
- **Definir los requisitos funcionales y no funcionales** que guiarán el diseño, desarrollo y operación del sistema.
- **Fomentar una comunicación clara** entre los desarrolladores, los usuarios finales y otros interesados.
- **Establecer criterios de aceptación** que permitan validar el cumplimiento de los objetivos del proyecto.

### *Descripción general de la aplicación*

#### **Visión del sistema**  
El sistema de monitoreo de calidad del agua será una solución integral capaz de capturar, almacenar y enviar datos relacionados con parámetros de calidad del agua. Este sistema estará compuesto por una red de sensores conectados a una unidad de procesamiento (Arduino) y una unidad de transmisión (Raspberry Pi). Los datos se enviarán a un servidor remoto para su almacenamiento y análisis posterior.

#### **Componentes principales del sistema**
1. **Hardware**
   - **Sensores**: Capturarán datos de que permitan determinar el estado de la calidad del agua.
   - **Arduino**: Actuará como controlador para la adquisición de datos de los sensores.
   - **Raspberry Pi**: Almanecará los datos, permitirá configuraciones locales y enviará la información al servidor remoto.

2. **Software**  
   - **Sistema embebido**: Controlará el funcionamiento de los sensores y la comunicación entre Arduino y Raspberry Pi.

#### **Funciones clave del sistema**
- Captura periódica de parámetros de calidad del agua.
- Almacenamiento y procesamiento de datos tanto local como remotamente.

---

## **Especificaciones Técnicas**

### *Requisitos Funcionales*

1. **Adquisición de datos**
   - El sistema debe capturar datos de sensores.
   - Los datos deben ser recogidos con una frecuencia configurable por el usuario (e.g., cada minuto, hora, o día).

2. **Procesamiento de datos**
   - La Raspberry Pi debe procesar los datos recibidos desde el Arduino y organizarlos en un formato estructurado (e.g., JSON).
   - Debe incluir la marca de tiempo asociada a cada medición.

3. **Almacenamiento local**
   - Los datos deben ser almacenados temporalmente en la Raspberry Pi en caso de que no haya conexión con el servidor remoto.
   - Se debe gestionar un límite de almacenamiento local configurable.

4. **Envío de datos al servidor**
   - El sistema debe enviar los datos recopilados al servidor a través de una API REST.
   - El envío debe ser periódico y garantizar la integridad de los datos.

5. **Configuración del sistema**
   - El sistema debe permitir configurar los siguientes parámetros:
     - Frecuencia de captura de datos.
     - Dirección del servidor remoto y protocolo de comunicación.
     - Límite de almacenamiento local.

6. **Monitorización en tiempo real**
   - Debe permitir la visualización en tiempo real de los datos capturados a través de una interfaz gráfica remota.

7. **Autodiagnóstico**
   - El sistema debe verificar periódicamente el estado de los sensores y notificar errores de conexión o mal funcionamiento.

### *Requisitos No Funcionales*

1. **Rendimiento**
   - El sistema debe ser capaz de procesar y enviar los datos de los sensores con un retraso máximo establecido después de la captura.

2. **Escalabilidad**
   - El diseño debe permitir la adición de nuevos sensores en el futuro sin cambios significativos en el sistema.

3. **Seguridad**
   - La comunicación entre la Raspberry Pi y el servidor debe estar protegida mediante encriptación (e.g., HTTPS).

4. **Confiabilidad**
   - Debe garantizar una tasa de operación correcta de al menos el 95% durante un período de 30 días sin reinicio manual.

5. **Compatibilidad**
   - El sistema debe ser compatible con al menos un sistema operativo de servidor estándar (e.g., Ubuntu Server).

6. **Mantenimiento**
   - Los componentes del sistema deben ser fácilmente reemplazables o actualizables.

### *Pila tecnológica*

1. **Hardware**

| Descripción | Modelo/Versión |
| ------------- | -------------- |
| Arduino | UNO |
| Raspberry Pi | 4 Model B |
| Atlas Scientific InterLink | i1 |
| Sonda de oxígeno disuelto Atlas Scientific | ENV-40-DO |
| Sonda de pH de grado de laboratorio Atlas Scientific | ENV-40-pH |
| Sonda de Conductivity Atlas Scientific | ENV-40-EC-K1.0 |
| Sonda de Turbidez DFROBOT| V1.0 |
| Sonda de Total de solidos disueltos DFROBOT| V1.0 |

2. **Software**

| Descripción | Versión |
| ------------- | -------------- |
| Python | 3.12 |
| Arduino Programing Language | --- |
