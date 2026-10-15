# APROVECHA - RESERVA DE EXCEDENTES ALIMENTARIOS

## Miembros del grupo L8-04 

1. Vidal Jiménez, Irene
2. Llamas Marín, Nicolás  

## 1. Introducción al problema

Actualmente, muchos establecimientos, como cafeterías, panaderías y pequeños restaurantes, tienen al final del día excedentes de alimentos que no llegan a venderse y que pueden acabar desperdiciándose. Por otro lado, hay personas que estarían interesadas en comprar estos productos a un precio más económico, pero no siempre conocen qué negocios tienen ofertas disponibles o cuándo pueden recogerlas.

Para dar solución a este problema, se propone 'Aprovecha', una aplicación que permite a los establecimientos ofrecer packs de excedentes alimentarios a un precio reducido y a los clientes consultar y reservar los que les interesen. Cada oferta incluirá información sobre el contenido del pack, los alérgenos, los precios, las unidades disponibles y el horario de recogida.

Además, la aplicación permitirá consultar las reservas y el estado de ellas, organizar las recogidas y conocer la actividad de los establecimientos. El pago se realizará directamente en el negocio cuando el cliente recoja los productos, por lo que no se incluirán pagos en línea ni entregas a domicilio.
        
## 2. Glosario de términos

- **Cancelación:** Anulación de una reserva pendiente antes del inicio de la primera franja de recogida de los packs incluidos.

- **Cliente:** Persona registrada que consulta ofertas, reserva packs y los recoge en el establecimiento.

- **Descripción del contenido:** Información facilitada por el negocio sobre los productos que forman parte de un pack.

- **Establecimiento:** Cafetería, panadería o pequeño restaurante que ofrece sus excedentes mediante la plataforma.

- **Estado de la reserva:** Situación en la que se encuentra una reserva: pendiente, recogida o cancelada.

- **Excedente alimentario:** Producto que no se ha vendido durante la jornada y que el establecimiento considera apto para ofrecer para su consumo.

- **Fecha de recogida:** Día al que corresponde la oferta y en el que se recogerán los packs reservados.

- **Franja de recogida:** Intervalo definido por una hora de inicio y una hora de fin durante el cual se recoge un pack.

- **Historial de reservas:** Conjunto de reservas anteriores y actuales de un cliente.

- **Importe total:** Suma de los importes de todas las líneas de una reserva.

- **Información de alérgenos:** Información proporcionada por el establecimiento sobre los alérgenos de los productos ofrecidos.

- **Línea de reserva:** Registro que relaciona una reserva con un pack e indica su cantidad y precio unitario.

- **Oferta:** Publicación de un pack para una fecha concreta, con un precio, una disponibilidad y una franja de recogida.

- **Pack:** Conjunto de productos que se ofrece como una única unidad de venta.

- **Personal del establecimiento:** Usuarios asociados a un negocio que mantienen sus ofertas y atienden las recogidas.

- **Precio de referencia:** Precio habitual del contenido del pack, indicado por el establecimiento.

- **Precio reducido:** Importe que debe pagar el cliente por una unidad del pack ofrecido.

- **Reserva:** Solicitud confirmada de uno o varios packs de un mismo establecimiento para una misma fecha.

- **Reserva cancelada:** Reserva anulada cuyas unidades se han devuelto a la disponibilidad de las ofertas.

- **Reserva pendiente:** Reserva confirmada que todavía no se ha recogido ni cancelado.

- **Reserva recogida:** Reserva cuyos productos han sido entregados y cuyo importe se ha cobrado.

- **Reseña:** Puntuación y comentario de un cliente sobre una reserva recogida.

- **Tipo de pack:** Clasificación de la oferta: panadería, comida preparada o productos variados.

- **Unidades disponibles:** Cantidad de packs que todavía pueden reservarse.

## 3. Visión general del sistema

### 3.1. Requisitos generales

#### R.G.01. CENTRALIZACIÓN DE OFERTAS

