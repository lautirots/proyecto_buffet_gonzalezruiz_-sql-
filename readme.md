CREACION BASE DE APP PARA GESTION GASTRONOMICA (BUFFET)


Problema:
Nuestro equipo de desarrollo está trabajando en un sistema de gestión de comercios gastronomicos, y nos enfrentamos a la necesidad de diseñar una base de datos eficiente que pueda manejar todas las operaciones relacionadas con la gestion de negocios gastronomicos, asi minimizar perdidas de dinero y mercaderia.


Descripción del Problema:
Gestión de Clientes y Empleados: Necesitamos una base de datos que nos permita registrar la información de los clientes que realizan pedidos, así como de los empleados involucrados en el proceso de preparacion de los diferentes platos, tanto los cocineros y encargados de atención al cliente. De esta manera poder definir un menu estable, segun la necesidad de nuestros clientes.

Gestión de Categoria de Platos: Es importante poder clasificar los platos según su tipo, distinguiendo entre celiaco, hipertenso, diabetico, vegetariano, etc. Esto nos ayudará a adaptar nuestros servicios según las necesidades del cliente.

Gestión de Pedidos: es importante saber el numero exacto de pedidos por dia, para asi poder hacer los pedidos de mercaderia, con mas exactitud y sin desperdicios.


Objetivo:


Nuestro objetivo es conocer nuestros comensales, para asi definir un menu  "semi-fijo", El cual nos va a dar la base de nuestras compras de mercaderia, con el afan de obtener la menor cantidad de desperdicio de almientos posibles.


Descripción de la Base de Datos - Buffet
Esta base de datos está diseñada para gestionar un negocio gastronomico, así como la información relacionada con clientes, Empleados, Platos y Pedidos. A continuación se detallan los elementos principales de la base de datos:

Tablas:

CLIENTE:  Almacena información sobre los clientes que realizan pedidos.


Atributos:

IDCLIENTE,
NOMBRE, 
TELEFONO,
EMAIL.

EMPLEADO: Contiene información sobre los empleados involucrados en el proceso de preparacion de alimentos y atencion al publico.


Atributos:

EmpleadoID ,
Nombre ,
Apellido ,
Cargo ,
FechaContratacion ,
 Salario 

PLATOS:  Define diferentes tipos de platos para clasificarlos según su categoria o precio específico.


Atributos:


 PlatoID 
Nombre 
 Precio 
 CategoriaID

CATEGORIAS:   Categorías a las que pertenecen los platos (por ejemplo, celiacos, vegetarianos, diabeticos).


Atributos:


CategoriaID ,
Nombre


PEDIDOS:     Información sobre los pedidos realizados por los clientes.


Atributos: 


   PedidoID ,
   ClienteID ,
   EmpleadoID ,
   FechaPedido ,
   Total

DETALLES_PEDIDOS:  Detalles de cada plato en un pedido específico.


Atributos:


 DetalleID ,
 PedidoID ,
 PlatoID ,
 Cantidad ,
 PrecioUnitario


Esta base de datos permite gestionar eficientemente el proceso de gestion gastronomica, desde la información de los clientes y empleados hasta los tipos de platos y sus precios. Algunos aspectos que aborda incluyen:

Registro de clientes y empleados involucrados en el proceso de gestion gastronomica.
Clasificación de platos según su tipo.
Registro detallado de los pedidos realizados, incluyendo la fecha, cliente, plato, empleado y categoria.
En resumen, esta base de datos proporciona una estructura para organizar y gestionar eficientemente las operaciones deun buffet, lo que contribuye a mejorar el servicio ofrecido a los clientes. 



Der simplificado

```
+------------------+       +-----------------------+       +------------------+
|      CLIENTE     |       |       PEDIDO          |       |   DETALLE_PEDIDO |
+------------------+       +-----------------------+       +------------------+
| idCliente (PK)   |<>-----| idPedido (PK)         |-------| idDetalle (PK)   |
| nombre           | 1 a * | fecha                 | 1 a * | idPedido (fk)    |
| telefono         |       | id_cliente (fk)       |       | idPlato (fk)     | 
| email            |       | id_empleado (fk)      |       | cantidad         |
+------------------+       +-----------------------+       +------------------+
                                                                    
+------------------+       +------------------+       +-------------------+
|     EMPLEADO     |       |    CATEGORIAS    |       |     PLATOS        |
+------------------+       +------------------+       +-------------------+
| idEmpleado (PK)  |       | idCategoria (PK) |-------| idPlato (PK)      |
| nombre           | 1 a * | nombre           | 1 a * | nombre            |
| telefono         |<>-----|                  |       | descripcion       |
| posicion         |       |                  |       | precio            |
| salario          |       +------------------+       | idCategoria (fk)  |
+------------------+                                 +-------------------+
```





