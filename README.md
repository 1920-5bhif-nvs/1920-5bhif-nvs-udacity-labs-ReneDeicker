# 1920-5bhif-nvs-udacity-labs-ReneDeicker
1920-5bhif-nvs-udacity-labs-ReneDeicker created by GitHub Classroom
## Lesson 1
### 1.1 Welcome To Developing Android Apps
Android wird benutzt, um Apps auf Telefonen, Tablets, Uhren, Fernseher und Autos zu entwickeln und ist eine Programmiersprache.
### 1.2 Dice Roller
Installieren von Android Studio (eine Entwicklungsumgebung). Um die Apps auszuführen, braucht man entweder ein Telefon, Tablet etc. oder man benutzt ein virtuelles Gerät. 
### 1.3 Installing Android Studio
In dieser Lektion installiert man Android Studio.
### 1.4 Creating the Dice Roller Project: Written Instructions
Jetzt erstellt man ein neues Projekt. Als Sprache wählt man Kotlin und als minimum API level API 19.
### 1.5 Running Your First App
Um die App auszuführen, hat man die Optin ein physisches android Gerät zu verwenden oder ein virtuelles Gerät zu erstellen. Der Vorteil eines virtuellen Geräts ist vor allem, dass man mehrere Geräte mit verschiedenen Android Versionen testen kann, ohne diese tatsächlich kaufen zu müssen. 
### 1.6 Running your First App on an Emulator
Um die App auszuführen erstellen wir nun einen Emulator. Dafür öffnen wir den AVD Manager und erstellen ein neues Gerät. Wir erstellen ein Pixel 2 Phone und wählen als system image Pie, welches wir downloaden. 
### 1.7 Running your First App on a Device
Um die App auf einem physischem Gerät auszuführen, steckt man das android Gerät an den Computer über einen USB-Anschluss. Auf dem Gerät geht man nun in die Entwickleroptionen und aktiviert USB-Debugging. Geht man nun wieder in Android Studio, kann man das physische Gerät auswählen.
### 1.8 Student Interview: Part 1
In dieser Lektion findet man Interviews mit mehreren Personen über Android. Die Hauptaussagen der Interviews sind, dass man leicht in das Arbeiten mit Android einsteigen kann und viele Lösungen zu Problemen im Internet findet. Es ist aber ein sehr komplexes Framework, wo man wahrscheinlich nie auslernt.
### 1.9 Main App Anatomy
Um im Projekt zwischen verschiedenen Files zu navigieren, gibt es unter View/Tool-Windows das Projekt Fenster. Darin kann man verschiedene Optionen wie Projekt die die tatsächliche Ordnerstruktur anzeigen, oder Android, welches sinnvoll für die Entwicklung ist. Die Android App beinhaltet Kotlin Files, welche für die Logik der App verantwortlich sind. Es gibt auch eine ressource Ordner, indem Content, der sich nicht verändert wir Bilder oder Icons, gespeichert wird. Ein weiteres wichtiges File ist das AndroidManifest.xml File, indem Informationen für das Betriebssystem zum Ausführen der App gespeichert werden. Es gibt auch gradle scripts die für das Bauen der App verantwortlich sind.
### 1.10 Quiz: App Anatomy
Ein Quiz über die bis jetzt erhaltenen Informationen.
### 1.11 Activity and Layout
Eine Layout definiert, wie die App ausschaut und besteht aus xml Code. Eine Activity bestimmt, was die App macht und besteht aus Kotline Code. Verbunden sind Layout und Activity über den Prozess Layout Inflation.
### 1.12 Exercise: Hello Android
Im Layout werden die Elemente die von unserer App benutzt werden definiert. Mit verschiedenen Attributen kann man Eigenschaften wie Text setzen.
### 1.13 Adding the Button
Ein Linear Layout ist dafür verantwortlich, mehrere views in die Oberfläche zu platzieren und die Position besser angeben zu können. Dabei wird immer ein Element unter das andere gesetzt. 
Empfohlen wird außerdem alle Strings, die in der UI verwendet werden in das File strings.xml zu speichern, um sie später leichter verändern zu können.
### 1.14 Exercise: Adding the Button
Hier wird noch einmal Schritt für Schritt erklärt, wie man den Button hinzufügt.
### 1.15 Exercise: Connecting the Button
Der Kotline Code ist für den interaktiven Part der Applikation verantwortlich, sprich was z.B. passiert, wenn auf einen Button geklickt wird. Um Elemente der View ansprechen zu könne, vergibt man den Elementen eine ID. Diese werden in das R File gespeichert und mit `findViewById(R.id.roll_button)` kann man diese im Kotlin-code ansprechen.
### 1.16 Exercise: findViewById
*   Mit diesem Befehl kann man in dem Layout eine ID zu einem Element hinzufügen: `android:id="@+id/roll_button"`
*   In der Activity kann das Element per ID gefunden werden: `val rollButton: Button = findViewById(R.id.roll_button)`
*   In der Activity können Attribute des Elements verändert werden: `rollButton.text = "Let's Roll"`
### 1.17 Exercise: OnClickListener
In dieser Sektion lernt man, wie ein Toast erscheint, wenn ein Button gedrückt wird.
*   OnClick Listener hinzufügen: `rollButton.setOnClickListener {}`
*   Toast erscheinen lassen: `Toast.makeText(this, "button clicked", Toast.LENGTH_SHORT).show()`
### 1.18 Exercise: Change the Text
Random Zahlen können mit diesem Befehl erzeugt werden: `val randomInt = Random().nextInt(6) + 1`
### 1.19 Dice Images
Einführung in den nächsten Teil der Lektion, in der wir das Textfeld durch Bilder ersetzen werden.
### 1.20 Exercise: Adding the Image Resource
In dem Ressourcen Ordner (res) befinden sich alle Ressourcen (Icons, Bilder, Layout-Files, etc. ). In dem res Ordner befindet sich ein drawable Ordner, indem Bilder abgelegt werden.
### 1.21 Exercise: Adding the ImageView
Image Views werden verwendet, um Bilder in der UI anzuzeigen. Diese können wie alle Elemente wieder per ID gefunden werden und mit dem Befehl `diceImage.setImageResource(drawableResource)` kann das Bild geändert werden.
### 1.22 Student Interview: Part 2
In dieser Sektion wird wieder ein Interview mit Studenten geführt, die erklären wie es ihnen mit den ersten Schritten in Android ging. Es ging ihnen vorwiegend positiv aufgrund der guten Dokumentation von Android.
### 1.23 Exercise: Finding Views Efficiently
In dieser Sektion wird der Code optimiert
*   Die Methode `findViewById(R.id.dice_image)` ist sehr ressourcenintensiv und sollte deshalb so wenig wie möglich aufgerufen werden.    Deshalb legt man sich ein Feld mit dem jeweiligen Element in der Aktivity an: `lateinit var diceImage: ImageView`. Lateinit verspricht dabei dass das Feld vor der 1. Interaktion von dem Element initialisiert ist.