El sistema deberá reunir las ofertas de los establecimientos participantes mediante la entidad Pack, para que los clientes puedan consultar los excedentes alimentarios disponibles y comparar sus características y precios.

#### R.G.02. GESTIÓN DE USUARIOS Y PERMISOS

El sistema deberá distinguir entre clientes, personal de los establecimientos y administradores mediante la información de la entidad Usuario, para que cada tipo de usuario acceda únicamente a las funciones y los datos que le correspondan.

#### R.G.03. CONTROL DE OFERTAS Y DISPONIBILIDAD

El sistema deberá conservar la información de los packs y mantener actualizadas sus unidades disponibles, teniendo en cuenta las reservas y cancelaciones, para evitar que se reserven más unidades de las existentes.

#### R.G.04. GESTIÓN Y SEGUIMIENTO DE RESERVAS

El sistema deberá almacenar la información de las reservas y sus líneas mediante las entidades Reserva y Línea de Reserva, para conocer los packs solicitados, sus cantidades, sus importes y el estado de cada reserva.

#### R.G.05. CONSULTA DE ACTIVIDAD Y VALORACIONES

El sistema deberá permitir consultar la actividad de los establecimientos y las reseñas registradas mediante las entidades Reserva, Línea de Reserva y Reseña, para conocer las unidades entregadas, los importes correspondientes y las valoraciones de los clientes.

### 3.2. Usuarios del sistema
#### 3.2.1. Usuario cliente

El cliente es la persona que utiliza la plataforma para encontrar y reservar packs.

Sus principales necesidades son:

- Conocer los establecimientos participantes.
- Consultar las ofertas disponibles.
- Revisar el contenido y la información de alérgenos.
- Comparar precios.
- Conocer las condiciones de recogida.
- Consultar sus reservas pendientes.
- Revisar su historial.
- Publicar una reseña después de recoger una reserva.

El cliente tendrá acceso al detalle de sus propias reservas.

#### 3.2.2. Usuario personal del establecimiento

El personal está formado por los empleados que utilizan la plataforma en representación de un negocio.

Cada empleado estará asociado a un único establecimiento, que podrá tener varios empleados.

Sus principales necesidades son:

- Mantener la información de las ofertas.
- Consultar las unidades disponibles.
- Identificar las reservas pendientes.
- Consultar los packs y cantidades de cada reserva.
- Registrar las recogidas una vez realizada la entrega y el cobro.
- Consultar la actividad anterior del negocio.

El personal accederá a la información operativa del establecimiento al que pertenece.

#### 3.2.3. Usuario administrador

El administrador supervisa los usuarios y establecimientos de la plataforma.

Sus principales necesidades son:

- Consultar los usuarios registrados.
- Diferenciar los usuarios por rol.
- Identificar el establecimiento asociado a cada empleado.
- Consultar los negocios participantes.
- Revisar la actividad general del sistema.

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales ---> 10 consultas a la base de datos. Consultas que realizan cálculos que aparezcan una de cada una: sum, avg, max, min, count, group by

#### R.F.01. CONSULTA DE ESTABLECIMIENTOS

Como cliente
quiero consultar la información de los negocios participantes mediante la entidad Establecimiento, incluyendo su identificador, nombre comercial, dirección, teléfono y descripción,
para conocer dónde se encuentran y dónde debo recoger los packs que reserve.


#### R.F.02. CONSULTA DE OFERTAS DISPONIBLES

Como cliente
quiero consultar la información de las ofertas mediante la entidad Pack, pudiendo filtrar por establecimiento, fecha de recogida, tipo de pack y precio máximo,
para encontrar packs que se ajusten a mis preferencias.


#### R.F.03. CONSULTA DEL DETALLE DE UNA OFERTA

Como cliente
quiero consultar la información de una oferta mediante la entidad Pack, incluyendo su identificador, nombre, descripción del contenido, información de alérgenos, tipo, precio de referencia, precio reducido, fecha, horario de recogida y unidades disponibles,
para conocer las características del pack antes de reservarlo.


#### R.F.04. CONSULTA DEL HISTORIAL DE RESERVAS

