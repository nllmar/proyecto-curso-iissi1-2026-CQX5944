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
### 4.1. Requisitos funcionales

#### R.F.01. CONSULTA DE ESTABLECIMIENTOS

Como cliente  
quiero consultar la información de los negocios participantes mediante la entidad Establecimiento, incluyendo su identificador, nombre comercial, dirección, teléfono y descripción,  
para conocer dónde se encuentran y dónde debo recoger los packs que reserve.

#### R.F.02. CONSULTA DE OFERTAS DISPONIBLES

Como cliente  
quiero consultar las ofertas de packs con unidades disponibles y cuyo plazo de reserva no haya terminado, pudiendo filtrar por establecimiento, fecha de recogida, tipo de pack y precio máximo,  
para encontrar packs que se ajusten a mis preferencias.

#### R.F.03. CONSULTA DEL DETALLE DE UNA OFERTA

Como cliente  
quiero consultar la información de una oferta mediante la entidad Pack, incluyendo su identificador, establecimiento, nombre, descripción del contenido, información de alérgenos, tipo, precio de referencia, precio reducido, fecha de recogida, horario de recogida y unidades disponibles,  
para conocer las características del pack antes de reservarlo.

#### R.F.04. CONSULTA DEL HISTORIAL DE RESERVAS

Como cliente  
quiero consultar mis reservas, incluyendo su identificador, establecimiento, fecha y hora de realización y estado, pudiendo filtrar por estado y fecha de recogida de los packs incluidos,  
para conocer la situación de mis reservas actuales y anteriores.

#### R.F.05. CONSULTA DEL DETALLE DE UNA RESERVA

Como cliente  
quiero consultar el detalle de una de mis reservas mediante Reserva, Pack y Línea de Reserva, incluyendo los packs, sus cantidades, el precio unitario aplicado, el importe de cada línea y el importe total calculado como la suma de los importes de sus líneas,  
para comprobar qué productos he reservado y cuánto debo pagar.

#### R.F.06. CONSULTA DE RESERVAS PENDIENTES

Como empleado del establecimiento  
quiero consultar las reservas pendientes de mi negocio, incluyendo el cliente, los packs y sus cantidades, pudiendo filtrar por la fecha de recogida de los packs incluidos,  
para organizar la entrega de los productos.

#### R.F.07. CONSULTA DE DISPONIBILIDAD Y RANGO DE PRECIOS

Como empleado del establecimiento  
quiero consultar, para una fecha de recogida, la suma de las unidades disponibles y el precio reducido mínimo y máximo de las ofertas de mi negocio, agrupando los resultados por tipo de pack e incluyendo las ofertas agotadas,  
para conocer la disponibilidad total y el rango de precios de cada tipo de pack.

#### R.F.08. CONSULTA DEL RESUMEN DE ACTIVIDAD

Como empleado del establecimiento  
quiero consultar, entre dos fechas de recogida, el número de reservas recogidas, la suma de las unidades entregadas y la suma de sus importes, agrupando los resultados por fecha de recogida,  
para conocer la actividad diaria de mi negocio durante ese periodo.


#### R.F.09. CONSULTA DE RESEÑAS Y PUNTUACIÓN MEDIA

Como cliente  
quiero consultar las reseñas de un establecimiento, incluyendo su puntuación, comentario y fecha de publicación, junto con la puntuación media de sus reseñas,  
para conocer las experiencias de otros compradores y la valoración general del negocio.

#### R.F.10. CONSULTA DE USUARIOS

Como administrador del sistema  
quiero consultar los usuarios registrados, incluyendo su identificador, nombre, apellidos, correo electrónico y tipo de usuario, pudiendo filtrar entre clientes, empleados y administradores e identificar el establecimiento asociado a cada empleado,  
para supervisar las cuentas existentes.



#### 4.1.1. Requisitos de información
#### 4.1.1. Requisitos de información

#### R.I.01 INFORMACIÓN SOBRE USUARIOS

Como administrador del sistema  
quiero almacenar la información de los usuarios mediante la entidad Usuario, incluyendo su identificador, nombre, apellidos, correo electrónico y contraseña almacenada de forma protegida, distinguiendo entre los tipos Cliente, Empleado y Administrador mediante la herencia,  
para identificar sus cuentas y conservar los datos de los participantes en la plataforma.

