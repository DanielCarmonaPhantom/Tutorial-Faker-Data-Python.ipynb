

::: {.cell .markdown id="OnsjR4Q0hHbL"}
# Tutorial Faker Data Python
:::

::: {.cell .markdown id="7bN9s1VJhMQV"}
Tutorial para aprender a crear data fake para proyectos: Puedes acceder
a la [documentación](https://faker.readthedocs.io/en/master/)

Para que puedo utilizar Faker:

-   Crear datos para CSV
-   DataFrames
-   Insertar datos a una base de datos
:::

::: {.cell .markdown id="IkHh3_rPh2Ms"}
Contenido:

1.  Introducción
:::

::: {.cell .markdown id="0eQxjb0BiBj8"}
## 1. Introducción {#1-introducción}
:::

::: {.cell .markdown id="Llkf2gTwliu5"}
\#\#\#Quick start
:::

::: {.cell .markdown id="phgzwgGEiHv4"}
Para poder utilizar la librería, procederemos a instalarla en nuestro
entorno local. Utilizaremos el instalador de paquetes de `pip` o si es
el caso `pip3`
:::

::: {.cell .code execution_count="1" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="ZeEPZ9gvf5Zb" outputId="f02ae8be-fb09-46e9-8b53-692f9657e85f"}
``` {.python}
pip install Faker
```

::: {.output .stream .stdout}
    Collecting Faker
      Downloading Faker-13.3.4-py3-none-any.whl (1.5 MB)
    ent already satisfied: python-dateutil>=2.4 in /usr/local/lib/python3.7/dist-packages (from Faker) (2.8.2)
    Requirement already satisfied: typing-extensions>=3.10.0.2 in /usr/local/lib/python3.7/dist-packages (from Faker) (3.10.0.2)
    Requirement already satisfied: six>=1.5 in /usr/local/lib/python3.7/dist-packages (from python-dateutil>=2.4->Faker) (1.15.0)
    Installing collected packages: Faker
    Successfully installed Faker-13.3.4
:::
:::

::: {.cell .markdown id="6cT_o76SlIXf"}
Una vez instalado debemos importarlo y crear una instancia.
:::

::: {.cell .code execution_count="2" id="nxb9m6cxiYBd"}
``` {.python}
from faker import Faker
fake = Faker()
```
:::

::: {.cell .markdown id="WPcM9w85kk2v"}
Para poder usarlo, llamaremos el método de los datos que deseas generar
aleatoriamente.
:::

::: {.cell .code execution_count="3" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="f3ilfEwykjMA" outputId="2711da2a-452a-4e91-9d73-68a8800041f2"}
``` {.python}
print(fake.name())
```

::: {.output .stream .stdout}
    Deborah Jacobs
:::
:::

::: {.cell .markdown id="955hOyS_ocl2"}
### Datos regionales
:::

::: {.cell .markdown id="V44DV7_smEvw"}
Tambien podemos cambiar la locación regional cambiando los provedores
para obtener datos regionales. En la [página de
provedores](https://faker.readthedocs.io/en/stable/providers.html)
puedes encontrar más información al respecto.

No solo puedes cambiar la locación regional si no tambien los elementos
a generar.

Para generar datos de una localización es en español, podemos pasar como
argumento `es_ES` al momento de instanciar para obtener datos regionales
en español. Si te interesa alguna otra región, puedes encontrarla en
[Localized
Providers](https://faker.readthedocs.io/en/stable/locales.html).

Al final contamos con una sección para visualizar los metodos especiales
generados para el idioma en español.
:::

::: {.cell .code execution_count="6" id="svl-9gAjldA6"}
``` {.python}
fake = Faker('es_ES')
```
:::

::: {.cell .code execution_count="7" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="4gxh7uNJlrtf" outputId="e35b3497-c4d1-4ce9-90de-52c1f467510b"}
``` {.python}
print(fake.name())
```

::: {.output .stream .stdout}
    Florentina Pérez Pozuelo
:::
:::

::: {.cell .markdown id="xdS9JXKznoJk"}
Datos de la región de México
:::

::: {.cell .code execution_count="11" id="HT59VQg4nQQX"}
``` {.python}
fake = Faker('es_MX')
```
:::

::: {.cell .code execution_count="12" colab="{\"base_uri\":\"https://localhost:8080/\"}" id="BUMksJLenkKF" outputId="ca269b52-2e57-4af3-91e6-2b45fe26c270"}
``` {.python}
print(fake.address())
```

::: {.output .stream .stdout}
    Continuación Campeche 914 077
    Vieja Alemania, GRO 03389-4294
:::
:::

::: {.cell .code id="jcWTz3KNoB3x"}
``` {.python}
```
:::
