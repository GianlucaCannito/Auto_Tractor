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
- Su un'altra scheda utilizzare il seguente comando per introdurre l'algoritmo slam gmapping:

  > roslaunch auto_tractor slam_gmapping.launch
- Su Rviz aggiungere i topic rigurdanti depth_camera, laser e Map
- Avviare il file teleop.launch per far muovere il trattore. Esplorato tutto l'ambiente la mappa è completa
- Per salvare la mappa nella cartella desiderata: 
  > rosrun map_server map_saver -f mymap2d
- Per ricaricare la mappa su Rviz utilizzare il comando: 
  > roslaunch auto_tractor map.launch

## Mappa 3D
- Avviare Gazebo e Rviz
- Avviare il pacchetto Octomap:

  > roslaunch auto_tractor octomap.launch
- Su RViz si aggiunge il MarkerArray con il topic occupied_cells_vis_array
- Avviare il file teleop.launch per far muovere il trattore. Esplorato tutto l'ambiente la mappa è completa
- Salvare la mappa appena realizzata nella cartella di interesse:
  > rosrun octomap_server octomap_saver -f map3d.bt
- Per ricaricare la mappa su RViz si utilizza il comando (inserendo Map nel fixed frame):
  > rosrun octomap_server octomap_server_node map3d.bt

## Pacchetti ROS 
