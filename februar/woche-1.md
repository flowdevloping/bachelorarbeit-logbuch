# Zusammenfassung

## Visualisierung der Ouster-Daten in Rviz und rtabmap

- Experimentieren mit eigenen ROS2-Nodes zur Verarbeitung der Ouster-Daten
- Erste Tests mit Octomap (da Elevation Mapping in ROS2 nicht direkt verfügbar ist)

## Details

### Verarbeitung der Ouster-Daten

- Nutzung des ouster-sdk, um aus Ouster-Rosbag-Daten (.pcap-Files) Punktwolkendaten (.pcd/.ply-Files) zu generieren

### Implementierung eigener ROS2-Nodes:

- Publishing der Punktwolken an entsprechende Topics
- rtabmap subscribed auf diese Topics und verarbeitet die Daten
- Durchführung von SLAM mit rtabmap zur Erstellung von 3D-Karten

### Untersuchung von Mapping-Ansätzen

- Recherche zu Elevation Mapping ergab, dass es eher keine kompatible Version mit ROS2 gibt
- Deshalb erste Tests mit Octomap als Alternative:
  - Ziel: Evaluierung der Eignung von Octomap für Boden- und Steigungsanalysen
- Überlegung: Möglichen Nutzung von ROS1, falls sich Elevation Mapping als vorteilhafter erweisen sollte

## Nächste Schritte

- Weiterführende Tests mit Octomap zur Bewertung für Boden- und Steigungsanalyse
- Recherche zu Möglichkeiten, Elevation Mapping für ROS2 zu implementieren
- Falls sinnvoll: Setup mit ROS1 zur Nutzung von Elevation Mapping
