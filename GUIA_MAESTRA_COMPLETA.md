# 📚 GUÍA MAESTRA DE ESTUDIO — EXAMEN ANUAL
## Módulos 2 al 7 | Full Stack Python Django

---

# MÓDULO 2: Fundamentos de Desarrollo Front-End

## 🌐 Arquitectura Web
- **Internet**: red global de computadoras interconectadas
- **Sitio estático**: contenido fijo, mismo para todos los usuarios
- **Sitio dinámico**: contenido cambia según usuario/interacción (requiere backend)
- **Frontend**: lo que ve el usuario (HTML, CSS, JS)
- **Backend**: lógica del servidor (Python, Django, bases de datos)
- **Full Stack**: dominio de ambos

---

## 📄 HTML5

### Estructura básica obligatoria:
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mi Página</title>
</head>
<body>
  <h1>Título principal</h1>
  <p>Párrafo de contenido.</p>
</body>
</html>
```

### Etiquetas semánticas:
| Etiqueta | Uso |
|----------|-----|
| `<header>` | Cabecera de la página/sección |
| `<nav>` | Menú de navegación |
| `<section>` | Agrupación temática de contenido |
| `<aside>` | Contenido lateral/relacionado |
| `<footer>` | Pie de página |
| `<main>` | Contenido principal |

### Encabezados (jerarquía):
- `<h1>` — Solo **uno por página** (tema principal / SEO)
- `<h2>` a `<h6>` — Subsecciones, orden jerárquico

### Etiquetas comunes:
```html
<!-- Párrafo -->
<p>Texto aquí</p>

<!-- Imagen -->
<img src="foto.jpg" alt="Descripción">

<!-- Enlace -->
<a href="https://ejemplo.com">Visitar</a>

<!-- Enlace de correo -->
<a href="mailto:correo@ejemplo.com">Contáctame</a>

<!-- Lista ordenada -->
<ol>
  <li>Primer elemento</li>
  <li>Segundo elemento</li>
</ol>

<!-- Lista desordenada -->
<ul>
  <li>Elemento</li>
</ul>

<!-- Tabla -->
<table>
  <tr><th>Nombre</th><th>Edad</th></tr>
  <tr><td>Alice</td><td>30</td></tr>
</table>

<!-- Contenedor genérico -->
<div class="mi-seccion">
  <p>Contenido agrupado</p>
</div>
```

### Formularios:
```html
<form action="/enviar" method="POST">
  <input type="text" name="nombre" placeholder="Tu nombre">
  <input type="email" name="correo" placeholder="correo@ejemplo.com">
  <input type="password" name="clave">
  <input type="checkbox" name="acepto"> Acepto términos
  <input type="radio" name="genero" value="m"> Masculino
  <input type="radio" name="genero" value="f"> Femenino

  <select name="color">
    <option value="rojo">Rojo</option>
    <option value="azul">Azul</option>
  </select>

  <button type="submit">Enviar</button>
</form>
```

**Atributos clave de `<form>`:**
- `action` — URL a donde se envían los datos
- `method` — `GET` (visible en URL) o `POST` (oculto, para datos sensibles)

---

## 🎨 CSS

### 3 formas de aplicar CSS:
```html
<!-- 1. En línea (NO recomendado para proyectos grandes) -->
<p style="color: red;">Texto rojo</p>

<!-- 2. Embebido (en el <head>) -->
<style>
  p { color: blue; }
</style>

<!-- 3. Externo (RECOMENDADO) -->
<link rel="stylesheet" href="styles.css">
```

### Selectores CSS:
```css
/* Por etiqueta */
p { color: black; }

/* Por clase (prefijo .) */
.destacado { font-weight: bold; }

/* Por ID (prefijo #, único por página) */
#titulo-principal { font-size: 2em; }
```

### Prioridad (especificidad):
1. **Estilos en línea** (mayor prioridad)
2. **ID** `#id`
3. **Clase** `.clase`
4. **Etiqueta** `p, h1`
5. `!important` — anula TODO (usar con cuidado)

### Modelo de Cajas (Box Model):
```css
div {
  width: 300px;        /* ancho del contenido */
  padding: 20px;       /* espacio interno */
  border: 5px solid black; /* borde */
  margin: 10px;        /* espacio externo */
  box-sizing: border-box; /* padding/border incluidos en width */
}
```
> **Capa a capa**: contenido → padding → border → margin

### Block vs Inline:
| Tipo | Comportamiento | Ejemplos |
|------|---------------|---------|
| **Block** | Ocupa todo el ancho, nueva línea | `<div>`, `<p>`, `<h1>` |
| **Inline** | Solo ocupa su contenido, misma línea | `<span>`, `<a>`, `<img>` |

### Propiedades CSS más usadas:
```css
/* Colores */
color: navy;
background-color: lightgray;

/* Fuentes */
font-family: Arial, sans-serif;
font-size: 16px;
font-weight: bold;

/* Bordes y espaciado */
border: 2px solid blue;
margin: 10px;
padding: 15px;

/* Imágenes de fondo */
background-image: url('imagen.jpg');
background-size: cover;     /* cubre todo el contenedor */
background-repeat: no-repeat;
background-position: center center;

/* Imágenes en contenido */
img { width: 100%; height: auto; }
```

### Herencia en CSS:
- Propiedades como `color` y `font-size` se **heredan** del elemento padre
- Si un `<body>` tiene `color: blue`, los `<p>` también serán azules (si no se sobreescriben)

