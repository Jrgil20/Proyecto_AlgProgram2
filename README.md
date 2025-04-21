# CentroDeEstudiantes
Este es el proyecto academico desarrollado en la materia de algoritmos y programacion 2, basado en el lenguaje de programacion C++, el cual tiene como objetivo la gestion de registros de estudiantes, cursos y materias.

Bajo la supervision del profesor: Omar Jesus Hernandez

## Tabla de Contenidos
- [Descripción General y Propósito](#descripción-general-y-propósito)
- [Requisitos del Sistema](#requisitos-del-sistema)
- [Instalación](#instalación)
- [Uso del Sistema](#uso-del-sistema)
- [Estructuras de Datos](#estructuras)
- [Funciones Principales](#funciones-principales)
- [Archivo y Persistencia de Datos](#importación-y-exportación)
- [Contribuidores](#contribuidores)
- [Licencia](#licencia)

## Descripción General y Propósito

El proyecto `CentroDeEstudiantes` está diseñado para gestionar registros de estudiantes, cursos y materias en una institución educativa. Proporciona funcionalidades para agregar, modificar, eliminar y consultar información sobre estudiantes, cursos y materias. El objetivo principal es facilitar la administración académica y el seguimiento del desempeño estudiantil.

## Requisitos del Sistema

Para compilar y ejecutar este proyecto necesitas:
- Compilador de C++ compatible con C++11 o superior
- Al menos 64MB de RAM
- Sistema operativo Windows o Linux

## Instalación

Para instalar y configurar el sistema en tu equipo local:

1. Clona el repositorio:
```bash
git clone https://github.com/usuario/CentroDeEstudiantes.git
```

2. Navega al directorio del proyecto:
```bash
cd CentroDeEstudiantes
```

3. Compila el programa:
```bash
g++ CentroDeEstudiantes.cpp -o CentroDeEstudiantes
```

4. Ejecuta el programa:
```bash
./CentroDeEstudiantes
```

## Uso del Sistema

El sistema presenta un menú principal con tres opciones:

1. **MANTENIMIENTO**: Para gestionar las tablas base del sistema (materias, cursos y personas).
2. **CONTROL DE ESTUDIOS**: Para gestionar la inscripción de estudiantes en cursos.
3. **CONSULTAS**: Para realizar diversas consultas sobre el sistema.

### Ejemplo de uso:

1. Selecciona la opción 1 (MANTENIMIENTO)
2. Selecciona la opción 1 (MATERIAS)
3. Selecciona la opción 1 (AGREGAR)
4. Sigue las instrucciones para ingresar los datos de la materia

## Estructuras

### Materias

La estructura `Materias` representa una asignatura académica e incluye los siguientes campos:
- `Codigo_de_la_Materia`: Código único de la materia (no se puede repetir).
- `Nombre_de_la_Materia`: Nombre de la materia (no debe estar vacío).
- `Descripcion_de_la_Materia`: Descripción detallada de la materia (no debe estar vacía).
- `Semestre`: Semestre en el que se ofrece la materia (rango: 1 a 10).
- `SemestreEnRomano`: Representación del semestre en números romanos (I a X).
- `Creditos_de_la_Materia`: Créditos académicos de la materia (rango: 2 a 5).
- `prx`: Puntero a la siguiente materia en la lista.

### Cursos

La estructura `Cursos` representa un curso específico de una materia y incluye:
- `Codigo_del_curso`: Código único del curso.
- `Codigo_de_la_Materia`: Código de la materia asociada (debe existir previamente).
- `AAAA`: Año en que se ofrece el curso (rango: 1900 a 2100).
- `lapso`: Período académico en que se ofrece (rango: 1 a 3).
- `prx`: Puntero al siguiente curso en la lista.

### Personas

La estructura `Personas` representa a un estudiante e incluye:
- `cedula`: Número de identificación único (cédula) del estudiante (no se puede modificar).
- `nombre_apellido`: Nombre y apellido del estudiante.
- `Fecha_de_Nacimiento`: Fecha de nacimiento del estudiante.
- `direccion`: Dirección del estudiante.
- `Record`: Puntero a la lista de participaciones del estudiante en cursos.
- `prx`: Puntero a la siguiente persona en la lista.

### Participacion

La estructura `Participacion` representa la inscripción de un estudiante en un curso:
- `Codigo_del_curso`: Código del curso en el que participa el estudiante.
- `nota`: Calificación obtenida por el estudiante (0-20).
- `status`: Estado del estudiante en el curso ('N' normal, 'I' inasistente, 'R' retirado).
- `prx`: Puntero a la siguiente participación del estudiante.

## Funciones Principales

### Agregar Registros

El proyecto proporciona funciones para agregar nuevos registros:
- `Agregar_Materia`: Agrega una nueva materia a la lista de materias.
- `Agregar_Curso`: Agrega un nuevo curso a la lista de cursos.
- `Agregar_Persona`: Agrega un nuevo estudiante a la lista de personas.
- `Agregar_Curso_persona`: Inscribe a un estudiante en un curso.

### Modificar Registros

El proyecto proporciona funciones para modificar registros existentes:
- `Modificar_Materia`: Modifica los detalles de una materia existente.
- `Modificar_Curso`: Modifica los detalles de un curso existente.
- `Modificar_Persona`: Modifica los detalles de un estudiante existente.
- `Modificar_Curso_persona`: Modifica la inscripción de un estudiante en un curso.

### Eliminar Registros

El proyecto proporciona funciones para eliminar registros:
- `Eliminar_materia`: Elimina una materia y sus cursos asociados.
- `Eliminar_curso`: Elimina un curso y sus referencias en el sistema.
- `Eliminar_persona`: Elimina un estudiante y sus participaciones.
- `Eliminar_curso_persona`: Elimina la participación de un estudiante en un curso.

## Otras Funciones Importantes

El proyecto también incluye funciones para consultar y generar reportes:
- `Consultar_materia`: Consulta y muestra detalles de materias.
- `Consultar_curso`: Consulta y muestra detalles de cursos.
- `Consultar_Personas`: Consulta y muestra detalles de estudiantes.
- `C_NombreMateria`: Busca materias por nombre y muestra sus cursos asociados.
- `C_NombreAlumno`: Busca estudiantes por nombre y muestra sus detalles.
- `c_Materia`: Muestra los detalles de una materia y sus cursos asociados.
- `c_CursosDePeriodo`: Muestra los cursos ofrecidos en un semestre específico.
- `C_Aprobados`: Muestra los estudiantes que han aprobado una materia.
- `C_Cursos`: Muestra todos los cursos con sus estudiantes y calificaciones.
- `C_CursosDeAnyoLapso`: Muestra los cursos de un año y lapso específicos.
- `C_Alumno`: Muestra los cursos y calificaciones de un estudiante específico.

## Importación y Exportación

El sistema permite guardar y cargar datos desde archivos:
- `Exportar_Materias`, `Exportar_Cursos`, `Exportar_Personas`: Guardan datos en archivos.
- `Importar_Materias`, `Importar_Cursos`, `Importar_Personas`: Cargan datos desde archivos.

## Reglas del Sistema

- Un alumno solo puede tener aprobada una materia una vez; luego no puede reinscribirla.
- Un alumno puede reprobar una materia máximo 4 veces; después no podrá inscribirse más.
- Un alumno puede retirar una materia un número ilimitado de veces.
- Cuando se elimina una materia, se eliminan todos los cursos asociados.
- Cuando se elimina un curso o un alumno, se eliminan todas sus referencias en el sistema.

## Contribuidores

Este proyecto fue desarrollado por:
- Gabriel Castellano (C.I: 28059781)
- Jesus Gil (C.I: 30175126)
- Andres Guilarte (C.I: 30246084)

## Licencia

Este proyecto es para fines académicos. Todos los derechos reservados.