#### R.I.02 INFORMACIÓN SOBRE ESTABLECIMIENTOS

Como administrador del sistema  
quiero almacenar la información de los negocios participantes mediante la entidad Establecimiento, incluyendo su identificador, nombre comercial, dirección, teléfono y descripción,  
para mantener un registro de los establecimientos que ofrecen packs y de sus datos de contacto y recogida.

#### R.I.03 INFORMACIÓN SOBRE EL PERSONAL

Como administrador del sistema  
quiero almacenar la asociación de cada empleado con el establecimiento al que pertenece mediante la relación entre Empleado y Establecimiento, conservando sus datos personales a través de los atributos heredados de Usuario,  
para identificar al personal de cada negocio y delimitar su acceso a las ofertas y reservas.

#### R.I.04 INFORMACIÓN SOBRE LAS OFERTAS DE PACKS

Como empleado del establecimiento  
quiero almacenar la información de las ofertas de mi negocio mediante la entidad Pack, incluyendo su identificador, establecimiento, nombre, descripción del contenido, información de alérgenos, tipo, precio de referencia, precio reducido, fecha de recogida, hora de inicio, hora de fin y unidades disponibles,  
para conservar las características de los packs ofrecidos y sus condiciones de venta y recogida.

#### R.I.05 INFORMACIÓN SOBRE RESERVAS

Como empleado del establecimiento  
quiero almacenar la información de las reservas mediante la entidad Reserva, incluyendo su identificador, cliente, establecimiento, fecha y hora de realización y estado, así como los packs incluidos, sus cantidades y los precios unitarios aplicados mediante la clase de asociación Línea de Reserva,  
para conservar los productos solicitados y las condiciones acordadas al confirmar cada reserva.

#### R.I.06 INFORMACIÓN SOBRE RESEÑAS

Como cliente  
quiero almacenar mi valoración de una reserva recogida mediante la entidad Reseña, incluyendo su identificador, reserva asociada, puntuación, comentario opcional y fecha de publicación,  
para dejar constancia de mi experiencia con el establecimiento.

#### 4.1.2. Reglas de negocio  
#### R.N.01 CORREO ELECTRÓNICO ÚNICO

Como administrador del sistema  
quiero que no se permita registrar dos usuarios con el mismo correo electrónico,  
para evitar cuentas duplicadas y poder identificar a cada usuario.

-> **Pruebas de aceptación**

- Comprobar que se permite registrar un usuario con un correo no utilizado.
- Verificar que se rechaza un correo ya registrado, aunque el nuevo usuario sea de otro tipo.

#### R.N.02 VALIDACIÓN DEL PRECIO REDUCIDO

Como administrador del sistema  
quiero que el precio reducido de cada pack sea mayor que cero y menor que su precio de referencia,  
para garantizar que las ofertas tengan un precio válido e inferior al habitual.

-> **Pruebas de aceptación**

- Comprobar que se acepta un precio reducido de 5 € cuando el precio de referencia es de 10 €.
- Verificar que se rechaza un precio reducido menor o igual que cero, o igual o superior al precio de referencia.


#### R.N.03 VALIDACIÓN DE LA DISPONIBILIDAD

Como empleado del establecimiento  
quiero que las unidades disponibles sean un número entero mayor o igual que cero y que los packs sin unidades no admitan reservas,  
para mantener una disponibilidad válida y evitar reservas de packs agotados.

-> **Pruebas de aceptación**

- Comprobar que se acepta una disponibilidad de cero unidades, pero no se permiten reservas de ese pack.
- Verificar que se rechazan disponibilidades negativas o no enteras.


#### R.N.04 VALIDACIÓN DE LA FRANJA DE RECOGIDA

Como empleado del establecimiento  
quiero que la hora de fin de recogida sea posterior a la hora de inicio y que ambas correspondan a la fecha de la oferta,  
para establecer un intervalo de recogida coherente.

-> **Pruebas de aceptación**

- Comprobar que se acepta una franja de 19:00 a 20:00 para la fecha de recogida.
- Verificar que se rechaza una hora de fin igual o anterior a la hora de inicio.


#### R.N.05 VALIDACIÓN DE LA COMPOSICIÓN DE LAS RESERVAS