---

## 📱 Diseño Responsivo y Mobile First

- **Responsivo**: el sitio se adapta al tamaño de la pantalla
- **Mobile First**: diseñar primero para móviles, luego escalar
- **Viewport meta tag** (obligatorio):
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
- Google prioriza sitios responsivos (Mobilegeddon 2015)
- Una sola base de código para todos los dispositivos

---

# MÓDULO 3: Fundamentos de Python

##  Python — Conceptos Clave
- Creado por **Guido van Rossum** (1991)
- **Multiparadigma**: soporta POO, programación funcional, imperativa
- **Tipado dinámico**: no declaras el tipo, Python lo infiere
- **Interpretado**: el intérprete lee y ejecuta línea a línea (no se compila a binario)
- **Indentación obligatoria**: los bloques se definen con espacios (4 espacios = estándar)

##  Instalación y Ejecución
```bash
# Verificar instalación (Linux/Mac)
python3

# Ejecutar script
python nombre_archivo.py

# Modo interactivo (REPL)
python
```

- **.py** — script estándar (muestra consola)
- **.pyw** — aplicación gráfica Windows (sin consola)
- **IDLE** — IDE básico incluido con Python
- **VS Code** — editor recomendado

## 📦 PIP — Gestor de Paquetes
```bash
pip install nombre_paquete      # instalar
pip install --upgrade paquete   # actualizar
pip uninstall paquete           # desinstalar
pip list                        # listar instalados
```
> PIP = "Pip Installs Packages" — accede a PyPI (Python Package Index)

##  Función print()
```python
print("Hola mundo")
print("Nombre:", nombre)
print("A", "B", "C", sep="-")   # A-B-C
print("Sin salto", end="")
```

##   Tipos de Datos
```python
# Entero (int)
edad = 25

# Decimal (float)
precio = 19.99

# Cadena (str)
nombre = "Ana"

# Booleano (bool)
activo = True
inactivo = False

# Lista — ordenada, mutable
frutas = ["manzana", "pera", "uva"]

# Tupla — ordenada, INMUTABLE
coordenadas = (10, 20)

# Diccionario — clave:valor
persona = {"nombre": "Luis", "edad": 30}

# Conjunto (set) — sin duplicados, no ordenado
numeros = {1, 2, 3, 4}
```

##  Operadores
```python
# Aritméticos
+   # suma
-   # resta
*   # multiplicación
/   # división (float)
//  # división entera
%   # módulo (resto)
**  # exponenciación: 2**3 = 8

# Comparación (devuelven True/False)
==  !=  >  <  >=  <=

# Lógicos
and   # ambas verdaderas
or    # al menos una verdadera
not   # invierte

# Ejemplo:
x = 5
print(x > 3 and x < 10)  # True
```

##  Conversiones de Tipo
```python
int("42")       # str → int
float("3.14")   # str → float
str(100)        # int → str
bool(0)         # 0 → False, cualquier otro → True
```

##  Variables — Reglas de Nombres
```python
# Correcto
mi_variable = 10
_privado = 5
contador1 = 0

# Incorrecto (errores comunes)
# 1variable = 10   → no puede empezar con número
# class = "Python" → no puede ser palabra reservada

# Convenciones:
mi_variable = 1      # snake_case para variables/funciones
MI_CONSTANTE = 3.14  # MAYÃÅ¡SCULAS para constantes
MiClase = None       # CamelCase para clases
```

##  Scope (Alcance de Variables)
```python
x = 10  # global — accesible desde cualquier lugar

def mi_funcion():
    y = 5  # local — solo existe dentro de la función
    print(x)  # puede acceder a global
    print(y)  # accede a local

mi_funcion()
# print(y)  # ERROR: y no existe fuera
```

##  Sentencias Condicionales
```python
edad = 18

if edad >= 18:
    print("Mayor de edad")
elif edad >= 12:
    print("Adolescente")
else:
    print("Niño")
```

##  Bucles
```python
# FOR — itera sobre secuencia
for i in range(5):     # 0, 1, 2, 3, 4
    print(i)

for fruta in ["manzana", "pera"]:
    print(fruta)

# WHILE — repite mientras condición sea True
contador = 0
while contador < 5:
    print(contador)
    contador += 1  # ¡importante actualizar o bucle infinito!

# BREAK — sale del bucle
for i in range(10):
    if i == 5:
        break      # para en 5

# CONTINUE — salta iteración actual
for i in range(10):
    if i == 5:
        continue   # omite el 5, continúa
    print(i)
```

##  Métodos Más Comunes
```python
# Cadenas (str)
"hola".upper()           # → "HOLA"
"HOLA".lower()           # → "hola"
"Python".replace("P","J") # → "Jython"
"a,b,c".split(",")       # → ["a","b","c"]

# Listas
lista = [1, 2, 3]
lista.append(4)          # agrega al final
lista.remove(2)          # elimina primera ocurrencia
lista.sort()             # ordena

# Diccionarios
d = {"a": 1, "b": 2}
d.keys()                 # claves: dict_keys(['a','b'])
d.values()               # valores: dict_values([1,2])
```

##  Módulos y Paquetes
```python
import math
print(math.pi)           # 3.14159...
print(math.sqrt(16))     # 4.0

from math import sqrt
print(sqrt(16))          # 4.0

# Módulo propio (archivo.py)
# Si se ejecuta directamente:
if __name__ == "__main__":
    print("Ejecutando directamente")
```

