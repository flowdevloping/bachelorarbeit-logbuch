# Zusammenfassung
- Problemlösungsschritte Elevation Mapping
- MOLA-LiDAR-Odometry-Framework Einrichtung und Test

## Details

### Problemlösungsschritte Elevation Mapping
Problem: Elevation Mappning läuft, aber erzeugt Daten voller "NaN"-Werte
- Einrichtung des Velodyne Plugins für Turtlebot3 Simulator
    - Erzeugung "echter" 3D-LiDAR Daten (trotzdem noch innerhalb Simulation) 
    -> Problem nicht gelöst 
- Überprüfung der Ros2 Nodes, Topics & Datentypen laut Dokumentation 
    -> Problem nicht gelöst
- Odometriedaten der Turtlebot Simulationsumgebung hatten große Unsicherheiten (Covariance)
    - Große Covariances bereinigt
        - Custom Node zum Publishen der bereinigten Odometriedaten erstellt
        -> Problem nicht gelöst

=> Bisher also noch keine Lösung hier gefunden 
-> Suche nach weiteren Möglichkeiten des 3D Mappings mittels Ros2 -> "MOLA" Framework gefunden

### MOLA-LiDAR-Odometry-Framework Einrichtung und Test
= Auf den ersten Blick ein gut dokumentiertes LiDAR Odometrie- & Mapping Framework für Ros2
- Einrichtung und Erstellung erster Karten war ohne Probleme möglich
- Output: 
    - .mm-Files -> 2D- & 3D-Maps erstellbar -> Steigungs- & Bodenbeschaffenheitsanalyse theoretisch machbar
    - .simplemap-Files -> Unterstütung mehrerer Kartenschichten -> weitere Option 

=> MOLA-Framework sieht auf den ersten Blick gut aus und ist gut dokumentiert
-> Demnächst weitere Tests -> Potentiell ein geeignetes Framework für unseren Anwendungsfall neben Elevation Mapping & Octomapping

## Nächste Schritte
- Elevation-Mapping Problem lösen 
- Weitere Tests mit MOLA-Framework
- Ocotmapping für Ros2 einrichten
(Da es für Elevation Mapping & Octomapping noch keine offizielle Unterstützung gibt, kommt es hierbei zu Problemen -> ggf. ist MOLA deshalb erstaml sinnvoller, wird
sich aber noch zeigen)
- Methoden zur Analyse unserer Bewertungsmetriken erarbeiten 
    -  Ansatz: 
        - Steigung: Voxelmap -> Gradienten der Höhenwerte nutzen -> Steigung = Höhenänderung[y]/Distanzänderung[x]
        - Bodenbeschaffenheit: Vermutlich eher Nutzung von RGBD-Kameras + Machine Learning & Computer Vision Methoden