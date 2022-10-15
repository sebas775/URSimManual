
# URSim Instalation Guide

    
## Installation


NOTA: La instalación del simulador URSim provocará la desinstalación de ROS, por ello
se recomienda realizar previamente los pasos de esta guía, para posteriormente instalar ROS.

Lo primero será **descargar** el simulador desde la página oficial:

<https://www.universal-robots.com/>

<p align="center">
<img src="https://github.com/sebas775/URSimManual/blob/main/Imaganes/image9.png" alt="Universal Robot e-Series family" style="width: 80%;"/>
</p>

![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image9.png)

![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image1.png)



Para ello, deberá desplazarse hasta el final de página donde encontrará el apartado

“**Training / Support**”, selecciona [**Technical**](https://www.universal-robots.com/support/)[** ](https://www.universal-robots.com/support/)[Support**](https://www.universal-robots.com/support/)[** ](https://www.universal-robots.com/support/)el cual le redirigirá a una nueva

página, donde se deberá seleccionar el botón **Download** ubicado en el banner superior.





Al dar click en el botón Download lo dirigirá a una nueva página, en dónde se visualizará

los filtros de búsqueda en el lateral izquierdo. Aquí debe desplegarse la opción

**“Software”** y marcar **“Linux Offline Simulator”**, de igual modo seleccionar el tipo de

robot con el que se va a trabajar como **e-series** o **CB-series**, para este ejemplo se

instalará para las versiones **e-serie**. Es claro que los pasos son los mismos

independientemente de la serie que vayas a utilizar. Para finalizar es necesario crear una

cuenta de usuario para descargar el simulador.

![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image8.png)

![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image13.png)

![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image25.png)






Una vez descargado el archivo se recomienda crear una carpeta en la ubicación **/home**

con el nombre **ursim** y pegar el archivo descargado ahí dentro.

![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image6.png)
![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image27.png)




NOTA: Antes de instalar el software se deberá verificar la versión del SDK con el siguiente

comando en una nueva terminal:

```bash
$ java -version
```


Si su versión es diferente a **openjdk version "1.8.0"** deberá sustituirla, para ello se

utilizan los siguientes comandos:


```bash
# Comando para instalar jdk v8
$ sudo apt install openjdk-8-jdk

# Comando para cambiar versión jdk
$ sudo update-alternatives --config java 
```
![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image15.png) ![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image4.png)


Una vez verificada la versión del SDK, acceder a la carpeta contenedora del simulador,

como se recomendó anteriormente /home/ursim, abrir una terminal y descomprimir el

archivo con los siguientes comandos.



```bash
$ tar xvzf URSim\_Linux-5.12.2.1101534.tar.gz
$ cd ursim-5.12.2.1101534
```



Nota: Si la versión del ubuntu esta en ingles omita la siguiente recomendación, de lo

contrario deberá dirigirse a la carpeta que descomprimió y en un editor de texto o block de

notas abra el archivo llamado **install.sh** y modifique la palabra Desktop por **Escritorio**,

como muestra la siguiente imagen.

![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image26.png)


Luego correr en la terminal el comando

```bash
$ sudo ./install.sh
```
![App Screenshot](https://github.com/sebas775/URSimManual/blob/main/Imaganes/image14.png)

Lo anterior permitirá observar en el escritorio los accesos directos que ejecutan el
simulador para cada versión, si los **íconos** mostrados son como se evidencia en la
siguiente imagen se debe ejecutar el siguiente comando.

```bash
$ sudo chown <user>/home/user/Escritorio/<nombre archivo>.desktop

```




Luego se debe seleccionar el acceso directo de la versión del robot que vaya a ejecutar y
darle permisos de confianza, así podrá visualizar el cambio del ícono y podrá ejecutar el simulador.





Antes de iniciar la aplicación se debe descargar el plugin [externalcontrol-1.0.5.urcap](https://github.com/UniversalRobots/Universal_Robots_ExternalControl_URCap/releases/download/v1.0.5/externalcontrol-1.0.5.urcap)[ ](https://github.com/UniversalRobots/Universal_Robots_ExternalControl_URCap/releases/download/v1.0.5/externalcontrol-1.0.5.urcap)y

pegarlo en la carpeta program.**versionRobot,** por ejemplo program.**UR3**





Ahora se podrá correr el simulador desde los íconos del escritorio. Si presenta el error

como muestra la imagen siguiente, sólo se deberá dar en el botón ok. Este error no afecta

la funcionalidad de la aplicación.

Para agregar el plugin ***external control*** que se descargó anteriormente, se deberá ingresar
en la configuración del simulador y realizar los pasos que se muestran en las siguientes

imágenes:









En este punto ya se puede realizar la instalación de ROS seleccionando la versión

compatible con el sistema operativo y siguiendo los pasos de la página oficial

<http://wiki.ros.org/es/ROS/Installation>.

NOTA: Si después de realizada la instalación de ROS y efectuar el comando

$ catkin\_make en la espacio de trabajo catkin\_ws, presenta problemas similares a

como se muestra en la imagen, utilizar los siguientes comandos:


```bash
$ sudo apt update -qq
$ rosdep update
$ rosdep install --from-paths src --ignore-src -y
```



Si el error persiste utilice el siguiente comando:


```bash
$ sudo apt install ros-melodic-PACKAGE
```
por ejemplo:

```bash
$ sudo apt install ros-melodic-**moveit-core**
```

Una vez instalado ROS se puede utilizar el simulador, para ello es necesario realizar la

configuración de la IP en el apartado de “Installation”, “URCaps”, “External Control” y

seguidamente activarlo en “Program”, “URCaps”, “External Control”.





Finalmente el programa ya está listo para usar, solamente debe darse en el botón de

Power off para encenderlo y ejecutar el controlador del robot desde una terminal.





## Usage/Examples

```javascript
import Component from 'my-project'

function App() {
  return <Component />
}
```