## — Ejecución Síncrona vs Asíncrona
- **Síncrona**: instrucciones una tras otra, bloqueante
- **Asíncrona**: múltiples tareas en paralelo, con `async`/`await`
```python
import asyncio

async def mi_tarea():
    await asyncio.sleep(1)
    print("Tarea lista")
```
# MÓDULO 4: Programación Orientada a Objetos (POO)

## Conceptos Fundamentales

### ¿Qué es una Clase?
Una **clase** es una plantilla/molde para crear objetos. Define atributos (datos) y métodos (comportamientos).

```python
class Auto:
    # Atributo de CLASE (compartido por todos)
    ruedas = 4

    # Constructor: se ejecuta al crear cada objeto
    def __init__(self, marca, modelo, color):
        # Atributos de INSTANCIA (únicos por objeto)
        self.marca = marca
        self.modelo = modelo
        self.color = color

    # Método
    def arrancar(self):
        print(f"El {self.marca} está arrancando...")

    def __str__(self):
        return f"{self.marca} {self.modelo} ({self.color})"

# Instanciar (crear objetos)
mi_auto = Auto("Toyota", "Corolla", "rojo")
tu_auto = Auto("Honda", "Civic", "azul")

# Usar métodos y atributos
mi_auto.arrancar()
print(mi_auto.marca)    # Toyota
print(Auto.ruedas)      # 4
print(mi_auto)          # Toyota Corolla (rojo)
```

---

## Encapsulamiento

Ocultar datos internos con atributos **privados** (`__`):

```python
class CuentaBancaria:
    def __init__(self, titular, saldo):
        self.titular = titular
        self.__saldo = saldo  # privado: doble guion bajo

    # GETTER — acceder al valor privado
    def get_saldo(self):
        return self.__saldo

    # SETTER — modificar con validación
    def set_saldo(self, nuevo_saldo):
        if nuevo_saldo >= 0:
            self.__saldo = nuevo_saldo
        else:
            print("Error: saldo no puede ser negativo")

cuenta = CuentaBancaria("Ana", 1000)
print(cuenta.get_saldo())    # 1000
cuenta.set_saldo(1500)
# cuenta.__saldo = -500      # ERROR — no accesible directamente
```

> **Getters** = accesadores (leer) | **Setters** = mutadores (escribir con validación)

---

## Herencia

Una clase **hija** hereda atributos y métodos de la clase **padre**:

```python
class Animal:
    def __init__(self, nombre):
        self.nombre = nombre

    def comer(self):
        print(f"{self.nombre} está comiendo")

class Perro(Animal):  # hereda de Animal
    def __init__(self, nombre, raza):
        super().__init__(nombre)  # llama al __init__ del padre
        self.raza = raza

    def ladrar(self):
        print("¡Guau guau!")

rex = Perro("Rex", "Labrador")
rex.comer()    # heredado de Animal
rex.ladrar()   # propio de Perro
```

---

## Polimorfismo

El mismo método se comporta diferente según el objeto:

```python
class Figura:
    def area(self):
        return 0

class Circulo(Figura):
    def __init__(self, radio):
        self.radio = radio
    def area(self):
        return 3.14 * self.radio ** 2

class Rectangulo(Figura):
    def __init__(self, base, altura):
        self.base = base
        self.altura = altura
    def area(self):
        return self.base * self.altura

figuras = [Circulo(5), Rectangulo(4, 6)]
for f in figuras:
    print(f.area())  # cada uno calcula su área diferente
```

---

## Sobrecarga de Métodos (simulada en Python)

Python NO tiene sobrecarga nativa, pero se simula con:

```python
# 1. Parámetros opcionales
def saludar(nombre, apellido=None):
    if apellido:
        print(f"Hola {nombre} {apellido}")
    else:
        print(f"Hola {nombre}")

# 2. *args y **kwargs
def sumar(*args):
    return sum(args)

print(sumar(1, 2))       # 3
print(sumar(1, 2, 3, 4)) # 10
```

---

## Colaboración vs Composición

| Aspecto | Colaboración | Composición |
|---------|-------------|-------------|
| Relación | Flexible, asociación | Contención ("tiene un") |
| Acoplamiento | Débil | Fuerte |
| Independencia | Clases existen solas | Parte depende del todo |
| Ejemplo | Jugador usa una Misión | Personaje tiene BarraSalud |

```python
# COLABORACIÃâN — clases independientes que cooperan
class Mision:
    def __init__(self, nombre):
        self.nombre = nombre

class Jugador:
    def aceptar_mision(self, mision):  # recibe objeto externo
        print(f"Acepté: {mision.nombre}")

# COMPOSICIÃâN — una clase contiene otra como parte esencial
class BarraSalud:
    def __init__(self, max_hp):
        self.hp = max_hp

class Personaje:
    def __init__(self, nombre):
        self.nombre = nombre
        self.salud = BarraSalud(100)  # creada DENTRO, parte esencial
```

---

## Diagramas de Clase UML

Representación visual de clases. Rectángulo con 3 secciones:
1. **Nombre** de la clase
2. **Atributos** con visibilidad
3. **Métodos** con parámetros y retorno

**Visibilidad:**
- `+` Público — accesible desde cualquier clase
- `-` Privado — solo accesible dentro de la clase
- `#` Protegido — accesible en clase y subclases

