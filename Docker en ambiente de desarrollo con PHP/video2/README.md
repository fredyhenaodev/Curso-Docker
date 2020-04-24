# Enlazando contenedores con Docker

Cuando estamos trabajando con múltiples contenedores, es común que necesitemos que estos puedan verse entre sí, ya sea para consultar información de la base de datos, o como hemos visto anteriormente, para interpretar los scripts de PHP, esto puede lograrse en Docker haciendo uso del parámetro **--link** al momento de crear el contenedor. En este post, vamos a ver qué es lo que sucede exactamente cuando hacemos uso de este parámetro.

