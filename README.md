# computaci-n_nube
este repositorio es requisito de la asignatura computación en la nube

Descripción del Proyecto
Este proyecto tiene como objetivo implementar un sistema de balanceo de carga utilizando HAProxy, gestionando las peticiones a dos servidores web que corren en contenedores LXD dentro de máquinas virtuales Vagrant. Además, se incorporará un sistema de manejo de fallas y servidores de backup para garantizar la alta disponibilidad y la capacidad de respuesta bajo diferentes cargas de tráfico utilizando JMeter para las pruebas.
Requerimientos Generales
Balanceo de Carga: Las peticiones no se realizan directamente a los servidores web, sino que el balanceador de carga HAProxy decidirá qué servidor procesará la petición.
Servidores Web: Dos servidores correrán exclusivamente Apache.
Interfaz de Usuario: La GUI de HAProxy será accesible desde la máquina anfitriona para visualizar el estado y estadísticas de los servidores web.
Contenedores LXD: Cada máquina virtual Vagrant debe correr al menos un contenedor LXD.
HAProxy en Contenedor: HAProxy debe operar en un contenedor LXD separado.
Implementación del Cluster LXD
Configuración
Clustering LXD: Seguir la documentación oficial de LXD para clustering disponible en LXD Clustering Documentation.
Videos Tutoriales: Para una guía visual, revisar los videos de YouTube:
LXD Clustering Explained – Part 1
LXD Clustering Explained – Part 2
Pasos
Configurar Vagrant para iniciar las máquinas virtuales necesarias.
Instalar y configurar LXD en cada máquina virtual.
Crear un cluster LXD siguiendo las instrucciones proporcionadas en la documentación y videos.
Manejo de la Disponibilidad y Pruebas de Carga con JMeter
Requisitos de Disponibilidad
Servidores de Backup: Mantener servidores de respaldo que puedan entrar en operación en caso de alta demanda o falla total de los servidores en producción.
Página de Error Personalizada: HAProxy debe mostrar una página personalizada en caso de que ningún servidor esté disponible.
Configuración de HAProxyConfigurar HAProxy para detectar la caída de servidores y redirigir el tráfico a los servidores de backup.
Personalizar las páginas de error para mostrar mensajes adecuados en caso de errores.
Pruebas de Carga con JMeter
Configurar JMeter para simular diferentes cargas de tráfico.
Realizar pruebas para evaluar la respuesta del sistema bajo diferentes escenarios de carga.
Ajustar la configuración del sistema basado en los resultados de las pruebas para optimizar el rendimiento y la disponibilidad.
Conclusión 
Este microproyecto proporcionará un entorno robusto para el manejo de aplicaciones web con alta disponibilidad y capacidad de respuesta bajo diversas condiciones de carga, utilizando tecnologías modernas como LXD, HAProxy y JMeter en un entorno controlado por Vagrant.

Requisitos
Vagrant
LXD/LXC
HAProxy (en un contenedor LXD)
Apache (en contenedores LXD)
JMeter para pruebas de carga
Pasos para la Implementación
1. Configuración de Vagrant
Primero, se necesita configurar Vagrant para crear y gestionar las máquinas virtuales necesarias. Cada máquina virtual funcionará como un nodo en el cluster LXD.

2. Instalación y Configuración de LXD en cada VM
Después de iniciar las máquinas virtuales, instale y configure LXD en cada una de ellas.

3. Creación del Cluster LXD
Una vez que LXD esté instalado en todas las VMs, proceda a configurar el cluster.

. Despliegue de Contenedores LXD para Apache y HAProxy
Cree contenedores LXD en los nodos del cluster para ejecutar los servicios Apache y HAProxy.

5. Configuración de HAProxy para Balanceo de Carga
Configure HAProxy para balancear las cargas entre los servidores web.

6. Pruebas de Carga con JMeter
Finalmente, realice pruebas de carga con JMeter para asegurarse de que el sistema puede manejar el tráfico esperado y responder adecuadamente bajo carga.

Documentación
Documente todos los pasos, configuraciones y resultados de las pruebas para asegurar que el sistema es reproducible y para facilitar la resolución de problemas en el futuro.
