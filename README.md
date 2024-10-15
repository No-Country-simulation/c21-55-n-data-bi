# c21-55-n-data-bi
Equipo Data
**Tema:** Análisis de Rendimiento Académico
**Descripción del Proyecto:** Analizar el rendimiento académico de estudiantes en una institución educativa utilizando datos de calificaciones, asistencia y participación en actividades extracurriculares.
**Participantes:** Lorena Maza https://www.linkedin.com/in/lorena-maza/

## Inicio del proyecto
Luego de una búsqueda exhaustiva, sin éxito, de un set de datos para comenzar el análisis, decidí generar datos aleatorios con base en un set que contenía información acerca de las Universidades Argentinas que dictan Carreras Culturales.
El DataSet original puede descargarse de https://datos.cultura.gob.ar/dataset/agentes-culturales-argentina/archivo/558d9a3c-6b9f-4f20-8605-d22c0398e4c1

## IMPORTACIÓN DE DATOS A EXCEL
Tras la importación de los datos al Excel:
*	se corrigieron los caracteres especiales para su correcta visualización. Por ejemplo se transformó Ã­ en í;
*	se eliminaron datos duplicados;
*	se eliminaron columnas que no aportaban relevancia al análisis;
*	se estandarizó la duración de las carreras, puesto que en algunos casos venía expresada en cuatrimestres y en otro en años. Se optó por años;
*	se cambiaron los Identificadores de INT a VARCHAR, realizando la correspondiente modificación de todos los valores

##NORMALIZACIÓN
El DataSet se trabaja en Microsoft Excel para normalizar la tabla original, separando los datos en distintas hojas:
