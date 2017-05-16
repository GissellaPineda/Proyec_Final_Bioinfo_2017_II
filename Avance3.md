# Proyecto Final Bioinf2017-II

## Avance 3

Inicialmente, como comenté en los primeros avances, la especie se llamaba *Hypsioboas crepitans*, sin embargo después de revisar
literatura y basado en la opinion de una persona que conoce el género se aclaró que el subset de datos que tomé corresponde a su
especie hermana *Hypsiboas pugnax* por lo que en adelante me referiré a ella así.
Debido a que los datos crudos contenian información tanto de *H. crepitans** como de *H. pugnax*, se seleccionó nuevamente el 
subset el cual difiere del originalmente planteado en el avance 1 y 2; en adelante las pobalciones se llamarán **Armero**, 
**PurificaciónA** y **PuruficaciónB** . El replanteamiento de las pobalciones no generó ningún conflicto ya que debido a 
un error que tuve en el paso de demultiplexing la primera vez que use los datos tuve nuevamente que correr algunos script 
en los cuales usé el nuevo subset.

Ya he corrido los siguientes Scripts:

* 1_Demulti_ipyrad.sh : Script para hacer demultiplexing con ipyrad
* 2_cutadapt.sh :Script para quitar adaptadores con el programa cutadapt
* 3_Trimming_calidad.sh: Script para hacer trimming y filtrado de calidad con
	    fastxTools en Docker
* 4_Ensamblado_SNPs.sh : Script para hacer ensamblado de novo y llamado de SNPs con
	  ipyrad
* 5_FastTree.sh : Script para generar un árbol en FastTree de Docker con un 
	  alineamiento de SNPs
*6_Arbol_gene.R: Script en R para editar el arbol generado en FastTree
* 7_Pop_Coor.R : Sript para ubicar las poblaciones de Hypsiboas pugnax en un mapa de
	  GoogleMaps
* 8_SNPrelate.R : Script para correr un PCA en R con la paqueteria SNPrelate

Ya tengo organizado el proyecto en carpetas, el Markdown está parcialmente listo y el [README](https://github.com/GissellaPineda/Proyec_Final_Bioinfo_2017_II/blob/master/Avance_README_proy.txt) 
está descrito aproximadamente a la mitad.

El proyecto está casi terminado, no puse la descripción de los codigos usados para cada script porque eso esta expicado en el Markdown que 
adjuntaré en la entrega final.

Debido a que estaré en campo un par de semanas leeré los comentarios y sugerencias después del 29 de mayo y les entregaré el proyecto el 2 de Junio
como habiamos acordado.

Pregunta: EL archivo crudo original está representado por un txt vacío dentro de la carpeta raw, esto debido a su tamaño, pero de ahí en adelante de todos
los archivos resultantes de cada script puse un o dos archivos representativos. Esta bien así?