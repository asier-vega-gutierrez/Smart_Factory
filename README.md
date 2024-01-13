## Desarrollo de aplicación IIoT para reocojida de datos de mauinas
<ul>
    <li>Fechas: Diciembre-Enero 2024</li>
    <li>Descripción: Partiendo de un gemelo digital en Machines Simulator y su programación en un PLC siemens 1500. Se realiza la comunicación vía OPC a un IPC (industrial PC), empleado el servidor OPC KepserverEX, este mapea las entradas del PLC. En este IPC no solo se ubica el servidor OPC, si no también un sistema SCADA (WinCC). Esta parte conforma la red Profinet + OPC en tiempo real de la parte OT de la fábrica.
El servidor IPC también es el encargado de separar las variables booleanas y reales en dos clientes MQTT (el formato de mensajes JSON que genera KepserverEX no tiene en cuenta el tipo de variables se debe separar por clientes). Estos clientes se conectan al servidor MQTT RabbitMQ. Esta parte conforma la transición de la red OT a IT donde ya no se tiene en cuenta el tiempo real.
Mediante dos consumidores MQTT en Telegraf se transfieren los datos a la base de datos de series temporales InfluxDB.Este parte conforma la red IT donde se almacenan los datos para su posterior uso. 
</li>
    <li>Imagen resumen:</li>
</ul>

![foto](https://github.com/asier-vega-gutierrez/SmartFactory/blob/main/net.png)