Como cliente
quiero consultar la información de mis reservas mediante la entidad Reserva, pudiendo filtrar por estado y fecha de recogida,
para conocer la situación de mis reservas actuales y anteriores.


#### R.F.05. CONSULTA DEL DETALLE DE UNA RESERVA

Como cliente
quiero consultar la información de mis reservas mediante las entidades Reserva y Línea de Reserva, incluyendo los packs, las cantidades, el precio unitario aplicado y el importe total,
para comprobar qué productos he reservado y qué importe corresponde a cada uno.


#### R.F.06. CONSULTA DE RESERVAS PENDIENTES

Como empleado del establecimiento
quiero consultar las reservas pendientes de mi negocio mediante la entidad Reserva, incluyendo los packs y las cantidades de cada reserva mediante la entidad Línea de Reserva, pudiendo filtrar por fecha de recogida,
para organizar la entrega de los productos.


#### R.F.07. CONSULTA DE OFERTAS Y DISPONIBILIDAD

Como empleado del establecimiento
quiero consultar la información de las ofertas de mi negocio mediante la entidad Pack, incluyendo las unidades disponibles y las ofertas agotadas,
para conocer la disponibilidad de los packs publicados.


#### R.F.08. CONSULTA DEL RESUMEN DE ACTIVIDAD

Como empleado del establecimiento
quiero consultar un resumen de actividad mediante las entidades Reserva y Línea de Reserva, incluyendo las reservas recogidas, las unidades entregadas y los importes entre dos fechas,
para conocer la actividad de mi negocio durante ese periodo.


#### R.F.09. CONSULTA DE RESEÑAS

Como cliente
quiero consultar las valoraciones de los establecimientos mediante la entidad Reseña, incluyendo la puntuación, el comentario y la fecha de publicación,
para conocer las experiencias de otros compradores.


#### R.F.10. CONSULTA DE USUARIOS

Como administrador del sistema
quiero consultar la información de los usuarios registrados mediante la entidad Usuario, pudiendo filtrar por rol e identificar el establecimiento asociado a cada empleado,
para distinguir entre clientes, empleados y administradores y supervisar las cuentas existentes.


#### 4.1.1. Requisitos de información
#### R.I.01 INFORMACIÓN SOBRE USUARIOS  --> quiero almacenar no consultar, 

Como administrador del sistema  
quiero acceder a la información de los usuarios registrados mediante la entidad Usuario, incluyendo su identificador, nombre, apellidos, correo electrónico y rol,  
para poder identificar sus cuentas y distinguir entre clientes, empleados y administradores.

#### R.I.02 INFORMACIÓN SOBRE ESTABLECIMIENTOS

Como cliente  
quiero consultar la información de los negocios participantes mediante la entidad Establecimiento, incluyendo su identificador, nombre comercial, dirección, teléfono y descripción,  
para conocer dónde se encuentran y dónde debo recoger los packs que reserve.

#### R.I.03 INFORMACIÓN SOBRE EL PERSONAL

Como administrador del sistema  
quiero -almacenar del personal de cada establecimiento-consultar la asociación de cada usuario empleado con su establecimiento mediante la relación entre Usuario y Establecimiento,  
para conocer qué personal pertenece a cada negocio y delimitar su acceso a las ofertas y reservas.

#### R.I.04 INFORMACIÓN SOBRE LAS OFERTAS DE PACKS

Como cliente  
quiero consultar la información de las ofertas mediante la entidad Pack, incluyendo su identificador, establecimiento, nombre, descripción del contenido, información de alérgenos, tipo, precio de referencia, precio reducido, fecha, horario de recogida y unidades disponibles,  
para decidir qué packs se ajustan a mis preferencias y conocer sus condiciones antes de reservar.

#### R.I.05 INFORMACIÓN SOBRE RESERVAS

Como empleado del establecimiento  
quiero consultar la información de las reservas de mi negocio mediante la entidad Reserva, incluyendo su identificador, cliente, establecimiento, fecha y hora de realización, fecha de recogida y estado,  
para identificar las reservas recibidas y organizar las entregas pendientes.