**Relaciones:**
- **Asociación** → línea simple (un cliente tiene pedidos)
- **Herencia** → flecha hueca (Perro hereda de Animal)
- **Composición** → rombo negro (parte esencial)
- **Agregación** → rombo blanco (relación débil)
- **Dependencia** → línea discontinua (uso temporal)

---

# MÓDULO 5: Bases de Datos Relacionales

## Conceptos Fundamentales

- **Base de datos**: colección organizada de datos
- **RDBMS**: Sistema Gestor de BD Relacionales (MySQL, PostgreSQL, SQLite)
- **Tabla**: conjunto de datos organizados en filas y columnas
- **Registro/Tupla**: una fila de la tabla
- **Campo/Atributo**: una columna
- **Clave primaria (PK)**: identifica únicamente cada registro (no null, único)
- **Clave foránea (FK)**: referencia a la PK de otra tabla

## Relaciones entre Tablas

| Tipo | Descripción | Ejemplo |
|------|------------|---------|
| **1:1** | Un registro se relaciona con uno | Persona — Pasaporte |
| **1:N** | Un registro con muchos | Cliente — Pedidos |
| **N:M** | Muchos con muchos (tabla intermedia) | Estudiante — Cursos |

## Normalización

Técnica para reducir redundancia y anomalías:

- **1FN**: valores atómicos, clave primaria única, sin grupos repetitivos
- **2FN**: cumple 1FN + sin dependencias parciales
- **3FN**: cumple 2FN + sin dependencias transitivas
- **Desnormalización**: agregar redundancia para mejorar rendimiento en consultas

## Diccionario de Datos

Documento que describe la estructura de cada campo:
- Nombre del campo, tipo, longitud, restricciones, descripción

---

## SQL — Lenguaje de Consulta Estructurado

### DDL (Data Definition Language) — Define estructura:

```sql
-- Crear base de datos
CREATE DATABASE mi_base;

-- Crear tabla
CREATE TABLE clientes (
  id      INT AUTO_INCREMENT PRIMARY KEY,
  nombre  VARCHAR(100) NOT NULL,
  correo  VARCHAR(100) UNIQUE NOT NULL,
  edad    INT CHECK (edad >= 18),
  estado  VARCHAR(10) DEFAULT 'activo'
);

-- Modificar tabla (agregar columna)
ALTER TABLE clientes ADD COLUMN telefono VARCHAR(15);

-- Eliminar tabla
DROP TABLE clientes;

-- Vaciar tabla (más rápido que DROP)
TRUNCATE TABLE clientes;
```

### DML (Data Manipulation Language) — Manipula datos:

```sql
-- INSERT — agregar registros
INSERT INTO clientes (nombre, correo, edad)
VALUES ('Ana García', 'ana@ejemplo.com', 25);

-- SELECT — consultar datos
SELECT * FROM clientes;
SELECT nombre, correo FROM clientes WHERE edad > 18;

-- UPDATE — modificar registros
UPDATE clientes
SET nombre = 'Ana López'
WHERE id = 1;
-- — ï¸ SIN WHERE actualiza TODOS los registros

-- DELETE — eliminar registros
DELETE FROM clientes WHERE id = 2;
-- — ï¸ SIN WHERE elimina TODOS los registros
```

### Restricciones (Constraints):

| Restricción | Descripción |
|------------|-------------|
| `PRIMARY KEY` | Identificador único, no null |
| `FOREIGN KEY` | Referencia a otra tabla |
| `NOT NULL` | Campo obligatorio |
| `UNIQUE` | Valores únicos |
| `CHECK` | Condición que debe cumplirse |
| `DEFAULT` | Valor por defecto |
| `AUTO_INCREMENT` | Número automático (MySQL) |

### Tipos de Datos MySQL:

```sql
-- Numéricos
INT, SMALLINT, BIGINT, FLOAT, DOUBLE, DECIMAL(8,2)

-- Texto
CHAR(n)       -- longitud fija
VARCHAR(n)    -- longitud variable (hasta n)
TEXT          -- texto largo

-- Fecha/Hora
DATE, DATETIME, TIMESTAMP, TIME, YEAR

-- Otros
BOOLEAN, ENUM('val1','val2')
```

### Integridad Referencial con FK:

```sql
CREATE TABLE pedidos (
  id         INT AUTO_INCREMENT PRIMARY KEY,
  cliente_id INT NOT NULL,
  fecha      DATE,
  FOREIGN KEY (cliente_id)
    REFERENCES clientes(id)
    ON DELETE CASCADE    -- si borra cliente, borra sus pedidos
    ON UPDATE CASCADE    -- si cambia id, actualiza pedidos
);
```

---

## Transacciones y ACID

Una **transacción** es un conjunto de operaciones tratadas como una unidad.

**Propiedades ACID:**
- **A**tomicidad: todo o nada
- **C**onsistencia: siempre en estado válido
- **I**solación: las transacciones no interfieren
- **D**urabilidad: los cambios confirmados son permanentes

```sql
-- Iniciar transacción
START TRANSACTION;

-- Operaciones
UPDATE cuentas SET saldo = saldo - 500 WHERE id = 1;
UPDATE cuentas SET saldo = saldo + 500 WHERE id = 2;

-- Confirmar (permanente)
COMMIT;

-- O revertir si hay error
ROLLBACK;

-- Modo autocommit (por defecto ON en MySQL)
SET autocommit = 0;  -- desactivar para control manual
```
# MÓDULO 6 y 7: Django Web Framework

