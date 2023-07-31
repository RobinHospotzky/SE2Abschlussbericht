# Abschlussbericht Software Engineering 2

## Das Projektziel

Das Ziel unseres Projekts war die Erstellung eines online zugänglichen Veranstaltungskalenders auf kommunaler beziehungsweise regionaler Basis.  

Um dieses Ziel zu erreichen, suchten wir ein Projektteam bestehend aus drei Personen. Wichtig hierbei war, dass wir alle ein ähnliches Ziel hatten und so ein konstruktiver Austausch hinsichtlich der Erreichung des Ziels entstehen konnte.

Bestehend aus Lucia Eiffler, Jan Scheffelmeier und Robin Hospotzky einigte sich das Projektteam auf folgende Funktionen der Webanwendung:
- Die Möglichkeit zum Veröffentlichen von Veranstaltungen
- Das Editieren von Informationen zur Veranstaltung
- Das Erstellen einer Kommentarfunktion nach registrierter Anmeldung
- Das Erstellen einer Bewertungsfunktion für Veranstaltungen

Wir nutzten die empfohlenen Tools wie Trello und GitHub bei der Umsetzung des Ziels. In Trello erarbeiteten wir Arbeitspakete, welche wir den Teammitgliedern zuteilten.  
Zum Erleichtern der Kommunikation innerhalb des Projektteams erstellten wir in Microsoft Teams einen Chat. Dieser diente als primäre Austauschplattform bei Meetings.

## Meine Verantwortungen im Projektteam
### Verantwortungen im Bereich Projektmanagement

Meine Aufgabe im Bereich Projektmanagement war die stichpunktartige Dokumentation der einzelnen Meetings, um zuordnen zu können, was wann besprochen wurde und ein Überblick darüber besteht, wem welche Aufgabe zuzuordnen ist. Die Protokolle halfen uns Entscheidungen festzuhalten und einen Nachweis zu erschaffen, was in der Sitzung besprochen wurde.  

Mit Hilfe der Protokolle konnte jedes Teammitglied jederzeit nachschauen, welche Themen behandelt wurden ohne nachfragen zu müssen. Außerdem halfen die Protokolle, eine bessere Effizienz zu schaffen, da klar festgehalten wurde, wie lang das jeweilige Meeting dauerte.

Zur Erstellung der der Meeting Protokolle und zur Erstellung des Abschlussberichts arbeitete ich mich in Markdown ein und erlernte die wichtigsten Elemente der Auszeichnungssprache. Dabei hilfreich waren folgende Webseiten:

