Proyecto iBuilding
==================


## 1. Requisitos funcionales

<table>
	<thead>
		<tr>
			<th>Requisito</th>
			<th>Descripción</th>
		</tr>		
	</thead>
	<tbody>
		<tr>
			<td>R01</td>
			<td>Los dispositivos deben alojar un servidor Web.</td>
		</tr>
		<tr>
			<td>R02</td>
			<td>El sistema debe permitir comunicarse con un dispositivo en específico mediante un identificador único.</td>
		</tr>
		<tr>
			<td>R03</td>
			<td>El sistema debe permitir controlar los dispositivos mediante una interfaz web.</td>
		</tr>
		<tr>
			<td>R04</td>
			<td>Cada dispositivo debe poder responder con una lista que contenga las URL hacia sus funcionalidades.</td>
		</tr>
		<tr>
			<td>R05</td>
			<td>Los dispositivos deben alojar un servidor Web.</td>
		</tr>
		<tr>
			<td>R06</td>
			<td>Deben existir roles de usuarios: visitante, administrador y supervisor.</td>
		</tr>
		<tr>
			<td>R07</td>
			<td>Todos usuarios deben poder ver la agenda de la sala mediante el dispositivo panel o algún cliente Web conectado a Internet.</td>
		</tr>
		<tr>
			<td>R08</td>
			<td>Los usuarios con rol de administrador y/o supervisor deben poder configurar la agenda de la sala mediante el dispositivo panel o algún cliente Web conectado a Internet.</td>
		</tr>
		<tr>
			<td>R09</td>
			<td>Los usuarios con rol de supervisor deben poder configurar los dispositivos mediante el dispositivo panel o algún cliente Web conectado a Internet.</td>
		</tr>
		<tr>
			<td>R10</td>
			<td>El sistema debe permitir configurar y administrar los permisos de usuario.</td>
		</tr>
		<tr>
			<td>R11</td>
			<td>El sistema debe permitir configurar y administrar la BD.</td>
		</tr>
		<tr>
			<td>R12</td>
			<td>El sistema debe permitir la configuracion y administracion de la simulación de dispositivos.</td>
		</tr>
		<tr>
			<td>R13</td>
			<td>El sistema debe permitir monitoreo y logging de su funcionamiento.</td>
		</tr>
	</tbody>
</table>


## 2.0 Requisitos no funcionales

<table>
	<thead>
		<tr>
			<th>Requisito</th>
			<th>Descripción</th>
			<th>Tipo</th>
			<th></th>
		</tr>		
	</thead>
	<tbody>
		<tr>
			<td>RN1</td>
			<td>El sistema debe poder soportar al menos 200 dispositivos.</td>
			<td>Escalabilidad</td>
			<td>Cantidad estimada por el cliente, de dispositivos en el sistema.</td>
		</tr>
		<tr>
			<td>RN2</td>
			<td>El sistema debe poder extenderse a  23 pisos.</td>
			<td>Escalabilidad</td>
			<td>Escalabilidad esperada por el cliente.</td>
		</tr>
		<tr>
			<td>RN3</td>
			<td>Todos los dispositivos se comunican con el servidor a través de un misma interfaz, para permitir integrar nuevos dispositivos.</td>
			<td>Flexibilidad</td>
			<td>Debe ser fácil lograr incorporar un dispositivo nuevo al sistema.</td>
		</tr>
		<tr>
			<td>RN4</td>
			<td>El servidor se comunica con los dispositivos utilizando una API REST.</td>
			<td>Flexibilidad y Escalabilidad</td>
			<td>Permite incorporar dispositivos fácilmente con operaciones estándar y recursos identificados.</td>
		</tr>
		<tr>
			<td>RN5</td>
			<td>El sistema posee una lista de dispositivos conocidos, con los cuales intercambia información.</td>
			<td>Testeabilidad</td>
			<td>Se considera como porcentaje razonable para el desarrollo del sistema.</td>
		</tr>
		<tr>
			<td>RN6</td>
			<td>El sistema posee una lista de dispositivos conocidos, con los cuales intercambia información.</td>
			<td>Seguridad</td>
			<td>Dispositivos desconocidos no deben participar en el sistema.</td>
		</tr>
		<tr>
			<td>RN7</td>
			<td>El sistema debe exigir autenticación de usuarios, con protocolo de seguridad SSL.</td>
			<td>Seguridad</td>
			<td>Se debe asegurar que los dispositivos no sean modificados por usuarios desconocidos.</td>
		</tr>	
        <tr>
			<td>RN8</td>
			<td>El sistema debe permitir ser configurado por el administrador.</td>
			<td>Configurabilidad</td>
			<td>Es necesario para poder configurar el sistema y probar</td>
		</tr>
        <tr>
			<td>RN9</td>
			<td>El tiempo de recuperación no debe ser mayor a 2 horas.</td>
			<td>Disponibilidad</td>
			<td>Se considera como tiempo razonable para no atentar contra los usuarios, ni el funcionamiento de los demás dispositivos.</td>
		</tr>
        <tr>
			<td>RN10</td>
			<td>El sistema debe permitir mantenibilidad por parte de usuarios administradores, permitiendo agregar o modificar datos de configuración al sistema.</td>
			<td>Mantenibilidad</td>
			<td>Necesario para los cambio futuros del sistema.</td>
		</tr>
	</tbody>
