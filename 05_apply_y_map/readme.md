# Práctica: Transformación de Datos con `apply` y `map`

## Objetivo
El objetivo de esta práctica es familiarizarse con los métodos `apply` y `map` para transformar datos en un conjunto de datos. Utilizaremos un conjunto de datos ficticio sobre ventas de productos para ilustrar estos conceptos.

## Conjunto de Datos
Supongamos que tenemos un DataFrame llamado `ventas_df` con las siguientes columnas:

- `producto`: Nombre del producto vendido.
- `cantidad`: Cantidad de unidades vendidas.
- `precio_unitario`: Precio unitario del producto.

## Tareas a Realizar

### 1. Calcular el Total de Ventas por Producto
Usaremos el método `apply` para calcular el total de ventas (cantidad * precio unitario) para cada producto. Crearemos una nueva columna llamada `total_ventas`.

```python
ventas_df['total_ventas'] = ventas_df.apply(lambda row: row['cantidad'] * row['precio_unitario'], axis=1)
```

### 2. Aplicar Descuento a los Precios
Supongamos que queremos aplicar un descuento del 10% a todos los precios unitarios. Usaremos el método `map` para actualizar los valores de la columna `precio_unitario`.

```python
ventas_df['precio_unitario'] = ventas_df['precio_unitario'].map(lambda precio: precio * 0.9)
```

### 3. Calcular el Precio Promedio por Producto
Utilizaremos el método `apply` para calcular el precio promedio por producto. Crearemos una nueva columna llamada `precio_promedio`.

```python
precio_promedio_por_producto = ventas_df.groupby('producto')['precio_unitario'].mean()
ventas_df['precio_promedio'] = ventas_df['producto'].map(precio_promedio_por_producto)
```

## Más información sobre la data
Puedes encontrar más información sobre los datos dando click [aqui](https://www.kaggle.com/datasets/aungpyaeap/supermarket-sales)