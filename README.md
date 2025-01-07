## **Introducción**

### *Proposito del documento*
...

### *Descripción general de la aplicación*
...

---

## **Especificaciones Técnicas**

### *Requisitos Funcionales*

1. **Adquisición de datos**
   - El sistema debe capturar datos de los seis sensores: oxígeno disuelto, turbidez, conductividad, total de sólidos disueltos, pH y temperatura.
   - Los datos deben ser recogidos con una frecuencia configurable por el usuario (e.g., cada minuto, hora, o día).

2. **Procesamiento de datos**
   - La Raspberry Pi debe procesar los datos recibidos desde el Arduino y organizarlos en un formato estructurado (e.g., JSON, CSV).
   - Debe incluir la marca de tiempo asociada a cada medición.

3. **Almacenamiento local**
   - Los datos deben ser almacenados temporalmente en la Raspberry Pi en caso de que no haya conexión con el servidor remoto.
   - Se debe gestionar un límite de almacenamiento local configurable.

4. **Envío de datos al servidor**
   - El sistema debe enviar los datos recopilados al servidor remoto utilizando un protocolo estándar (e.g., HTTP/HTTPS, MQTT).
   - El envío debe ser periódico y garantizar la integridad de los datos.

5. **Configuración del sistema**
   - El sistema debe permitir configurar los siguientes parámetros:
     - Frecuencia de captura de datos.
     - Dirección del servidor remoto y protocolo de comunicación.
     - Límite de almacenamiento local.

6. **Alertas y notificaciones**
   - El sistema debe generar alertas si algún sensor detecta valores fuera de rango predefinido.
   - Debe ser posible configurar los umbrales de alerta para cada sensor.

7. **Monitorización en tiempo real**
   - Debe permitir la visualización en tiempo real de los datos capturados a través de una interfaz gráfica remota.

8. **Autodiagnóstico**
   - El sistema debe verificar periódicamente el estado de los sensores y notificar errores de conexión o mal funcionamiento.

### **Requisitos No Funcionales**

1. **Rendimiento**
   - El sistema debe ser capaz de procesar y enviar los datos de los seis sensores con un retraso máximo establecido después de la captura.

2. **Escalabilidad**
   - El diseño debe permitir la adición de nuevos sensores en el futuro sin cambios significativos en el sistema.

3. **Seguridad**
   - La comunicación entre la Raspberry Pi y el servidor debe estar protegida mediante encriptación (e.g., TLS para HTTPS o cifrado en MQTT).

4. **Confiabilidad**
   - Debe garantizar una tasa de operación correcta de al menos el 95% durante un período de 30 días sin reinicio manual.

5. **Compatibilidad**
   - El sistema debe ser compatible con al menos un sistema operativo de servidor estándar (e.g., Ubuntu Server).

6. **Mantenimiento**
   - Los componentes del sistema deben ser fácilmente reemplazables o actualizables.

### **Pila tecnológica**
1. **Hardware**
   - ...

2. **Software**
   - ...