Como empleado del establecimiento  
quiero que cada reserva contenga al menos una línea, que todos sus packs pertenezcan al mismo establecimiento y fecha de recogida y que un mismo pack no aparezca en varias líneas,  
para organizar correctamente la preparación y entrega de los productos.

-> **Pruebas de aceptación**

- Comprobar que se acepta una reserva con packs diferentes del mismo establecimiento y fecha, si cumple las demás reglas.
- Verificar que se rechaza una reserva sin líneas, con packs repetidos o con packs de distintos establecimientos o fechas.


#### R.N.06 VALIDACIÓN DE CANTIDADES Y EXISTENCIAS

Como empleado del establecimiento  
quiero que las cantidades reservadas sean números enteros positivos, que no superen las unidades disponibles y que la confirmación de todas las líneas y la reducción de existencias se realicen conjuntamente,  
para evitar reservas sin disponibilidad y cambios parciales en el sistema.

-> **Pruebas de aceptación**

- Comprobar que reservar 2 unidades de un pack con 5 disponibles confirma la reserva y deja 3 unidades.
- Verificar que, si alguna línea tiene una cantidad no válida o superior a la disponibilidad, se rechaza toda la reserva sin modificar las existencias.


#### R.N.07 CONTROL DEL PLAZO DE RESERVA

Como empleado del establecimiento  
quiero que solo se confirmen reservas antes del inicio de la primera franja de recogida de los packs incluidos,  
para conocer las reservas antes de comenzar las entregas.

-> **Pruebas de aceptación**

- Comprobar que se permite confirmar una reserva antes del inicio de la primera franja de recogida de sus packs.
- Verificar que se rechaza la confirmación al comenzar esa franja o después, teniendo en cuenta la fecha y la hora.


#### R.N.08 CONTROL DE LOS ESTADOS DE LAS RESERVAS

Como administrador del sistema  
quiero que las reservas confirmadas comiencen en estado «Pendiente» y que únicamente puedan pasar a «Recogida» o «Cancelada», sin permitir otros estados ni cambios posteriores desde estos dos estados finales,  
para mantener un seguimiento coherente de las reservas.

-> **Pruebas de aceptación**

- Comprobar que una reserva comienza como «Pendiente» y puede pasar a «Recogida» o «Cancelada» cuando se cumplen las condiciones correspondientes.
- Verificar que se rechazan estados no permitidos y cambios desde los estados finales «Recogida» y «Cancelada».


#### R.N.09 CONTROL DE CANCELACIONES

Como cliente  
quiero poder cancelar únicamente mis reservas pendientes antes del inicio de la primera franja de recogida y que la cancelación devuelva las unidades disponibles una sola vez y de forma conjunta con el cambio de estado,  
para anular una reserva dentro del plazo permitido y permitir que otros clientes reserven esos packs.

-> **Pruebas de aceptación**

- Comprobar que el titular puede cancelar su reserva pendiente antes del plazo, cambiando el estado y devolviendo las unidades conjuntamente y una sola vez.
- Verificar que se rechaza la cancelación de una reserva ajena, recogida o fuera de plazo.


#### R.N.10 CONSERVACIÓN DEL PRECIO DE LAS RESERVAS

Como cliente  
quiero que cada línea conserve el precio reducido aplicado al confirmar la reserva, aunque posteriormente cambie el precio de la oferta, y que el total se calcule sumando la cantidad por el precio unitario de cada línea,  
para pagar el importe acordado al realizar la reserva.

-> **Pruebas de aceptación**

- Comprobar que una reserva de 2 unidades a 4 € conserva su total de 8 € aunque el precio de la oferta cambie después.
- Verificar que el total de una reserva con varias líneas es la suma de sus cantidades multiplicadas por los precios unitarios guardados.


#### R.N.11 CONTROL DEL REGISTRO DE RECOGIDAS

Como empleado del establecimiento  
quiero que solo el personal de mi establecimiento pueda marcar sus reservas pendientes como recogidas, una vez confirmadas la entrega de los productos y el cobro del importe,  
para mantener un registro fiable de las entregas realizadas.

-> **Pruebas de aceptación**

