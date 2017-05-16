¡¡¡README!!!!

Esta carpeta "Proy_Final_Gissella" esta organizada así:

- La carpeta "bin" contiene todos los scripts ocupados para hacer el procesamiento y análisis del proyecto, estos son:
	
	- 1_Demulti_ipyrad.sh : Script para hacer demultiplexing con ipyrad
	- 2_cutadapt.sh :Script para quitar adaptadores con el programa cutadapt
	- 3_Trimming_calidad.sh: Script para hacer trimming y filtrado de calidad con
	    fastxTools en Docker
	- 4_Ensamblado_SNPs.sh : Script para hacer ensamblado de novo y llamado de SNPs con
	  ipyrad
	- 5_FastTree.sh : Script para generar un árbol en FastTree de Docker con un 
	  alineamiento de SNPs
	- 6_Arbol_gene.R: Script en R para editar el arbol generado en FastTree
	- 7_Pop_Coor.R : Sript para ubicar las poblaciones de Hypsiboas pugnax en un mapa de
	  GoogleMaps
	- 8_SNPrelate.R : Script para correr un PCA en R con la paqueteria SNPrelate
	- params-Hypsiboas.txt : archivo de parametros necesario para correr el Scrip 1
	- params-Hypsiboas2.txt : archivo de parametros necesario para correr el Scrip 4
	

-La carpeta "data" contine varias carpetas distribuidad Así:

	- Raw : contiene dos archivos uno llamado "C9ME6ANXX_7_fastq.gz" que se encuentra
	  vacío y representa el archivo de datos crudos que contiene los 96 individuos; otro
	  llamado "Barcodes1.txt".
	  	- Hypsiboas_fastqs : esta carpeta contiene dos archivos fastqs como ejemplo de lo
	  	 	que resultó después del Demultiplexing
	- Sin_Adap : carpeta que contiene ejemplos de los archivos resultantes despues de 
	  correr los scripts de para cortar adaptadores, trimming, filtrado de calidad.
			-Hypsiboas2_outfiles : contiene los archivos de SNPs resultantes después de
			 correr el script 4
	  	
-la carpeta "Graficas" contiene los siguientes archivos:
	-

- Un archivo llamado "Proyecto_Giss.md" que contiene la descripción de los análisis
 	realizados en el proyecto