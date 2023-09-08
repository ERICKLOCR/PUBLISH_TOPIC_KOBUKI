# PUBLISH_TOPIC_KOBUKI







#  Instalación del Turtlebot2 en ROS melodic(Ubuntu 18.04)

## Instalaciones adicionales


```
mkdir -p ~/turtlebot2_ws/src
cd turtlebot2_ws
catkin_make
cd src
curl -sLf https://raw.githubusercontent.com/gaunthan/Turtlebot2-On-Melodic/master/install_all.sh | bash
cd ..
catkin_make

```


#  Instalación del Turtlebot3 en ROS melodic(Ubuntu 18.04)




Creamos nuestro workspace de trabajo 
```
mkdir -p ~/turtlebot3_ws/src
cd turtlebot3_ws
catkin_make
```
Nos ubicamos en la carpeta para clonar el repositorio

```
cd src
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
```


# Instalar SLAM
```
sudo apt install ros-melodic-slam-gmapping

```


#                 Para abrir el entorno virtual de simulación del Turtlebot3 en Gazebo


##  Ejecutar Turtlebot en Gazebo

Nos ubicamos en la cartepara de trabajo

```
cd turtlebot3_ws
```

Se puede elejir el model de robot a acargar ene l simulador eentre ellos se tiene model-> burger, waffle, waffle_pi

Ahora para abrir tu espacio de tranajo en el semilador Gaseo podemos tener difeentes entornos entre ellos tenemos

1. Lanza un espacio de trabajo turtlebot uncamente en un plano
 ```
export TURTLEBOT3_MODEL=burger
  roslaunch turtlebot3_gazebo turtlebot3_empty_world.launch     
```
2. Lanza un espacio de trabajo turtlebot uncamente en un plano
```
export TURTLEBOT3_MODEL=burger
 roslaunch turtlebot3_gazebo turtlebot3_world.launch           
```

3. Lanza un espacio de trabajo turtlebot mostrando el interior de una casa

```
 export TURTLEBOT3_MODEL=burger
 roslaunch turtlebot3_gazebo turtlebot3_house.launch         
```

##                Control del Turtlebot3 
###  Se controlará al Turtlebot3 mediante teclado
```
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```




##                 Mapeo el mundo


### Para visualizar el mapeo en RViz

Ejecutar en una nueva terminal 
```
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
Se mostrara una nueva ventana de RViz la cual mostrará el mapeo que el robot realizara mientras este, avanzá por el mundo.











## PRUEB DE IMAG

![SOC top](docs/doxygen/pics/soc_top_v5.png)


## PRUEB DE DOC

SoC documentation in [.pdf](docs/riscv_vhdl_trm.pdf) formats.



## -Comandos en nueva terminal  – Joystick node-

 /dev/input/jsX “X:0,1,2” colocar el número de puerto:
```
 rosparam set joy_node/dev "/dev/input/js0"
 rosrun joy joy_node                        
```

  Se levanta el nodo joy
 
## -Comandos en nueva terminal – Teleoperación con joystick-


- Dirigirse al  repositorio de AutoMini en simulación  mediante el Joystick el cual se  clonó previamente:

```
  source devel/setup.bash
  cd src/principal/src 
  rosrun principal joyop.py
```

