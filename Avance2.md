# Proyecto Final Bioinf2017-II

## Avance 2

El archivo original de los datos crudos de GBS  de *Hypsiboas crepitans* provenientes del secuenciador de Illumina tiene un tamaño 18.71 GB comprimido; hasta la fecha he realizado:

**1**. Un revisión del archivo crudo  para ver el estado de las secuencias con **FastQC**, usé la interfaz gráfica de este programa.

**2** Debido a que el archivo es muy grande, lo primero que hice fue el **demultiplexing** para tener las secuencias de cada individuo en un archivo por separado y así poder seleccionar un subconjunto de datos que pueda que manejar en mi laptop. El demultiplexing lo hice con el programa **ipyrad**; este programa es facil de instalar y tiene un tutorial cómodo de entender. Para este paso tenia que tener a la mano el archivo txt de los **barcodes** y otro archivo txt de **parámetros**, dentro de este archivo de parámetros sólo modifiqué el directorio que conduce a los datos y al archivo de barcodes, los demás parámetros se quedaron por default porque sólo me interesaba hacer el paso de demultiplexing, el comando de **ipyrad** para este paso es:

	`ipyrad -p params-Hypsiboas.txt -s 1` 
		
**3**. Después del paso anterior obtuve una carpeta con 96 archivos que corresponde a cada individuo; seleccioné tres poblaciones llamadas: **Orquideas** (10), **San Jorge** (10) y **Picaleña** (4) para un total de **24** individuos que ocuparé en mi trabajo; decidí tomar estas poblaciones porque se encuentran ubicadas alrededor de la ciudad de Ibagué Colombia, me parece interesante ver que resultados puedo obtener de la estructura genética de estos anfibios que como se sabe no tienen una alta dispersión.


**4**.El siguiente paso fue **quitar los adaptadores**, inicialmente queria usar el programa **Skewer** pero tuve algunos problemas con la instalación, así que decidí probar con **cutadapt**, a este programa debía indicarle la secuencia, el nombre del archivo de salida y el nombre del archivo de entrada así:

	`cutadapt -a GCAAGCCAT -o 018.fastq.gz 018:C9ME6ANXX:7:486037_R1_.fastq.gz` 
	
**5**. Seguido decidí hacer otro **FastQC** para ver el estado de cada secuencia y así poder elegir los parámetros de trimming y filtrado.

**6**. Luego ocupé el programa **fastxTools kit** en un contenedor de **Docker** para realizar limpieza de las secuencias, **trimming, filtrado de calidad y limpieza de artefactos**; aunque antes de esto, descomprimí los archivos `gunzip *.fastq.gz`. 

Después de crear y activar el contenedor, hice un `for loop` para correr cada comando así:

	`for i in *.fastq;do fastx_trimmer -f 1 -l 80  -i $i -o trimmer$i; done`


	`for i in trimmer*.fastq; do fastq_quality_filter -q 20 -p 50 -i $i -o calidad$i; done`


	`for i in calidad*.fastq; do fastx_artifacts_filter -v -i $i -o Artef$i; done`

Para el caso de filtrado por calidad he probado varios valores para el parametro de porcentaje `-p` *50, 55, 60, 65, 70, 75, 80, 85, 90*; después de correr cada uno de los comandos anteriores, realicé varios **fastQC** para ver el estado de las secuencias después de los distintos filtros.

**7**. En el momento me encuentro explorando filtrados con **VCFtools** en **Docker** para ver cuál programa me arroja mejores resultados y así continuar con el siguiente paso del procesamiento.
