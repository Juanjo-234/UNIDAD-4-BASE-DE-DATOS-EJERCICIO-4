# UNIDAD-4-BASE-DE-DATOS-EJERCICIO-4
Tablas Principales y Atributos

categoria: Administra las categorías de los productos. Contiene los campos id_categoria (PK), nombre y id_categoria_padre (clave foránea autorreferencial para manejar jerarquías o subcategorías).

cliente: Almacena la información de los usuarios registrados. Incluye id_cliente (PK), correo, nombre, apellido, contrasenia y direccion_envio (FK hacia la tabla de direcciones).

direccion: Contiene la ubicación física detallada con los campos id_direccion (PK), calle, numero_calle, ciudad y codigo_postal.

transportista: Registra los datos de las empresas de logística o envío mediante cuit (PK), razon_social y telefono.

producto: Catálogo de artículos con sku (PK), nombre, descripcion, precio, stock y id_categoria (FK).

pedido: Cabecera de las órdenes de compra. Posee numero_orden (PK), fecha, hora, estado, monto_total, además de las claves foráneas id_cliente y cuit_transportista.

detalles_envio: Tabla intermedia que resuelve la relación de muchos a muchos entre pedidos y productos. Utiliza una clave primaria compuesta por sku y numero_orden, acompañada del campo numérico cantidad.

Restricciones y Claves Foráneas (Foreign Keys)

fk_categoria_padre: Relaciona categoria(id_categoria_padre) con categoria(id_categoria).

fk_cliente_direccion: Relaciona cliente(direccion_envio) con direccion(id_direccion).

fk_pedido_cliente: Relaciona pedido(id_cliente) con cliente(id_cliente).

fk_pedido_transportista: Relaciona pedido(cuit_transportista) con transportista(cuit).

fk_producto_categoria: Relaciona producto(id_categoria) con categoria(id_categoria).

fk_detalle_pedido: Relaciona detalles_envio(numero_orden) con pedido(numero_orden).

fk_detalle_producto: Relaciona detalles_envio(sku) con producto(sku).

IMAGEN DE EJEMPLO DE CONSULTA:
<img width="952" height="362" alt="image" src="https://github.com/user-attachments/assets/e650be34-0bb4-4a43-942d-d188dd3c216c" />
