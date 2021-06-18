# Auto_Tractor

## Gazebo e Rviz
Per avviare la simulazione:
> roslaunch auto_tractor innok_heros_gazebo.launch

> roslaunch auto_tractor innok_heros_rviz.launch

## Controllo
Per controllare il trattore da tastiera:
> roslaunch auto_tractor teleop.launch

Per muoverlo:  

     u    i    o
   
     j    k    l
   
     m    ,    .

q/z : aumenta/diminuisce velocità massima del 10%

w/x : aumenta/diminuisce velocità lineare del 10%

e/c : aumenta/diminuisce velocità angolare del 10%  

cliccando su altri tasti si ferma

## Topic
Per visualizzare le velocità del trattore su terminale
> rostopic echo /cmd_vel

## Camera e Depth_Camera
Per visionare l'immagine della camera (posteriore) e della depth_camera (anteriore) su Gazebo:
> rosrun image_view image_view image:=/camera/image_raw

> rosrun image_view image_view image:=/depth_camera/color/image_raw

> rosrun image_view image_view image:=/depth_camera/depth/image_raw

## Mappa 2D
- Avviare Gazebo e Rviz (su due schede separate del terminale)
- Su un'altra scheda utilizzare il seguente comando:
> roslaunch auto_tractor slam_gmapping.launch
- Su Rviz aggiungere i topic rigurdanti depth_camera, laser e Map
- Avviare il file teleop.launch per far muovere il trattore. Esplorato tutto l'ambiente la mappa è completa
- Per salvare la mappa nella cartella desiderata: 
> rosrun map_server map_saver -f mymap2d






