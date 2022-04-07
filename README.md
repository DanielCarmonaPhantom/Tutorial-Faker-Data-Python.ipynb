{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "name": "Tutorial Fake Data Python.ipynb",
      "provenance": [],
      "collapsed_sections": [],
      "toc_visible": true,
      "authorship_tag": "ABX9TyNlVjInsVAWeksHe+GnJ/KQ",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/DanielCarmonaPhantom/Tutorial-Faker-Data-Python.ipynb/blob/main/Tutorial_Fake_Data_Python.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "# Tutorial Faker Data Python"
      ],
      "metadata": {
        "id": "OnsjR4Q0hHbL"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "Tutorial para aprender a crear data fake para proyectos:\n",
        "Puedes acceder a la [documentación](https://faker.readthedocs.io/en/master/)\n",
        "\n",
        "Para que puedo utilizar Faker:\n",
        "* Crear datos para CSV\n",
        "* DataFrames\n",
        "* Insertar datos a una base de datos"
      ],
      "metadata": {
        "id": "7bN9s1VJhMQV"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "Contenido:\n",
        "\n",
        "1. Introducción "
      ],
      "metadata": {
        "id": "IkHh3_rPh2Ms"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "## 1. Introducción"
      ],
      "metadata": {
        "id": "0eQxjb0BiBj8"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "###Quick start\n"
      ],
      "metadata": {
        "id": "Llkf2gTwliu5"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "Para poder utilizar la librería, procederemos a instalarla en nuestro entorno local. Utilizaremos el instalador de paquetes de `pip` o si es el caso `pip3`"
      ],
      "metadata": {
        "id": "phgzwgGEiHv4"
      }
    },
    {
      "cell_type": "code",
      "execution_count": 1,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "ZeEPZ9gvf5Zb",
        "outputId": "f02ae8be-fb09-46e9-8b53-692f9657e85f"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Collecting Faker\n",
            "  Downloading Faker-13.3.4-py3-none-any.whl (1.5 MB)\n",
            "\u001b[K     |████████████████████████████████| 1.5 MB 4.1 MB/s \n",
            "\u001b[?25hRequirement already satisfied: python-dateutil>=2.4 in /usr/local/lib/python3.7/dist-packages (from Faker) (2.8.2)\n",
            "Requirement already satisfied: typing-extensions>=3.10.0.2 in /usr/local/lib/python3.7/dist-packages (from Faker) (3.10.0.2)\n",
            "Requirement already satisfied: six>=1.5 in /usr/local/lib/python3.7/dist-packages (from python-dateutil>=2.4->Faker) (1.15.0)\n",
            "Installing collected packages: Faker\n",
            "Successfully installed Faker-13.3.4\n"
          ]
        }
      ],
      "source": [
        "pip install Faker"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "Una vez instalado debemos importarlo y crear una instancia."
      ],
      "metadata": {
        "id": "6cT_o76SlIXf"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "from faker import Faker\n",
        "fake = Faker()"
      ],
      "metadata": {
        "id": "nxb9m6cxiYBd"
      },
      "execution_count": 2,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "Para poder usarlo, llamaremos el método de los datos que deseas generar aleatoriamente."
      ],
      "metadata": {
        "id": "WPcM9w85kk2v"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "print(fake.name())"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "f3ilfEwykjMA",
        "outputId": "2711da2a-452a-4e91-9d73-68a8800041f2"
      },
      "execution_count": 3,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Deborah Jacobs\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "### Datos regionales"
      ],
      "metadata": {
        "id": "955hOyS_ocl2"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "Tambien podemos cambiar la locación regional cambiando los provedores para obtener datos regionales. En la [página de provedores](https://faker.readthedocs.io/en/stable/providers.html) puedes encontrar más información al respecto.\n",
        "\n",
        "No solo puedes cambiar la locación regional si no tambien los elementos a generar.\n",
        "\n",
        "Para generar datos de una localización es en español, podemos pasar como argumento `es_ES` al momento de instanciar para obtener datos regionales en español. Si te interesa alguna otra región, puedes encontrarla en [Localized Providers](https://faker.readthedocs.io/en/stable/locales.html).\n",
        "\n",
        "Al final contamos con una sección para visualizar los metodos especiales generados para el idioma en español."
      ],
      "metadata": {
        "id": "V44DV7_smEvw"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "fake = Faker('es_ES')"
      ],
      "metadata": {
        "id": "svl-9gAjldA6"
      },
      "execution_count": 6,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "print(fake.name())"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "4gxh7uNJlrtf",
        "outputId": "e35b3497-c4d1-4ce9-90de-52c1f467510b"
      },
      "execution_count": 7,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Florentina Pérez Pozuelo\n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "Datos de la región de México"
      ],
      "metadata": {
        "id": "xdS9JXKznoJk"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "fake = Faker('es_MX')"
      ],
      "metadata": {
        "id": "HT59VQg4nQQX"
      },
      "execution_count": 11,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "print(fake.address())"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "BUMksJLenkKF",
        "outputId": "ca269b52-2e57-4af3-91e6-2b45fe26c270"
      },
      "execution_count": 12,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Continuación Campeche 914 077\n",
            "Vieja Alemania, GRO 03389-4294\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        ""
      ],
      "metadata": {
        "id": "jcWTz3KNoB3x"
      },
      "execution_count": null,
      "outputs": []
    }
  ]
}