#### R.I.06 INFORMACIÓN SOBRE LAS LÍNEAS DE RESERVA  ---> quitar

Como cliente  
quiero consultar los packs incluidos en mis reservas mediante la entidad Línea de Reserva, incluyendo la reserva, el pack, la cantidad y el precio unitario aplicado al confirmar,  
para comprobar qué productos he reservado y qué importe corresponde a cada uno.

#### R.I.07 INFORMACIÓN SOBRE RESEÑAS

Como cliente  
quiero consultar las valoraciones mediante la entidad Reseña, incluyendo su identificador, reserva asociada, puntuación, comentario y fecha de publicación,  
para conocer las experiencias de otros compradores con los establecimientos.

#### R.I.08 INFORMACIÓN SOBRE IMPORTES Y RESUMEN DE ACTIVIDAD  -- requisito funcional quitar de aquí

Como empleado del establecimiento  
quiero consultar los importes de las reservas y el resumen de actividad mediante los datos de Reserva y Línea de Reserva, así como las valoraciones obtenidas mediante Reseña,  
para conocer las unidades entregadas, los importes correspondientes y la puntuación media de mi negocio.



#### 4.1.2. Reglas de negocio  ----> AÑADIR PRUEBAS DE ACEPTACIÓN
#### R.N.01 CORREO ELECTRÓNICO ÚNICO

Como administrador del sistema  
quiero que no se permita registrar dos usuarios con el mismo correo electrónico,  
para evitar cuentas duplicadas y poder identificar a cada usuario.

#### R.N.02 VALIDACIÓN DEL PRECIO REDUCIDO

Como administrador del sistema  
quiero que el precio reducido de cada pack sea mayor que cero y menor que su precio de referencia,  
para garantizar que las ofertas tengan un precio válido e inferior al habitual.

#### R.N.03 VALIDACIÓN DE LA DISPONIBILIDAD

Como empleado del establecimiento  
quiero que las unidades disponibles sean un número entero mayor o igual que cero y que los packs sin unidades no admitan reservas,  
para mantener una disponibilidad válida y evitar reservas de packs agotados.

#### R.N.04 VALIDACIÓN DE LA FRANJA DE RECOGIDA

Como empleado del establecimiento  
quiero que la hora de fin de recogida sea posterior a la hora de inicio y que ambas correspondan a la fecha de la oferta,  
para establecer un intervalo de recogida coherente.

#### R.N.05 VALIDACIÓN DE LA COMPOSICIÓN DE LAS RESERVAS

Como empleado del establecimiento  
quiero que cada reserva contenga al menos una línea, que todos sus packs pertenezcan al mismo establecimiento y fecha de recogida y que un mismo pack no aparezca en varias líneas,  
para organizar correctamente la preparación y entrega de los productos.

#### R.N.06 VALIDACIÓN DE CANTIDADES Y EXISTENCIAS

Como empleado del establecimiento  
quiero que las cantidades reservadas sean números enteros positivos, que no superen las unidades disponibles y que la confirmación de todas las líneas y la reducción de existencias se realicen conjuntamente,  
para evitar reservas sin disponibilidad y cambios parciales en el sistema.

#### R.N.07 CONTROL DEL PLAZO DE RESERVA

Como empleado del establecimiento  
quiero que solo se confirmen reservas antes del inicio de la primera franja de recogida de los packs incluidos,  
para conocer las reservas antes de comenzar las entregas.

#### R.N.08 CONTROL DE LOS ESTADOS DE LAS RESERVAS

Como administrador del sistema  
quiero que las reservas confirmadas comiencen en estado «Pendiente» y que únicamente puedan pasar a «Recogida» o «Cancelada», sin permitir otros estados ni cambios posteriores desde estos dos estados finales,  
para mantener un seguimiento coherente de las reservas.

#### R.N.09 CONTROL DE CANCELACIONES

