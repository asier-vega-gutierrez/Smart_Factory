# Use the official RabbitMQ image with the 3-management tag
FROM rabbitmq:3-management

# Enable the RabbitMQ MQTT plugin
RUN rabbitmq-plugins enable rabbitmq_mqtt

# Expose ports used by RabbitMQ and RabbitMQ Management Plugin
EXPOSE 1883 
EXPOSE 15672 
EXPOSE 5672