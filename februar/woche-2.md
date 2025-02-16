# Zusammenfassung
- Testen des ouster-sdk & rtabmap 
- Einrichtung Octomap & Elevation Mapping

## Details

### Testen des ouster-sdk & rtabmap
- Erstellung von Karten aus den .pcd/.ply Files in rtabmap 
- Visualisierung mit rtabmap & rviz
- Test Octomap Implementierungen innerhalb von rtabmap, bisher ohne Erfolg

### Einrichtung Octomap & Elevation Mapping
→ Einrichtung Octomap:
- Probleme mit Parametern
    - frame_id, topics, …
    → Zeit für das Verstehen von Ros Launch-Files investiert
    
→ Einrichtung von Elevation Mapping:
- Probleme mit der Einrichtung für ros2, da bisherige Implementierungen auf ros1 ausgelegt sind
→ Portierung auf ros2, aber ebenfalls noch Probleme mit Parametern

⇒ Octomap & Elevation Mapping installiert und eingerichtet, jedoch noch nicht vollständig funktionsfähig

→ Erstmal Zeit in das Verstehen der Implementierungen der jeweiligen Ros Module investiert
- Config- & Launch-Files usw. durchgegangen und getestet
- Dokumentation gelesen

Ergebnis: Pcd Daten werden gepublished und von den jeweiligen Modulen subscribed, aber es werden noch fehlerhafte Maps erzeugt

## Nächste Schritte
- Fehlerfreie Maps erzeugen
- Recherche der Möglichkeiten der Analyse unserer Metrics
