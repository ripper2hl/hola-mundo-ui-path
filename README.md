# hola-mundo-ui-path

Muestra un mensaje de hola mundo en una ventana de dialogo del sistema operativo

## TODO

* construir con jenkins https://wiki.jenkins.io/display/JENKINS/UiPath+Plugin

* empaquetar con nuget para enviarlo a nexus

----------------------
Jenkins windows slave

* poner un alias al dominio de Jenkins

* agregar el alias del dominio al archivo hosts de windows

* agregar el esclavo jenkins desde la consola web y poner como directorio raiz C:\jenkins

* crear una carpeta en raiz llamada jenkins

* descargar y ejecutar el jar

 - http://jenkins.local:8080/jnlpJars/slave.jar

 - generar el archivo secreto, se obtiene desde la consola web en la configuracion del esclavo

 - java -jar slave.jar -jnlpUrl http://jenkins.local:8080/computer/windows-slave/slave-agent.jnlp -secret @secret-file -workDir "C:\jenkins"

  - no es posible usar el plugin para generar el empaquetado de nuget

  - se debe crear el directorio de los builds
-----------------------
