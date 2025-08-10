# Technikerarbeit-DGUV-V3-mit-Solana-Anbindung
Ziel dieses Projekts ist die Entwicklung eines prototypischen DGUV-Messsystems auf Basis eines Raspberry Pi, das eine fälschungssichere, benutzerfreundliche und datenschutzkonforme Erfassung sowie Archivierung von Prüfdaten ermöglicht. Die zentrale Anforderung besteht in der unveränderlichen Speicherung aller Messergebnisse auf der Solana-Blockchain, wodurch eine nachträgliche Manipulation ausgeschlossen wird und die Prüfdaten langfristig nachvollziehbar bleiben.
Die Bedienung erfolgt über eine grafische Benutzeroberfläche, die lokal auf dem Raspberry Pi läuft und sowohl die strukturierte Erstellung der Prüfumgebung als auch die Durchführung und Protokollierung der Messungen unterstützt. 
Nach Abschluss der Messungen wird ein PDF-Protokoll generiert, das die relevanten Prüfdaten enthält und anschließend verschlüsselt über ArDrive gespeichert wird. Der Zugriff auf diese Protokolle ist ausschließlich autorisierten Nutzern vorbehalten. 
Die Software wird modular aufgebaut, um perspektivisch Funktionen wie den Import von EPLAN-Strukturen in der Zukunft zu ermöglichen

# Status der Software

## 🗓 Update – 10.08.2025

Heute habe ich die beiden Tabs **Login** und **Registrierung** fertiggestellt.  
Diese erscheinen immer zuerst nach dem Start der Software.  
- **Login:** Benutzer meldet sich mit **Benutzername**, **Passwort** und **Key-Datei** vom USB-Stick an.  
  Das Passwort wird mit **bcrypt** validiert, anschließend wird die Wallet mit **AES-256** entschlüsselt.  
- **Registrierung:** Erstellt einen neuen Account mit Benutzername/Passwort und generiert dabei eine echte **Solana-Wallet** via CLI.  
  Die privaten Schlüssel werden AES-verschlüsselt in der Datei `user.json` auf dem Stick gespeichert.  

Damit ist es möglich, nach erfolgreichem Login Transaktionen auf der automatisch erzeugten Prüfer-Wallet durchzuführen.  
Die Wallet-Erstellung erfolgt plattformübergreifend (Raspberry Pi & Windows/WSL).

![Login und Registrierung Demo](gifs/Sperrbildschirm1.gif)


