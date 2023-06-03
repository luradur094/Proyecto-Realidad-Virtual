# Creacion de escenario virtual
Lo primero que haremos para empezar con el entorno virtual sera crear las esferas:
1. Click delecho en la parte latelar ---> 3D Object ---> Sphere

![..](https://github.com/luradur094/Proyecto-Realidad-Virtual/blob/main/Imagen/captura%201.png)

2. Una vez creada ajustaremos la escala a 10 x 10 x 10

![..](https://github.com/luradur094/Proyecto-Realidad-Virtual/blob/main/Imagen/captura%202.png)

3. Ya creada la esfera pasaremos la imagen que queremos usar y le haremos los siguientes cambios: en texture Shape le pondremos cube y en mapping le pondremos Latitude-Longitude Layout (Cylindrical) y le damos a aplicar

![..](https://github.com/luradur094/Proyecto-Realidad-Virtual/blob/main/Imagen/captura%203.png)

4. Ahora crearemos un material nuevo y lo modificaremos para meter la imagen dentro 

![..](https://github.com/luradur094/Proyecto-Realidad-Virtual/blob/main/Imagen/captura%204.png)

![..](https://github.com/luradur094/Proyecto-Realidad-Virtual/blob/main/Imagen/captura%205.png)


5. ya echo eso le damos a la esfera que creamos anteriormente y en la parte de material element 0 le damos y elegimos la imagen que creamos en el paso 4 

![..](https://github.com/luradur094/Proyecto-Realidad-Virtual/blob/main/Imagen/captura%206.png)

6. Y por ultimo a nuestra camara tiene que estar en el centro de la esfera mas o menos si no no saldra bien en donde pone clear flags elegimos solid color para que aparezca la imagen de la esfera al estar dentro de ella 

![..](https://github.com/luradur094/Proyecto-Realidad-Virtual/blob/main/Imagen/captura%207.png)

7. Volvemos a repetir los mismos pasos para tener dops esferas o las que queramos que tenga ya echo lo que hacemos sera crear un script en create C# script

![..](https://github.com/luradur094/Proyecto-Realidad-Virtual/blob/main/Imagen/captura%207.png)

8. El primer script es para el movimiento de la camara para moverte dentro de ella y ver la imagen y el segunco script es para cambiar entre las esferas que hemos creado 

![MoverCamara]()

![CambiarCamara]()