</table>

## 2.1 Árbol de Utilidad

![alt_text][diagram0]

[diagram0]: https://github.com/lhpaul/iBuilding/raw/master/img/DiagramaUtilidad.png "Diagrama de Utilidad"

## 3. Diagrama de componentes


![alt text][diagram1]

[diagram1]: https://github.com/lhpaul/iBuilding/raw/master/img/package_diagram.png "Diagrama de componentes"

**Estilos arquitectónicos**
- Cliente Servidor
- 3 Capas (Dispositivo, Servidor, Cliente)


**Conectores**
- (1): Llamada a procedimientos, Parámetros (transferencia de datos)
- (2): Árbitro, Planificación
- (3): Árbitro, Seguridad: Autentificación
- (4): Acceso a datos (disponibilidad persistente)

---

## 4. Diagrama de Deployment


![alt text][diagram2]

[diagram2]: https://github.com/lhpaul/iBuilding/raw/master/img/DiagramaDeployment.png "Diagrama de Deployment"

## 5. Identificación de Riesgos, Puntos Sensibles y Trade‐Offs

**Identificación de Riesgos**
Al momento de tomar las decisiones arquitectónicas, se generan distintas problemáticas que pueden generar conflictos. Por un lado se genera un riesgo al generar un componente común con su respectiva interfaz para todos los dispositivos,  considerando la diversidad de estos, y los distintos niveles de complejidad hay decidir abstraerse por una interfaz, sin embargo, ¿Con que nivel de profundidad se debe generar?  
Por otro lado está el tema de los componentes que podrían verse afectado al momento de escalar. El servidor debe ser capaz de procesar gran cantidad de información por ende el “Controlador dispositivo” y su respectivo conector con la API de data-in deben ser identificados como un factor de riesgo claro.  En este caso, la capacidad de leer información, va verse restringida por el ancho de banda y por la cantidad máxima de request, sin embargo hay que tener en cuenta posibles opciones de replicar esta lógica de modo de procesar información simultánea.

**Puntos Sensibles**
- Escalabilidad: capacidad de aumentar los request sin que el servidor colapse y pierda datos.
- Flexibilidad: Elegir una interfaz común para todos los dispositivos,  que no sea necesario hacer cambios cada vez que se quiera agregar un tipo de dispositivo nuevo.
- Seguridad: Los datos deben ser de los dispositivos inscritos y no de dispositivos ajenos al sistema. Por otro lado el control de los dispositivos debe ser restringido, es de suma importancia que los dispositivos no sean manipulados externamente sin autorización. 

**TradeOffs** 
La complejidad se va a ver afectada claramente con las decisiones tomadas tanto en escalabilidad, flexibilidad y seguridad. Por un lado, en caso que se desee escalar ocupando replicaciones, claramente va a generarse mayor complejidad debido a tener que coordinar distintos componentes en paralelo que procesan información y modifican la base de datos de manera concurrente. 
En el caso de la flexibilidad también hay un trade-off con complejidad ya que a medida que aumento la flexibilidad de los dispositivos, más complejo va a ser mi componente dispositivo. 
El aumentar la seguridad va a afectar por un lado la escalabilidad, debido a que protocolos de seguridad más complejos involucran una sobrecargar mayor en el servidor y a su vez un aumento de complejidad.  

 


###### Trabajo en conjunto de todo el grupo