>[Digital Guide IONOS Markdown Anleitung](https://www.ionos.at/digitalguide/websites/web-entwicklung/markdown/)  
>[Markdown.de](https://markdown.de/)

Dabei lernte ich die Relevanz von Markdown im Bereich der IT-Projekte kennen. Denn mit Markdown lassen sich Protokolle und wichtige Notizen schnell und simpel notieren und gleichzeitig beispielsweise in einem GitHub Repository für alle einsehbar hochladen.

Zudem erstellte ich die PowerPoint Präsentation zur Milestone Meeting- und der Abschlusspräsentation, wobei sowohl Herr Scheffelmeier die Graphik unserer Front- und Backend Skizzierung erstellte und Frau Eiffler unseren Projektzeitplan in diese einbaute. Somit war eine effiziente und effektive Erstellung der Präsentation möglich, da jede Person die erstellten Unterlagen einbinden konnte.

### Verantwortungen im Bereich Technik

Im Bereich Technik hatte ich ebenfalls mehrere Aufgaben in dem Projekt. Dazu zählte das Skizzieren der Webseite.   
Dieser Schritt war einer der ersten, die wir in diesem Projekt angegangen sind. Denn durch die grobe Skizzierung der Webseite hatten alle die gleiche Vorstellung darüber, wie diese aussehen soll und es konnte ein HTML-Gerüst davon erstellt werden.   
Jedoch wurde die Webseite schlussendlich eine Abwandlung der ursprünglichen Skizzierung. Durch agiles Projektmanagement wurde eine veränderte Lösung während der Erstellung der Webseite erschaffen, die eine schönere Lösung darstellt. So wurde die obere Navigationsleiste der Skizze in der praktischen Umsetzung auf die rechte Seite gebracht, um ein zentrales Feld für die Veranstaltungen zu haben, welches sowohl links als auch rechts durch Navigationsleisten eingeschränkt ist.  
![Bild der Sizze](/SkizzeSE2.png)

Zu meinen Aufgaben gehörte auch das Erstellen der Navigationsleiste links und die Buttons dazu.  
Dazu frischte ich meine Kenntnisse in HTML und CSS im Bereich des Erstellens und Designens einer Navigationsleiste auf und designte diese.
```html
<!--Das Fenster, um eine neue Veranstaltung eintragen zu können wird geöffnet -->
<button onclick="dialogevent.showModal()" class="boxes-left">
    <div>
        <i class="fa fa-plus-square-o"> Neue Veranstaltung</i>
    </div>
</button>
```  
Dazu verlinkte ich verschiedene Icons von W3 Schools passend zum  jeweiligen Button.  
```html
    <!--Style für Icons von W3 Schools -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
```
Zusätzlich zum HTML- Part erstellte ich die Class _boxes-left_ in CSS, die das gewünschte Design der Buttons bestimmen.
```css
.boxes-left {
    min-width: 100%;
    margin: 15px;
    margin-left: 0px;
    padding: 5px;
    height: 10%;
    min-height: 80px;
    font-size: 20px;
    border-radius: 12px;
    border: none;
    text-align: left;
    cursor:pointer;
    position: relative;
}
```
Zudem erstellte ich ein Hover-Effekt für die Buttons um die Seite ansprechender Wirken zu lassen. Bei diesem Effekt bekommen die Buttons beim scrollen eine andere Hintergrundfarbe und einen anderen Schatten.
```css
.boxes-left:hover {
    background-color: rgb(252, 31, 31);
    box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24),0 17px 50px 0 rgba(0,0,0,0.19);
}
```
Zudem erstellte ich einen JavaScript-Code zur flexiblen Erstellung der Veranstaltungen im mittleren DIV-Container. Dafür erarbeitete ich mir wieder die Grundlagen von JavaScript. Damit konnte ich nun eine Funktion erstellen, welche nach Vorlage der Statischen Seite div Container erstellt, in denen die einzelnen Veranstaltungsparameter übergeben werden können. Dazu erstellte ich zuerst eine Funktion zum entfernen des davor da gewesenen Texts um Platz für den neuen Container zu erschaffen
```javascript
function destroy() {
     
     const myNode = document.getElementById("mittelContainer");
     while (myNode.firstChild) {
      myNode.removeChild(myNode.lastChild);
    }
}
```
Danach erstellte ich pro Veranstaltung einen weiteren Container in dem ein Bild übergeben wird, welches in den Container der Veranstaltung hineingegeben wird
```javascript
 var image = document.createElement("img");
    image.src = {{%hochgeldaenesBild%}};
    image.alt = "Bild";
    image.style.maxWidth = 100%;

    bildContainer.appendChild(image);
    divContainer.appendChild(bildContainer);
```
und mehrere Informationen, wie der Veranstalter oder der Name der Veranstaltung werden übergeben.
```javascript
var veranstalterauswahl = dokument.createElement("h4");
    veranstalterauswahl.innerText = {{% veranstalter %}};
    inhaltContainer.appendChild(veranstalterauswahl);
```
Leider hat es uns zeitlich nicht mehr gereicht, das JavaScript- Programm mit dem Server zu verbinden.  
Gemeinsam mit den anderen Teammitgliedern entwickelten wir am 06.07.2023 ein Programm zur Erstellung einzelner Kommentarspalten für die jeweiligen Veranstaltungen auf der statischen Seite. Dabei erarbeiteten wir gemeinsam eine Lösung, um die einzelnen Kommentare in jeweils einer eigenen Textdatei zu speichern und diese an der zugehörigen Veranstaltung anzuzeigen.  

## Zusammenarbeit im Team

Die Zusammenarbeit innerhalb des Teams hat sehr gut funktioniert. Durch eine hohe Zuverlässigkeit der Teammitglieder konnte ein großes Vertrauen innerhalb des Teams geschaffen werden.   
Die Meetings waren stets produktiv, die Mitglieder waren zu vereinbarten Terminen immer anwesend und trugen konstruktiv zur Problemlösung bei.  
Zudem war eine hohe Arbeitsbereitschaft vorhanden. So wurden Meetings erst dann abgeschlossen, wenn alle Fragen geklärt und die aufgetretenen Probleme gelöst wurden. Dies dauerte manchmal auch bis spät abends. 

Zudem war es hilfreich, dass alle Teammitglieder sich über das gemeinsam beschlossene Ziel einig waren und somit eine hohe Grundmotivation vorhanden war. Diese wurde allerdings ein wenig geschmälert durch die zeitweise Frustration, als das Projekt stagnierte, da das Knowhow zur Verbindung von Frontend und Backend noch nicht erlernt worden war.

Außerdem ist die gute Kommunikation innerhalb des Teams erwähnenswert. Da neben den offiziellen Meetings auch viel in den Vorlesungspausen besprochen wurde und kleinere Dinge schnell von Person zu Person besprochen werden konnten. 

## Was ich das nächste Mal anders machen würde

Eines unserer Hauptprobleme bei der Durchführung und Umsetzung unseres Projekts war die Ungewissheit, welche Bestandteile des Projekts wir wann umsetzen können, da uns das Knowhow fehlte, was realistisch ist und wann wir dies mit unserem Wissen umsetzen können. Deshalb ist es für die nächsten Projekte wichtig uns frühzeitig zu informieren, welche Ziele realistisch sind und wann wir diese erreichen können.

Dabei kann ein Lösungsansatz sein, die Ziele niedriger zu setzen und danach lieber zu erweitern, anstatt priorisieren zu müssen, welche Teilziele gestrichen werden müssen.   
Zudem können Prototypen helfen erst kleine Teile des Projekts umzusetzen und danach die anderen Dinge zu immigrieren.   

Wichtig ist eine bessere Projektplanung in Hinsicht auf Risikomanagement und Lösungsansätze und wie wir diesen Risiken zuvorkommen können. Zusätzlich ist mit einem Wissen, welche Ziele in einem gewissen Zeitraum möglich sind zu erreichen, eine bessere und strukturierte Zeitplanung für das Projekt möglich.   
Daily Meetings sind ein wichtiger Bestandteil und sollten beim nächsten Mal konsequenter umgesetzt werden. Jedoch war durch den eher schleppenden Fortschritt zeitweise die Notwendigkeit von Daily Meetings eher eingeschränkt, da durch die Vorlesungen Kontakt zwischen den Teilnehmenden gegeben war und deswegen zusätzliche Meetings teilweise unnötig waren.

Zudem wäre einer der ersten Schritte das nächste Mal das Einrichten eines Servers, auf dem alle Arbeiten können und Zugriff haben. Somit können Änderungen direkt umgesetzt werden, ohne erst eine andere Person zum Hochladen der aktuellen Version bringen zu müssen. 

Zudem war am Anfang das Problem, dass mehrere Personen gleichzeitig an einer Datei arbeiteten. Da die Versionen nicht synchronisiert waren und somit eine Person an einer veralteten Version der Datei arbeitete kamen Probleme auf. Dies kann jedoch durch Regelmäßigen synchronisieren der Datei behoben werden.

<br>
<br>

>Abschließend kann ich sagen, dass das Projekt, obwohl es nicht fertig geworden ist, eine gute Erfahrung war. Das Projektteam war sehr gut und mit vorherigem Wissen, was in welcher Zeit möglich ist, ist ein erfolgreicherer Projektausgang gut möglich.