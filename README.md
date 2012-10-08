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
			<td>El sistema debe permitir controlar los dispositivos de manera remota.</td>
		</tr>
			<tr>
			<td>R02</td>
			<td>Cada dispositivo debe poder responder con una lista que contenga las URL hacia sus funcionalidades.</td>
		</tr>
		</tr>
			<tr>
			<td>R03</td>
			<td>Los dispositivos deben poder publicar su información a un servidor, de forma automática cada cierto intervalo de tiempo (dependiendo del dispositivo), y en diferentes formatos.</td>
		</tr>
		</tr>
			<tr>
			<td>R04</td>
			<td>El sistema debe permitir comunicarse con un dispositivo en específico mediante un identificador único.</td>
		</tr>
		</tr>
			<tr>
			<td>R05</td>
			<td>Los dispositivos deben alojar un servidor Web.</td>
		</tr>
		</tr>
			<tr>
			<td>R06</td>
			<td>Deben existir roles de usuarios: visitante, administrador y supervisor.</td>
		</tr>
		</tr>
			<tr>
			<td>R07</td>
			<td>Un usuario con rol de visitante sólo deberá poder ver la información de la sala.</td>
		</tr>
		</tr>
			<tr>
			<td>R08</td>
			<td>Un usuario con rol de administrador deberá poder ver la información de la sala.</td>
		</tr>
		</tr>
			<tr>
			<td>R09</td>
			<td>Un usuario con rol de administrador deberá poder configurar la agenda de la sala.</td>
		</tr>
		</tr>
			<tr>
			<td>R10</td>
			<td>Un usuario con rol de supervisor deberá poder ver la información de la sala.</td>
		</tr>
		</tr>
			<tr>
			<td>R11</td>
			<td>Un usuario con rol de supervisor deberá poder configurar la agenda de la sala.</td>
		</tr>
		</tr>
			<tr>
			<td>R12</td>
			<td>Un usuario con rol de supervisor deberá poder configurar los dispositivos que se encuentran en la sala.</td>
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
			<td>El sistema debe exigir autenticación de usuarios, con protocolo de seguridad SSL.</td>
			<td>Seguridad</td>
			<td>Se debe asegurar que los dispositivos no sean modificados por usuarios desconocidos.</td>
		</tr>
		<tr>
			<td>RN6</td>
			<td>El sistema posee una lista de dispositivos conocidos, con los cuales intercambia información.</td>
			<td>Seguridad</td>
			<td>Dispositivos desconocidos no deben participar en el sistema.</td>
		</tr>
		<tr>
			<td>RN7</td>
			<td>El tiempo de recuperación no debe ser mayor a 2 horas.</td>
			<td>Disponibilidad</td>
			<td>Se considera como tiempo razonable para no atentar contra los usuarios, ni el funcionamiento de los demás dispositivos.</td>
		</tr>
	</tbody>
</table>


## 3. Diagrama de componentes


![alt text][diagram]

[diagram]: https://github.com/lhpaul/iBuilding/raw/master/img/package_diagram.png "Diagrama de componentesen "

**Estilos arquitectónicos**
- Cliente Servidor
- 3 Capas (Dispositivo, Servidor, Cliente)


**Conectores**
- (1): Llamada a procedimientos, Parámetros (transferencia de datos)
- (2): Árbitro, Planificación
- (3): Árbitro, Seguridad: Autentificación