## ¿Qué es Django?
Framework web Python de alto nivel. Filosofía **"batteries included"** (todo incluido).
Usado por: Instagram, Pinterest, Spotify, Mozilla.

---

## Patrón MTV (Model-Template-View)

Django usa **MTV**, equivalente al patrón MVC:

| Django (MTV) | MVC clásico | Rol |
|-------------|-------------|-----|
| **Model** | Model | Datos y lógica de base de datos |
| **Template** | View | Presentación HTML al usuario |
| **View** | Controller | Lógica de negocio, procesa request |

### Flujo de una petición:
```
Usuario → URL (urls.py) → View (views.py) → Model (models.py)
                                          — â
                              Template (.html) → Respuesta HTML
```

---

## Comandos Esenciales Django

```bash
# Crear entorno virtual (antes de todo)
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # Linux/Mac

# Instalar Django
pip install django

# Crear proyecto
django-admin startproject nombre_proyecto .

# Crear aplicación dentro del proyecto
python manage.py startapp nombre_app

# Ejecutar servidor de desarrollo
python manage.py runserver
# → Abrir: http://127.0.0.1:8000/

# Migraciones
python manage.py makemigrations   # detecta cambios en models.py → crea archivo
python manage.py migrate          # aplica migraciones → actualiza BD
python manage.py showmigrations   # ver estado de migraciones

# Retroceder migración
python manage.py migrate app_name 0007_nombre_anterior

# Crear superusuario (para panel admin)
python manage.py createsuperuser

# Shell interactivo (Python + Django)
python manage.py shell

# Ver todos los comandos
python manage.py help
```

---

## Estructura de un Proyecto Django

```
mi_proyecto/
—
— manage.py                  — Â punto de entrada de comandos
—
— mi_proyecto/               — Â configuración del proyecto
—   — settings.py            — Â configuración global
—   — urls.py                — Â rutas principales
—   — wsgi.py                — Â despliegue en producción
—   — asgi.py
—
— mi_app/                    — Â aplicación
    — models.py              — Â clases de datos (tablas BD)
    — views.py               — Â lógica de las páginas
    — urls.py                — Â rutas de la app (crear manual)
    — forms.py               — Â formularios (crear manual)
    — admin.py               — Â registro en panel admin
    — apps.py                — Â config de la app
    — migrations/            — Â archivos de migración
```

---

## settings.py — Configuración Clave

```python
# Agregar tu app aquí (OBLIGATORIO)
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'mi_app',                  # — Â agregar aquí
]

# Base de datos (por defecto SQLite)
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}

# Conectar con PostgreSQL
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'bd_django',
        'USER': 'django',
        'PASSWORD': '123456',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}

# Instalar conector PostgreSQL:
# pip install psycopg2-binary

# Archivos estáticos
STATIC_URL = '/static/'
STATICFILES_DIRS = [BASE_DIR / 'static']

# Redirecciones de autenticación
LOGIN_REDIRECT_URL = '/'
LOGOUT_REDIRECT_URL = '/login/'

# Templates
TEMPLATES = [{'DIRS': [BASE_DIR / 'templates'], ...}]
```

---

## Models (Modelos)

Cada clase modelo = una tabla en la base de datos.

```python
# models.py
from django.db import models

class Producto(models.Model):
    nombre      = models.CharField(max_length=100)
    descripcion = models.TextField(blank=True)
    precio      = models.DecimalField(max_digits=10, decimal_places=2)
    stock       = models.IntegerField(default=0)
    activo      = models.BooleanField(default=True)
    creado      = models.DateTimeField(auto_now_add=True)
    actualizado = models.DateTimeField(auto_now=True)

    def __str__(self):
        return self.nombre

    class Meta:
        ordering = ['-creado']      # orden por defecto
        verbose_name = 'Producto'
```

### Campos de Modelos más Comunes:

| Campo | Uso |
|-------|-----|
| `CharField(max_length=n)` | Texto corto |
| `TextField()` | Texto largo |
| `IntegerField()` | Entero |
| `FloatField()` | Decimal |
| `DecimalField(max_digits, decimal_places)` | Decimal exacto |
| `BooleanField()` | True/False |
| `DateField()` | Fecha |
| `DateTimeField()` | Fecha y hora |
| `EmailField()` | Email (validado) |
| `ForeignKey()` | Relación 1:N |
| `OneToOneField()` | Relación 1:1 |
| `ManyToManyField()` | Relación N:M |

### Opciones comunes de campos:
```python
nombre = models.CharField(
    max_length=100,
    null=True,      # permite NULL en BD
    blank=True,     # permite vacío en formularios
    unique=True,    # valor único
    default="N/A",  # valor por defecto
)
```

---

## Relaciones entre Modelos

