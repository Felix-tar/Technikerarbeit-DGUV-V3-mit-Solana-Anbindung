#  Technikerarbeit: DGUV-V3-Messgerät mit Solana-Anbindung

Ziel dieses Projekts ist die Entwicklung eines prototypischen DGUV-Messsystems auf Basis eines Raspberry Pi, das eine fälschungssichere, benutzerfreundliche und datenschutzkonforme Erfassung sowie Archivierung von Prüfdaten ermöglicht.  
Die zentrale Anforderung besteht in der unveränderlichen Speicherung aller Messergebnisse auf der Solana-Blockchain, wodurch eine nachträgliche Manipulation ausgeschlossen wird und die Prüfdaten langfristig nachvollziehbar bleiben.
Die Bedienung erfolgt über eine grafische Benutzeroberfläche, die lokal auf dem Raspberry Pi läuft und sowohl die strukturierte Erstellung der Prüfumgebung als auch die Durchführung und Protokollierung der Messungen unterstützt.  
Nach Abschluss der Messungen wird ein PDF-Protokoll generiert, das die relevanten Prüfdaten enthält und anschließend verschlüsselt über ArDrive gespeichert wird. Der Zugriff auf diese Protokolle ist ausschließlich autorisierten Nutzern vorbehalten.  


---


##  Status & Updates

### Nächstes update: **aktivitätsanzeige bei wallet erstellung hinzufügen & Struktureditor debuggen**


### Update – 16.08.2025
Zur besseren Bedienung und Benutzerfreundlichkeit habe ich ein Fenster hinzugefügt, das den Status des Generierungsprozesses in Form eines Fortschrittsbalkens anzeigt. Darin werden die einzelnen Schritte – Beginn der Generierung, Solana-Wallet-Generierung, Solana-Wallet erstellt, Beginn der Arweave-Wallet-Generierung und Arweave-Wallet erstellt – dargestellt, um dem Benutzer zu verdeutlichen, dass der Prozess bereits läuft und er bitte warten soll.

![status bar](gifs/Sperrbildschirm%mit%statusanzeige.gif)

### Update – 11.08.2025
Die ArWeave-Privatekeys werden nun ebenfalls in der `.user.json` gespeichert und mit dem Benutzernamen sowie Passwort vertschlüsselt. Da die ArWeave-CLI die Eingabe selbstgewählter BIP-32-Seedphrasen erfordert, habe ich eine Zufallsgenerierung eingebaut, die die Seeds erstellt. Die Seeds sind dabei unwichtig, da sie ohnehin verschlüsselt auf dem USB-Stick gespeichert werden und daher nicht separat aufgeschrieben werden müssen.

![User Jason](gifs/user%20jason%20V2.png)



### Update – 10.08.2025

Heute habe ich die beiden Tabs **Login** und **Registrierung** fertiggestellt.  
Diese erscheinen nach dem Start der Software.  

- **Login:** Benutzer meldet sich mit **Benutzername**, **Passwort** und **Key-Datei** vom USB-Stick an.  
  Das Passwort wird mit **bcrypt** validiert, anschließend wird die Wallet mit **AES-256** entschlüsselt.  
- **Registrierung:** Erstellt einen neuen Account mit Benutzername/Passwort und generiert dabei eine echte **Solana-Wallet** via CLI.  
  Die privaten Schlüssel werden AES-verschlüsselt in der Datei `.user.json` auf dem Stick gespeichert.  

Damit ist es möglich, nach erfolgreichem Login Transaktionen auf der automatisch erzeugten Prüfer-Wallet durchzuführen.  
Die Wallet-Erstellung erfolgt plattformübergreifend (Raspberry Pi & Windows/WSL).

![Login und Registrierung Demo](gifs/Sperrbildschirm.gif)



---

##  Installation 


---



