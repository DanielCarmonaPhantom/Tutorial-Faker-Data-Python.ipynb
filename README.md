# Tutorial Faker Data Python

Tutorial para aprender a crear data fake para proyectos:
Puedes acceder a la [documentación](https://faker.readthedocs.io/en/master/)

Para que puedo utilizar Faker:
* Crear datos para CSV
* DataFrames
* Insertar datos a una base de datos

Contenido:

1. Introducción 


## 1. Introducción

<h3>Quick start</h3>

Para poder utilizar la librería, procederemos a instalarla en nuestro entorno local. Utilizaremos el instalador de paquetes de `pip` o si es el caso `pip3`

````
pip install Faker
````

Una vez instalado debemos importarlo y crear una instancia.
```python
from faker import Faker
fake = Faker()
```

Para poder usarlo, llamaremos el método de los datos que deseas generar aleatoriamente.

````python
print(fake.name())
````