```python
# 1:N — ForeignKey (uno a muchos)
class Comentario(models.Model):
    blog = models.ForeignKey(
        'Blog',
        on_delete=models.CASCADE,    # eliminar comentarios si se borra el blog
        related_name='comentarios'   # blog.comentarios.all()
    )
    texto = models.TextField()

# on_delete opciones:
# CASCADE      → elimina objetos relacionados
# PROTECT      → impide borrar si hay relacionados
# SET_NULL     → pone NULL (requiere null=True)
# SET_DEFAULT  → pone valor por defecto

# 1:1 — OneToOneField
class DetalleEmpleado(models.Model):
    empleado = models.OneToOneField(
        'Empleado',
        on_delete=models.CASCADE,
        related_name='detalle'
    )
    bio = models.TextField()

# N:M — ManyToManyField
class Estudiante(models.Model):
    nombre  = models.CharField(max_length=100)
    cursos  = models.ManyToManyField('Curso')  # crea tabla intermedia automáticamente

# N:M con tabla intermedia personalizada
class Inscripcion(models.Model):
    estudiante  = models.ForeignKey('Estudiante', on_delete=models.CASCADE)
    curso       = models.ForeignKey('Curso', on_delete=models.CASCADE)
    fecha       = models.DateField()
    calificacion = models.FloatField(null=True)

class Curso(models.Model):
    titulo      = models.CharField(max_length=200)
    estudiantes = models.ManyToManyField('Estudiante', through='Inscripcion')
```

---

## Migraciones — Flujo Completo

```bash
# 1. Definir/modificar modelo en models.py
# 2. Crear migración (genera archivo en migrations/)
python manage.py makemigrations

# 3. Aplicar migración (actualiza la BD)
python manage.py migrate

# Ver qué migraciones existen
python manage.py showmigrations

# Revertir a migración anterior
python manage.py migrate nombre_app 0003_anterior
```

**¿Qué hay en un archivo de migración?**
```python
# migrations/0001_initial.py
class Migration(migrations.Migration):
    dependencies = []      # orden de aplicación
    operations = [
        migrations.CreateModel(
            name='Producto',
            fields=[...],
        ),
    ]
```

---

## URLs (Enrutamiento)

```python
# mi_proyecto/urls.py — rutas globales
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('mi_app.urls')),          # delega a la app
    path('gestion/', include('gestion.urls')), # con prefijo
]

# mi_app/urls.py — rutas de la app
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),                    # /
    path('productos/', views.lista, name='lista'),        # /productos/
    path('productos/<int:pk>/', views.detalle, name='detalle'),  # con parámetro
    path('crear/', views.crear, name='crear'),
    path('editar/<int:pk>/', views.editar, name='editar'),
    path('eliminar/<int:pk>/', views.eliminar, name='eliminar'),
]
```

**En templates, usar `{% url %}` para no hardcodear:**
```html
<a href="{% url 'lista' %}">Ver todos</a>
<a href="{% url 'detalle' pk=producto.id %}">Ver detalle</a>
```

---

## Views (Vistas)

```python
# views.py
from django.shortcuts import render, redirect, get_object_or_404
from .models import Producto
from .forms import ProductoForm

# Vista basada en función
def lista(request):
    productos = Producto.objects.all()
    context = {'productos': productos}
    return render(request, 'mi_app/lista.html', context)

def detalle(request, pk):
    producto = get_object_or_404(Producto, pk=pk)  # 404 si no existe
    return render(request, 'mi_app/detalle.html', {'producto': producto})

def crear(request):
    if request.method == 'POST':
        form = ProductoForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('lista')
    else:
        form = ProductoForm()
    return render(request, 'mi_app/form.html', {'form': form})

def editar(request, pk):
    producto = get_object_or_404(Producto, pk=pk)
    if request.method == 'POST':
        form = ProductoForm(request.POST, instance=producto)
        if form.is_valid():
            form.save()
            return redirect('lista')
    else:
        form = ProductoForm(instance=producto)
    return render(request, 'mi_app/form.html', {'form': form})

def eliminar(request, pk):
    producto = get_object_or_404(Producto, pk=pk)
    if request.method == 'POST':
        producto.delete()
        return redirect('lista')
    return render(request, 'mi_app/confirmar_eliminar.html', {'producto': producto})
```

---

## Templates (Plantillas)

### Sintaxis del Django Template Language (DTL):

```html
<!-- Variables -->
{{ variable }}
{{ objeto.atributo }}
{{ lista.0 }}

<!-- Etiquetas (lógica) -->
{% if usuario.is_authenticated %}
  <p>Bienvenido {{ usuario.username }}</p>
{% elif condicion %}
  <p>Alternativa</p>
{% else %}
  <p>No autenticado</p>
{% endif %}

{% for producto in productos %}
  <li>{{ producto.nombre }} — ${{ producto.precio }}</li>
{% empty %}
  <li>No hay productos</li>
{% endfor %}

<!-- URL dinámica -->
{% url 'nombre_ruta' %}
{% url 'detalle' pk=producto.id %}

<!-- Archivos estáticos -->
{% load static %}
<link rel="stylesheet" href="{% static 'css/style.css' %}">
<img src="{% static 'img/logo.png' %}">

<!-- CSRF Token (OBLIGATORIO en formularios POST) -->
<form method="POST">
  {% csrf_token %}
  {{ form.as_p }}
  <button type="submit">Guardar</button>
</form>

<!-- Incluir otro template -->
{% include 'nav.html' %}
```

### Herencia de Templates:

```html
<!-- base.html — plantilla base -->
<!DOCTYPE html>
<html>
<head>
  {% load static %}
  <title>{% block title %}Mi Sitio{% endblock %}</title>
  <link rel="stylesheet" href="{% static 'css/style.css' %}">
</head>
<body>
  <nav><!-- Navbar aquí --></nav>

  <main>
    {% block content %}
    <!-- Aquí va el contenido de cada página -->
    {% endblock %}
  </main>

  <footer><!-- Footer aquí --></footer>
</body>
</html>

<!-- lista.html — plantilla hija -->
{% extends 'base.html' %}

{% block title %}Lista de Productos{% endblock %}

{% block content %}
  <h1>Productos</h1>
  {% for p in productos %}
    <p>{{ p.nombre }}</p>
  {% endfor %}
{% endblock %}
```

