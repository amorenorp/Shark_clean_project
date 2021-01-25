# Shark Storytelling Project
![sharkimg](https://github.com/amorenorp/Shark_clean_project/blob/main/images/sharkimg.jpg)


En este proyecto he utlizado el documento [Shark Attack] (https://www.kaggle.com/teajay/global-shark-attacks) descargado de Kaggle .



# Storytelling


Supongamos que surge la idea de realizar una nueva modalidad de Triathlon cuyos deportes sean el surf, swimming y fishing. 


El proposito de este ejericio es obtener una respuesta a las siguientes preguntas:

- ¿qué paises serian los más peligrosos para realizar este nuevo deporte? 
- ¿por cual de los deportes se sienten más atraido los tiburones? 
- ¿son esos ataques letales?


 # Data Cleanning

Nos encontramos ante un archivo CSV con mucho errores, vamos a limpiarlo lo maximo posible: 

Comienzo quitando los espacios en blanco que hay en los nombres de columna y reorganizando el index para así poder usar la columna Case Number que mas adelante será clave para obtener el año de cada ataque.

Compruebo si hay columnas duplicadas como lo son Case Number.1 ,Case Number.2. 

Tras echarle un vistazo a lo que me ofrece cada columna decido quedarme solo con 7 de ellas. 

Compruebo los valor nulos con "isnull().sum" y procedo a eliminar las filas cuyos valores son todos NULL.
Aun quedan algunas filas que son todos los valores nulos excepto la columna Case Number. 
Elimino esos nulos. 

Creo una nueva columna "Year1" con la obtengo el año de cada ataque, sacandolo de la columna Case Number porque es la que tenia un formato mas limpio de todas las que habia con fechas. Y limpio los NA de Year1

Vuelvo a eliminar columnas y me quedo con 5 : Year , Country , Activity , Sex y Fatal.

Vamos a limpiar estas columnas:

La columna **Dead** tiene valores nulos, creo una nueva a partir de esa que se va a llamar "dead" donde solo hay 3 valores : Yes, No y NA , usando replace.

Comienzo con la columna **Country**,  pongo todo los nombres en miniscula y observo que hay una gran cantidad diferente de paises. 
Decido quedarme con el Top 5 , creando una variable para cada uno y luego concatenando todo en un nuevo dataframe que se llama Sharkfinal.

Limpio la columna **Sex** usando replace : F , M y Uknown.

para la columna **Activity** realizo lo mismo que para Country

Reseteo el index y elimino la columna Fatal que ha sido sustituida por "dead". 

Guardo la nueva tabla como "sharkfinallimpio.csv"


Tras la limpieza , he creado un nuevo archivo **sharl_storytelling.ipynb** donde se puede ver un resumen organizado en graficos para que sea mas visual y atractivo. 


## *Referencias y bibliotecas:*

 - Kaggel 
 - Seaborn
 - Pandas 
 - Matplotlib
