# 📚 Sistema de Gestión Literaria

Aplicación desarrollada como parte de un reto técnico de especialización Back-End. Su propósito es facilitar la exploración, organización y análisis de libros y autores, integrando datos externos y almacenamiento local.

---

## 📝 Descripción General

Este sistema permite:

- Buscar libros por título.
- Consultar autores por nombre.
- Listar libros y autores registrados.
- Filtrar autores vivos en un año específico.
- Mostrar libros por idioma.
- Obtener estadísticas generales.
- Ver los libros más descargados.
- Consultar autores nacidos o fallecidos en un año determinado.

La aplicación se conecta a una API pública para obtener información literaria y utiliza una base de datos relacional para almacenar los datos de forma persistente.

---

## 💻 Tecnologías Utilizadas

- **Java** – Lenguaje principal del proyecto.
- **Spring Framework** – Para la gestión de dependencias y acceso a datos.
- **API externa** – Fuente de información sobre libros y autores.
- **Base de datos relacional** – Persistencia de datos (H2, MySQL, etc.).
- **Git** – Control de versiones.
- **IDE** – Desarrollo y depuración (por ejemplo, IntelliJ IDEA).

---

## 🧩 Estructura del Proyecto

### `Principal.java`

Clase principal que gestiona la interacción con el usuario mediante consola. Presenta un menú con todas las funcionalidades disponibles.

### `ConsumoApi.java`

Encargada de realizar peticiones HTTP a la API externa para obtener datos literarios.

### `ConvierteDatos.java`

Transforma la respuesta JSON de la API en objetos internos que la aplicación puede utilizar.

### `AutorRepository.java`

Interfaz que gestiona las operaciones CRUD relacionadas con los autores en la base de datos.

---

## 🗃️ Modelado de Entidades

### `Autor.java`

Representa a un autor con los siguientes atributos:

- `id`: Identificador único.
- `nombre`: Nombre completo.
- `fechaDeNacimiento`: Año de nacimiento.
- `fechaDeFallecimiento`: Año de fallecimiento (puede ser nulo).
- `libros`: Lista de libros asociados.

### `Datos.java`

Mapea la respuesta general de la API:

- `total`: Número total de resultados.
- `libros`: Lista de objetos `DatosLibro`.

### `DatosLibro.java`

Contiene información de cada libro:

- `titulo`
- `autores`
- `idiomas`
- `numeroDeDescargas`

---

## 🔄 Persistencia con JPA

Se utilizan las siguientes anotaciones para mapear las clases a la base de datos:

- `@Entity`
- `@Table`
- `@Id`
- `@GeneratedValue`
- `@Column`
- `@OneToMany`

Estas permiten que las entidades se integren con la base de datos relacional y se gestionen mediante repositorios.

---

## 🚀 Cómo Ejecutar el Proyecto

1. Clona el repositorio en tu equipo local.
2. Abre el proyecto en tu IDE favorito.
3. Configura la conexión a la base de datos en el archivo de propiedades.
4. Ejecuta la clase `Principal.java`.
5. Usa el menú interactivo para explorar libros, autores y estadísticas.
