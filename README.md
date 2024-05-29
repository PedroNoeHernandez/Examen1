TShit

# EXAMEN A

El examen consta de 4 apartados técnicos (preguntas) y 6 preguntas teóricas.

Cada apartado técnico contestado correctamente tendrá un valor de 4 puntos.
Cada pregunta teórica tendrá un valor de un punto.
Dando un total de 22 puntos posibles.

 Técnico: 4*4 = 16
+Teórico:        6
--------------------
                22

Esta actividad no cuenta con el código para copiar y pegar en las instrucciones como en los laboratorios.

El alumno puede usar chatGPT, o cualquier otro asistente de Inteligencia artificial para resolver la parte técnica, stackoverflow para revisar errores y w3school para documentarse.

El alumno NO puede utilizar videos de youtube, utilizar su teléfono durante el examen ni solicitar ayuda para resolver el examen.

Solo se atenderán dudas de las instrucciones.

## Prueba el correcto funcionamiento de la app 



```python --version```
```pip install mysql-connector-python```
```pip install rsa```
```flask --app main run --debug```


## Parte técnica

### Pregunta1
Pon las credenciales de la base de datos que el profesor te proporcionará en el archivo config.json

### Pregunta2
Crea un MODELO nuevo llamado ```color``` en app/cmodels que sirva para abstraer la siguiente tabla (nota que el último valor está mal escrito, respeta este error en tu código):
```sql
CREATE TABLE color(
	id varchar(16) PRIMARY KEY,
	name varchar(40),
	primaryColorCode varchar(6), --#hexadecimal color
	secondaryColoir varchar(6) --#hexadecimal color
);
```
Puedes utilizar los archivos app/models/user.py y app/models/proveedor/proveedor.py como referencia

### Pregunta 3
Crea un Controlador para que extienda de app/controllers/CtrlMain.py con los métodos generateId,insert y getAll que manden allamar la función snowflake, inserte un nuevo elemento en la base de datos y liste todos los elementos en la base de datos respectivamente, aquí tiene un prototipo de dicho controlador
```python
from app.models.color import color
from app.controllers.CtrlMain import CtrlMain
from app.database.mysqlConn import mysqlConn
class CtrlColor(CtrlMain):
    def __init__(self,color:color=None):
        if(color!=None):
            self.color=color
        self.connect = mysqlConn(self.conn)
    
    def generateId(self):
        #... 

    def insert(self):
        self.connect.start()
        self.generateId()
        #...

    def getAll(self,id):
        self.connect.start()
```
Utiliza app/controllers/CtrlProveedor.py como referencia.

### Pregunta 4

Crea un modulo ```color``` en ```app/modules``` que implemente un Blueprint de flask.
Crea las rutas para Get y Post mostrar todos los colores y para crear colores en el módulo.
Mándalo a llamar en el módulo creado en el archivo main.py

Usa de referencia app/modules/proveedores.py y app/modules/auth.py

No olvides importar los elementos previamente creados.

## Preguntas
Responde estas preguntas en este archivo.

1.- ¿Qué es un módelo?

2.- ¿Qué es un controlador?

3.- ¿Cuáles son los métodos para Métodos de petición HTTP más comunes?

4.- ¿Qué es un tablero de control?(en administración de proyectos informáticos)

5.- ¿Cuál es la objeto de Javascript que nos premite hacer solicitude HTTP?

6.- ¿Por qué teniendo todo el semestre para hacer 6 laboratorios sencillo donde solo copiabas y pegabas código y hacer un tutorial de youtube de 1 hora para hacer un CRUD preferiste hacer este examen?
