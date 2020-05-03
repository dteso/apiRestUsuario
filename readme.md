


A P I    R E S T    U S U A R I O

> a p i  R E S T  u s u a r i o

Se trata de una proyecto base de un API rest para gestión de usuarios desplegada en Heroku



To run mongo Database:SEED
"C:\Program Files\MongoDB\Server\4.2\bin\mongod.exe" --dbpath="c:\data\db"

+++++++++++++++++++++++++++++++++++++++++++++++++++

"C:\Program Files\MongoDB\Server\4.2\bin\mongo.exe" o la ruta donde el usuario que haga uso del proyecto tengo su ejecutable de mongo

+++++++++++++++++++++++++++++++++++++++++++++++++++


MongoDb 


1. Create database directory.
Create the data directory where MongoDB stores data. MongoDB’s default data directory path is the absolute path \data\db on the drive from which you start MongoDB.

From the Command Interpreter, create the data directories:

cd C:\
md "\data\db"


2. Start your MongoDB database.
To start MongoDB, run mongod.exe.

"C:\Program Files\MongoDB\Server\4.2\bin\mongod.exe" --dbpath="c:\data\db"
The --dbpath option points to your database directory.

If the MongoDB database server is running correctly, the Command Interpreter displays:

[initandlisten] waiting for connections
IMPORTANT

Depending on the Windows Defender Firewall settings on your Windows host, Windows may display a Security Alert dialog box about blocking “some features” of C:\Program Files\MongoDB\Server\4.2\bin\mongod.exe from communicating on networks. To remedy this issue:

Click Private Networks, such as my home or work network.
Click Allow access.
To learn more about security and MongoDB, see the Security Documentation.

3. Connect to MongoDB.
To connect a mongo.exe shell to the MongoDB instance, open another Command Interpreter with Administrative privileges and run:

"C:\Program Files\MongoDB\Server\4.2\bin\mongo.exe"
For more information on connecting a mongo.exe shell, such as to connect to a MongoDB instance running on a different host and/or port, see The mongo Shell. For information on CRUD (Create,Read,Update,Delete) operations, see:

Insert Documents
Query Documents
Update Documents
Delete Documents
/********************************************************************/




GIT PROCESS 

1. git init
2. git add .  ---> Stage all
3. git commit -m "initial commit"
4. git status  ---> Para comprobar el estado actual 
5. git remote add origin https://github.com/dteso/apiRestUsuario.git   Seteo el origin a gitHub
6. git push -u origin master ---> PUSH  a Master


- Creación del release
--------------------------------------------------------------------
1. git tag -a v0.0.0 -m "VersiónAlpha-Base"
2. git tag
3. git push --tags
/********************************************************************/



PROCESO 

1º Server

2º Config ( para el enviroment )

4º Conexión a base de datos 

3º Rutas
/********************************************************************/




HEROKU 

> Para subir a heroku:

  1. Sign in en la página de heroku

  2. Añadir el proyecto con nombre único ( sólo minúsculas )

  Hay que inicizalizarlo como un proyecto git
  de forma que antes de seguir, crear el .gitignore
  e incluir node_modules/

  3. git init

  4. git satus

  5. git add . ---> stage all 

  6. git commit -m  'nombre_del_commit'

  7. heroku login ---> abrirá navegador y solicita credenciales ( en teoría sólo una vez por máquina ) y nos dará confirmación en la consola

  8. heroku git:remote -a iotized-api-rest-usuario

  9. git add .

  10. git commit -m 'segundo_commit"

  11. git push heroku master

  12. Al finalizar el proceso obtengo el url completamente válido para ser usado https://iotrize-rest-server.herokuapp.com/ 

---------------------------------------------------------------------------

*** Proceso manual:

  Crear el proyecto desde la terminal:

  1. heroku create

  Nos proporciona un nombre por defecto al no haberlo especificado, aunque podríamos haberlo hecho.
  En este caso nos ha devuelto:

URL                                    
   > https://peaceful-headland-42142.herokuapp.com/ 

Nombre del repositorio 
   > https://git.heroku.com/peaceful-headland-42142.git



  2. git remote -v 

  C:\Projects\Node\REST_Server>git remote -v
  heroku  https://git.heroku.com/peaceful-headland-42142.git (fetch)
  heroku  https://git.heroku.com/peaceful-headland-42142.git (push)
  origin  https://github.com/dteso/REST_server.git (fetch)
  origin  https://github.com/dteso/REST_server.git (push)


  3. git push heroku master

  4. heroku open ----> Abre directamente la url en el navegador que nos acaba de crear al hacer el push a heroku

  5. En caso de errores ( El más habitual es no haber definido el start en los cripts del package json. En este caso: 
    "scripts": {
      "start": "node server/server.js",    <------------- ¡¡¡¡¡ IMPORTANTE !!!!
      "test": "echo \"Error: no test specified\" && exit 1"
    },
  )
    
    heroku logs --tail
/**********************************************************************************************/



> mLab  - Ofrece un sevicio gratuito para hasta 500Mb. Nos sirve para gestionar un servicio MongoDB en la nube.
          Actualmente se realiza a través de MongoDB Atlas



+ express - + express@4.17.1
+ bodyparser - > npm i body-parser --save
+ BCRYPT -> npm install @bcrypt@4.0.1 ----> Última versión a fecha 26_04_2020
+ draw.io ---> Para diagramas de clase
+ npm i mongoose ---> + mongoose@5.9.5
+ npm i underscore ---> 
+ npm i google-auth-library --save
+ npm i express-fileupload


-----------------------------------------------------------------------------------------------


> Variables de entorno Heroku

1. heroku config ---> Muestra las variables de entorno actuales

2. heroku config:set MONGO_URI="valor_de_la_ur_de_la_base_de_datos_remota_por_ejemplo" ---> Añade una variable de entorno 

3. heroku config:unset nombre ----> Elimina una variable de entorno con el nombre especificado

4. Sustituir en el código urlDB = process.env.MONGO_URI;