### Filtros en Templates:
```html
{{ nombre|upper }}           <!-- MAYÃÅ¡SCULAS -->
{{ texto|lower }}            <!-- minúsculas -->
{{ precio|floatformat:2 }}   <!-- 2 decimales -->
{{ fecha|date:"d/m/Y" }}     <!-- formato fecha -->
{{ lista|length }}           <!-- cantidad de items -->
{{ valor|default:"N/A" }}    <!-- valor por defecto si vacío -->
```

---

## Formularios Django

```python
# forms.py
from django import forms
from .models import Producto

# 1. forms.Form — no vinculado a modelo
class ContactoForm(forms.Form):
    nombre  = forms.CharField(max_length=100)
    correo  = forms.EmailField()
    mensaje = forms.CharField(widget=forms.Textarea)

# 2. forms.ModelForm — vinculado al modelo (RECOMENDADO)
class ProductoForm(forms.ModelForm):
    class Meta:
        model   = Producto
        fields  = ['nombre', 'precio', 'stock']  # campos a mostrar
        # fields = '__all__'  → todos los campos
        widgets = {
            'nombre': forms.TextInput(attrs={'class': 'form-control'}),
        }
```

**Flujo del formulario:**
1. Usuario llena el formulario (GET → mostrar)
2. Vista recibe datos (POST)
3. `form.is_valid()` → valida
4. Si válido → `form.save()` → guardar
5. `redirect()` → redirigir

**Ventajas de Django Forms:**
- Validación automática
- Protección CSRF integrada
- Renderizado automático: `{{ form.as_p }}`, `{{ form.as_table }}`

---

## ORM — Object Relational Mapper

Interactuar con la BD usando objetos Python, sin SQL.

```python
# En el shell: python manage.py shell
from mi_app.models import Producto

# CREATE — crear registro
p = Producto(nombre="Laptop", precio=999.99)
p.save()
# O también:
p = Producto.objects.create(nombre="Mouse", precio=29.99)

# READ — leer registros
Producto.objects.all()                    # todos
Producto.objects.get(id=1)               # uno exacto (error si no existe)
Producto.objects.filter(precio__gt=500)  # filtrados
Producto.objects.filter(nombre__icontains="lap")  # contiene (sin distinción mayúsculas)
Producto.objects.exclude(activo=False)   # excluir
Producto.objects.order_by('-precio')     # ordenar desc
Producto.objects.count()                 # contar

# UPDATE — actualizar
p = Producto.objects.get(id=1)
p.precio = 899.99
p.save()
# O masivamente:
Producto.objects.filter(activo=False).update(stock=0)

# DELETE — eliminar
p = Producto.objects.get(id=1)
p.delete()
# O masivamente:
Producto.objects.filter(stock=0).delete()
```

### Lookups (Filtros ORM):
```python
# Comparaciones
__gt    # mayor que
__gte   # mayor o igual
__lt    # menor que
__lte   # menor o igual
__exact  # igual exacto
__iexact # igual (sin distinción mayúsculas)
__contains  # contiene
__icontains # contiene (sin distinción mayúsculas)
__startswith / __endswith
__in    # en lista: filter(id__in=[1,2,3])
__isnull # es null: filter(campo__isnull=True)

# Ejemplo completo:
Producto.objects.filter(
    precio__gte=100,
    precio__lte=500,
    nombre__icontains="pro"
)
```

### SQL Nativo con Django:
```python
# raw() — mapea resultados al modelo
productos = Producto.objects.raw('SELECT * FROM mi_app_producto WHERE precio > 500')

# cursor() — control total
from django.db import connection
with connection.cursor() as cursor:
    cursor.execute("SELECT nombre, precio FROM mi_app_producto WHERE stock > %s", [10])
    resultados = cursor.fetchall()  # lista de tuplas
```

### Anotaciones y Agregaciones:
```python
from django.db.models import Count, Sum, Avg

# Contar comentarios por blog
from django.db.models import Count
blogs = Blog.objects.annotate(num_comentarios=Count('comentarios'))

# Suma total de precios
total = Producto.objects.aggregate(total=Sum('precio'))
```

---

## Panel de Administración

```python
# admin.py — registrar modelo
from django.contrib import admin
from .models import Producto, Categoria

# Registro simple
admin.site.register(Producto)

# Registro personalizado
@admin.register(Producto)
class ProductoAdmin(admin.ModelAdmin):
    list_display = ['nombre', 'precio', 'stock', 'activo']
    list_filter  = ['activo']
    search_fields = ['nombre']
    ordering = ['-creado']
```

```bash
# Crear superusuario para acceder
python manage.py createsuperuser
# → http://127.0.0.1:8000/admin/
```

**Aplicaciones preinstaladas de Django (INSTALLED_APPS):**
- `django.contrib.admin` — Panel de administración
- `django.contrib.auth` — Autenticación y permisos
- `django.contrib.contenttypes` — Relaciones genéricas entre modelos
- `django.contrib.sessions` — Gestión de sesiones
- `django.contrib.messages` — Sistema de mensajes flash
- `django.contrib.staticfiles` — Gestión de archivos estáticos

---

## Autenticación y Autorización

