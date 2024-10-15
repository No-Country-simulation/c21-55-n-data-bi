# c21-55-n-data-bi
* Equipo Data
* **Tema:** Análisis de Rendimiento Académico
* **Descripción del Proyecto:** Analizar el rendimiento académico de estudiantes en una institución educativa utilizando datos de calificaciones, asistencia y participación en actividades extracurriculares.
* **Participantes:** Lorena Maza https://www.linkedin.com/in/lorena-maza/

## INICIO DEL PROYECTO
Luego de una búsqueda exhaustiva, sin éxito, de un set de datos para comenzar el análisis, decidí generar datos aleatorios con base en un set que contenía información acerca de las Universidades Argentinas que dictan Carreras Culturales.
El DataSet original puede descargarse de https://datos.cultura.gob.ar/dataset/agentes-culturales-argentina/archivo/558d9a3c-6b9f-4f20-8605-d22c0398e4c1

## IMPORTACIÓN DE DATOS A EXCEL
Tras la importación de los datos al Excel:
*	se corrigieron los caracteres especiales para su correcta visualización. Por ejemplo se transformó Ã­ en í;
*	se eliminaron datos duplicados;
*	se eliminaron columnas que no aportaban relevancia al análisis;
*	se estandarizó la duración de las carreras, puesto que en algunos casos venía expresada en cuatrimestres y en otro en años. Se optó por años;
*	se cambiaron los Identificadores de INT a VARCHAR, realizando la correspondiente modificación de todos los valores

## NORMALIZACIÓN
El DataSet se trabaja en Microsoft Excel para normalizar la tabla original, separando los datos en distintas hojas:
* DatosUniversidades: IDUniversidad; IDFacultad; Domicilio; CP; IDLocalidad; Latitud; Longitud; IDGestion; Web; E-Mail
* Titulos: IDTitulo; Titulo; IDNivel; IDUniversidad; IDFacultad; IDModalidad; Duración; Vigencia; IDTematica; FechaActualizacion
* Facultades: IDFacultad; Facultad
* Universidades: IDUniversidad; Universidad
* Niveles: IDNivel; Nivel
* Gestion: IDGestion; TipoGestion
* Modalidades: IDModalidad; TipoModalidad
* Tematicas: IDTematica; Temática
* Provincias: IDProvincia; Provincia
* Departamentos: IDProvincia; IDDepartamento; Departamento
* Localidades: IDDepartamento; IDProvincia; IDLocalidad; Localidad

## COMPLEMENTO DE DATOS
Para complementar la información sobre las instituciones, generé una lista de datos de alumnos utilizando la versión Free de https://www.mockaroo.com/schemas/new (1000 registros)
Solicitando como Campos: DNI; Nombre; Apellido; Edad (Se adjunta imagen de la configuración de campos).

Dicho Set se adjunta a los datos trabajados anteriormente, incorporando la tabla Alumnos. A continuación, en Excel se generan nuevos campos en esta tabla:
* IDTítulo: generado a partir de =Indice(IDTitulos;Aleatorio.entre(1;Contar(IDTitulos)))
* Duración: generado a partir de =BUSCARV(E2;Titulos!$A$1:$J$1477;8;0)
* Permanencia: generado a partir de =Aleatorio.entre(1;10)
* Cant_Materias: generado a partir de =Redondear.mas(duracion*7;0)
* Materias_Cursadas: generado a partir de =SI(J2="Adeuda Tesis";H2;SI(O(J2="Continúa";J2="Abandonó");ALEATORIO.ENTRE(1;H2-1);H2+1))
* Estado: generado a partir de =SI((G2-F2)<0;"Abandonó";Si(G2=F2;Indice(Estados;Aleatorio.entre(1;3));Indice(Estados;Aleatorio.entre(1;4))))

## LINEAS A CONTINUAR
* Se podría agregar un listado de materias por Carrera y asociar la cursada de cada alumnos con sus notas para tener una variable más del rendimiento
* O se podría dejar en el estado actual y llevar los datos a Locker Studio para iniciar el análisis y visualización
