#############################################################################################
#Algoritmo PFS provide functions to implement the PFS and the PFS-US algorithms

#Copyright 2017 Carlos Daniel Hernandez Mena 
#Contact: carlos.mena@ciempiess.org

#This file is part of Algoritmo PFS

#    Algoritmo PFS is free software: you can redistribute it and/or modify
#    it under the terms of the GNU General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.

#    Algoritmo PFS is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU General Public License for more details.

#    You should have received a copy of the GNU General Public License
#    along with Algoritmo PFS.  If not, see <http://www.gnu.org/licenses/>.
#############################################################################################
Content of the Algoritmo_PFS directory
#############################################################################################

At the Algoritmo_PFS directory you can find 2 different scripts:

- Algoritmo_PFS_Ejemplo.py : Script for testing the codigo_pfs() function.

- Algoritmo_PFS-US_Ejemplo.py : Script for testing the codigo_pfs_us() function.

And also you can find three directories:

- fonetica3 : Contains functions to perform phonetic and phonological transcriptions to 
              spanish words. You can download the most recent version of the 
              "fonetica3 library" from: http://www.ciempiess.org/downloads

- libpfs : Contains Python functions called by the scripts: "Algoritmo_PFS_Ejemplo.py"
           and "Algoritmo_PFS-US_Ejemplo.py". These functions perform the PFS and the
           PFS-US algorithms. There is also a function needed to read the rules-file
           in the "REGLAS" directory.

- REGLAS : Contains the rules-files needed by the two PFS algorithms.

The functions in the "libpfs" directory are: 

- leer_reglas() : This function allows the codigo_pfs() and the codigo_pfs_us()
                  functions to read a rules-file in the "REGLAS" directory.

- codigo_pfs() : Converts an incoming word into a phonetic code, according to the PFS
                 algorithm and the phonetic rules specified in the rules-file.

- codigo_pfs_us() : Converts an incoming word into a phonetic code, according to the 
                    PFS-US algorithm and the phonetic rules specified in the rules-file. 
                    The "-US" means "Ultima Sílaba" = "last syllable". It means that the 
                    PFS-US algorithm preserves the last syllable of the incoming word, 
                    untouched.

NOTICE THAT: The functions codigo_pfs() and codigo_pfs_us() accept Spanish words in 
lowercase as arguments. These words can have the tonic vowel marked in uppercase or not 
(e.g. cAldo, aviOn, comida, etc.).

#############################################################################################
System Requirements
#############################################################################################

You need to install:

python 2.7

#############################################################################################
INSTRUCTIONS FOR USING THE Algoritmo PFS PACKAGE
#############################################################################################

Every script with the suffix _Ejemplo.py must be placed at the same level of the
fonetica3, libpfs and REGLAS directories. You can run them this way:

	$ python <script_name>_Ejemplo.py <REGLAS/<rules-file>

This may produce a result in the command line.

For example, to run the script Algoritmo_PFS_Ejemplo.py you go to the Algoritmo_PFS directory

	$ cd Algoritmo_PFS

An then

	$ python Algoritmo_PFS_Ejemplo.py REGLAS/reglas_pfs.txt

This produces:

179-179-293-s99_76
179-179-293-s99_76


If you inspect the code of every of these testing scripts you will see
lines of code similar to these, for adding functions of the libpfs 
directory into your code:

	#Modulo para funciones del sistema operativo
	import sys

	#Añadir el path donde estan las carpeta "fonetica3" y "libpsf"
	sys.path.append(".")

	#Modulo creado por mi donde viene la funcion leer_reglas()
	from libpfs.leer_reglas import leer_reglas

	#Modulo creado por mi donde viene la funcion codigo_pfs()
	from libpfs.codigo_pfs_us import codigo_pfs_us


Based on these, you can include the functions of the Algoritmo_PFS package
easily into your code.

#############################################################################################
       You downloaded the Algoritmo PFS from the CIEMPIESS-UNAM Project website at

                                 www.ciempiess.org
#############################################################################################