```python
# views.py — autenticación manual
from django.contrib.auth import authenticate, login, logout

def mi_login(request):
    if request.method == 'POST':
        user = authenticate(
            request,
            username=request.POST['username'],
            password=request.POST['password']
        )
        if user:
            login(request, user)
            return redirect('home')
    return render(request, 'login.html')

def mi_logout(request):
    logout(request)
    return redirect('login')
```

```python
# urls.py — vistas predefinidas de Django
from django.contrib.auth import views as auth_views

urlpatterns = [
    path('login/', auth_views.LoginView.as_view(), name='login'),
    path('logout/', auth_views.LogoutView.as_view(), name='logout'),
    path('accounts/', include('django.contrib.auth.urls')),
]
```

### Mixins para controlar acceso:
```python
from django.contrib.auth.mixins import LoginRequiredMixin, PermissionRequiredMixin
from django.views.generic import ListView

# Solo usuarios autenticados
class ProductoListView(LoginRequiredMixin, ListView):
    model = Producto
    login_url = '/login/'

# Solo usuarios con permiso específico
class ProductoDeleteView(PermissionRequiredMixin, View):
    permission_required = 'mi_app.delete_producto'
```

### Decorador para vistas de función:
```python
from django.contrib.auth.decorators import login_required

@login_required(login_url='/login/')
def mi_vista_protegida(request):
    return render(request, 'privado.html')
```

### Permisos automáticos por modelo:
- `add_producto` → crear
- `change_producto` → editar
- `delete_producto` → eliminar
- `view_producto` → ver

---

## Seguridad CSRF

**CSRF**: Cross-Site Request Forgery — ataque que fuerza acciones no deseadas.

**Protección en Django:**
- Django genera un token único por sesión
- Incluirlo en CADA formulario POST:
```html
<form method="POST">
  {% csrf_token %}
  <!-- campos del formulario -->
</form>
```
- Django verifica el token al recibir POST
- Si token no coincide → rechaza la petición

---

## Bootstrap con Django

```html
<!-- Incluir Bootstrap via CDN en base.html -->
<link rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
<script
  src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js">
</script>

<!-- Usar clases Bootstrap -->
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">...</nav>
<div class="container mt-4">
  <div class="row">
    <div class="col-md-6">...</div>
  </div>
</div>
<button class="btn btn-primary">Guardar</button>
```

**Bootstrap = framework CSS + JS** (creado en Twitter):
- Mobile First por defecto
- Grid de 12 columnas
- Componentes: navbar, cards, carousel, modal, alerts

---

##  FLUJO COMPLETO DE UN PROYECTO DJANGO

```
1. Entorno virtual
   python -m venv venv && venv\Scripts\activate

2. Instalar Django y dependencias
   pip install django psycopg2-binary

3. Crear proyecto
   django-admin startproject mi_proyecto .

4. Crear app
   python manage.py startapp mi_app

5. Registrar app en settings.py
   INSTALLED_APPS = [..., 'mi_app']

6. Configurar BD en settings.py
   DATABASES = {...}

7. Crear modelos en models.py

8. Crear y aplicar migraciones
   python manage.py makemigrations
   python manage.py migrate

9. Crear vistas en views.py

10. Crear URLs en urls.py (app + proyecto)

11. Crear templates HTML en templates/

12. Registrar modelos en admin.py

13. Crear superusuario
    python manage.py createsuperuser

14. Ejecutar servidor
    python manage.py runserver
    → http://127.0.0.1:8000/
    → http://127.0.0.1:8000/admin/
```

---

##  RESUMEN DE COMANDOS CRÍTICOS PARA EL EXAMEN

```bash
# Entorno virtual
python -m venv venv
venv\Scripts\activate

# Django
pip install django
django-admin startproject proyecto .
python manage.py startapp app
python manage.py runserver
python manage.py makemigrations
python manage.py migrate
python manage.py showmigrations
python manage.py createsuperuser
python manage.py shell

# PIP
pip install paquete
pip list
pip uninstall paquete
pip install --upgrade paquete
```

---

##  CONCEPTOS CLAVE PARA RECORDAR

| Concepto | Definición breve |
|---------|-----------------|
| **MTV** | Model-Template-View (patrón Django) |
| **ORM** | Interactuar con BD usando Python, sin SQL |
| **Migración** | Archivo que sincroniza modelos con BD |
| **makemigrations** | Detecta cambios en models.py |
| **migrate** | Aplica los cambios a la BD |
| **render()** | Devuelve template con contexto |
| **redirect()** | Redirige a otra URL |
| **get_object_or_404()** | Busca objeto o retorna error 404 |
| **context** | Diccionario de datos que se pasa al template |
| **csrf_token** | Token de seguridad en formularios POST |
| **ModelForm** | Formulario generado desde un modelo |
| **ForeignKey** | Relación 1:N entre tablas |
| **CASCADE** | Al eliminar padre, elimina hijos |
| **ACID** | Atomicidad, Consistencia, Isolación, Durabilidad |
| **DDL** | SQL para definir estructura (CREATE, ALTER, DROP) |
| **DML** | SQL para manipular datos (INSERT, UPDATE, DELETE, SELECT) |
| **Normalización** | Reducir redundancia en BD (1FN, 2FN, 3FN) |
| **Encapsulamiento** | Ocultar datos internos con atributos privados |
| **Herencia** | Clase hija reutiliza código de clase padre |
| **Polimorfismo** | Mismo método, comportamiento diferente |
