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


## 2. Requisitos no funcionales

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


###### Trabajo en conjunto de todo el grupo