- Comprobar que un empleado del establecimiento puede marcar una reserva pendiente como recogida tras confirmar la entrega y el cobro.
- Verificar que se rechaza el registro si el usuario no es empleado de ese establecimiento, la reserva no está pendiente o falta confirmar la entrega o el cobro.


#### R.N.12 VALIDACIÓN DE RESEÑAS

Como administrador del sistema  
quiero que solo el cliente titular de una reserva recogida pueda publicar una única reseña sobre ella y que su puntuación sea un número entero entre 1 y 5,  
para que las valoraciones correspondan a compras realizadas y utilicen una escala común.

-> **Pruebas de aceptación**

- Comprobar que el titular de una reserva recogida y sin reseña puede publicar una puntuación entera entre 1 y 5.
- Verificar que se rechazan reseñas duplicadas, sobre reservas ajenas o no recogidas, o con puntuaciones no válidas.


### 4.2. Mapa de historias de usuario (opcional)

<img width="626" height="445" alt="MAPAHISTORIAUSUARIO" src="https://github.com/user-attachments/assets/2dfaedbc-d8c5-4b52-9709-3ce8fbe96aed" />


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

<img width="1062" height="1142" alt="IISSI1_diagramaUML drawio" src="https://github.com/user-attachments/assets/87364370-4e5a-45b1-a707-0746f8f6ed40" />


### 5.2. Escenarios de prueba

<img width="1062" height="1372" alt="escenariosPrueba drawio" src="https://github.com/user-attachments/assets/e40ebe71-b702-47e7-9887-b1cab2d1dc60" />


## 6. Matrices de trazabilidad

### 6.1. Matriz de trazabilidad de clases

| Requisito | Administrador | Empleado | Cliente | Usuario | Establecimiento | Pack | Reserva | Línea de Reserva | Reseña |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| RI-01 | ✓ | ✓ | ✓ | ✓ | | | | | |
| RI-02 | ✓ | | | | ✓ | | | | |
| RI-03 | | ✓ | | ✓ | ✓ | | | | |
| RI-04 | | ✓ | | | ✓ | ✓ | | | |
| RI-05 | | ✓ | ✓ | | ✓ | ✓ | ✓ | ✓ | |
| RI-06 | | | ✓ | | ✓ | | ✓ | | ✓ |
| RN-01 | ✓ | ✓ | ✓ | ✓ | | | | | |
| RN-02 | | | | | | ✓ | | | |
| RN-03 | | ✓ | | | | ✓ | | | |
| RN-04 | | | | | | ✓ | | | |
| RN-05 | | | ✓ | | ✓ | ✓ | ✓ | ✓ | |
| RN-06 | | | ✓ | | | ✓ | ✓ | ✓ | |
| RN-07 | | | ✓ | | | ✓ | ✓ | ✓ | |
| RN-08 | | ✓ | | | | | ✓ | | |
| RN-09 | | | ✓ | | | ✓ | ✓ | ✓ | |
| RN-10 | | | ✓ | | | ✓ | ✓ | ✓ | |
| RN-11 | | ✓ | | | ✓ | | ✓ | | |
| RN-12 | | | ✓ | | | | ✓ | | ✓ |

### 6.2. Matriz de trazabilidad de asociaciones

| Requisito | Empleado–Establecimiento | Establecimiento–Pack | Cliente–Reserva | Reserva–Línea de Reserva | Línea de Reserva–Pack | Reserva–Reseña |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| RI-01 | | | | | | |
| RI-02 | | | | | | |
| RI-03 | ✓ | | | | | |
| RI-04 | | ✓ | | | | |
| RI-05 | | ✓ | ✓ | ✓ | ✓ | |
| RI-06 | | | | | | ✓ |
| RN-01 | | | | | | |
| RN-02 | | ✓ | | | | |
| RN-03 | | ✓ | | | | |
| RN-04 | | ✓ | | | | |
| RN-05 | | ✓ | | ✓ | ✓ | |
| RN-06 | | | ✓ | ✓ | ✓ | |
| RN-07 | | ✓ | ✓ | ✓ | ✓ | |
| RN-08 | | | | ✓ | | |
| RN-09 | | | ✓ | ✓ | | |
| RN-10 | | | | ✓ | ✓ | |
| RN-11 | ✓ | | | ✓ | | |
| RN-12 | | | ✓ | | | ✓ |

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