Como cliente  
quiero poder cancelar únicamente mis reservas pendientes antes del inicio de la primera franja de recogida y que la cancelación devuelva las unidades disponibles una sola vez y de forma conjunta con el cambio de estado,  
para anular una reserva dentro del plazo permitido y permitir que otros clientes reserven esos packs.

#### R.N.10 CONSERVACIÓN DEL PRECIO DE LAS RESERVAS

Como cliente  
quiero que cada línea conserve el precio reducido aplicado al confirmar la reserva, aunque posteriormente cambie el precio de la oferta, y que el total se calcule sumando la cantidad por el precio unitario de cada línea,  
para pagar el importe acordado al realizar la reserva.

#### R.N.11 CONTROL DEL REGISTRO DE RECOGIDAS

Como empleado del establecimiento  
quiero que solo el personal de mi establecimiento pueda marcar sus reservas pendientes como recogidas, una vez confirmadas la entrega de los productos y el cobro del importe,  
para mantener un registro fiable de las entregas realizadas.

#### R.N.12 VALIDACIÓN DE RESEÑAS

Como administrador del sistema  
quiero que solo el cliente titular de una reserva recogida pueda publicar una única reseña sobre ella y que su puntuación sea un número entero entre 1 y 5,  
para que las valoraciones correspondan a compras realizadas y utilicen una escala común.



### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales 


#### R.NF.01 ADAPTACIÓN A DIFERENTES DISPOSITIVOS

Como cliente  
quiero que la interfaz se adapte a ordenadores y teléfonos móviles,  
para consultar las ofertas y mis reservas desde cualquiera de estos dispositivos.

#### R.NF.02 CLARIDAD DE LA INFORMACIÓN

Como cliente  
quiero que los precios, las fechas y los horarios de recogida aparezcan identificados y con un formato uniforme,  
para comprender las condiciones de cada oferta antes de reservar.

#### R.NF.03 IDENTIFICACIÓN VISUAL DE LOS ESTADOS

Como empleado del establecimiento  
quiero que el estado de cada reserva se muestre mediante texto y, opcionalmente, un color que lo acompañe,  
para distinguir las reservas pendientes, recogidas y canceladas sin depender únicamente del color.

#### R.NF.04 MENSAJES COMPRENSIBLES

Como usuario del sistema  
quiero recibir mensajes claros cuando se produzca un error o una consulta no encuentre resultados,  
para entender lo ocurrido y saber cómo continuar.

#### R.NF.05 PROTECCIÓN DE CONTRASEÑAS

Como usuario del sistema  
quiero que mi contraseña se almacene mediante un mecanismo de hash seguro y no aparezca en las consultas,  
para proteger mis credenciales de acceso.

#### R.NF.06 CONTROL DE ACCESO

Como administrador del sistema  
quiero que los permisos de acceso a la información se comprueben en el servidor según el usuario y su rol,  
para proteger las reservas de los clientes y la información operativa de los establecimientos.

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

- con restricciones.

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

-- fin entregable 2 --

## 7. Modelo relacional en 3FN

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.

### 7.1.  Justificación de la estrategia de transformación de jerarquías

- si se identificaron jerarquías en el MC.


### 8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)
- Incluir Reglas de negocio — Constraints/Triggers en las matrices de trazabilidad para el entregable 3

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:-------|:-------|:-------|:-------|:-------|
| TABLA-1 |        |        |        |        |
| TABLA-2 |        |        |        |        |
| TABLA-3 |        |        |        |        |
| TABLA-4 |        |        |        |        |
| TRIG-1 |        |        |        |        |
| TRIG-2 | X      | X      |        | X      |
| TRIG-3 |        | X      |        | X      |
| TRIG-4 |        |        | X      |        |
| CONST-1 |        |        |        |        |
| CONST-2 | X      | X      |        | X      |
| CONST-3 |        | X      |        | X      |
| CONST-4 |        |        | X      |        |

Se consideran todo tipo de constraints declarativas (aquellas definidas durante el CREATE TABLE).
-- fin entregable 3 --

## Referencias


