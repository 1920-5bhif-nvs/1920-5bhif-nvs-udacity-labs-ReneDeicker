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
### 1.24 Namespaces
Am Anfang der Applikation zeigen wir nun immer das Bild 1 an. Um dies zu ändern wird der Tools Namespace  benutze, um Dummy-Kontent zu erzeugen. Dieser wird nur in der Preview angezeigt aber später nach dem compilen nicht mehr.
### 1.25 Introduction to Gradle
Gradle ist das Buildtool für Android. Gradle ist verantwortlich für das Kompilieren, Dependency Management, automatisierte Tests usw. Gradle macht den Code zur ausführbaren App und erstellt dabei ein APK (Android Applikation Package) welches ein File ist um Android Applikationen zu installieren.
### 1.26 Build.gradle
Ein Repository in Gradle ist ein Server, wo externer Code heruntergeladen wird wie z.B. Libraries. Dependencies sind externer Code, auf dem die Applikation aufbaut. Gradle ist nicht nur für Android verantwortlich sondern wird auch in anderen Sprachen eingesetzt. Mit der ApplikationID identifiziert Android als auch GooglePlay die App.
### 1.27 Android Compatibility
Ein großer Vorteil von Android ist es, dass die Applikation auf sehr vielen Geräten verwendet werden kann (Tablets, Pixel-Books, Uhren, Fernseher, Autos etc.). Jedoch muss man einiges berücksichtigen, um diese Kompatibilität zu gewährleisten.
*   Minimum API Level: Definiert, welche Funktionalitäten das Gerät zur Verfügung stellt. Auf jedem Gerät, auf welchem eine niedrigere API-Version läuft, als in der App definiert ist, kann die App nicht installiert werden. In dem Code selber kann man auch überprüfen, welche API-version das Gerät verwendet und so Einzelheiten berücksichtigen.
### 1.28 Exercise: Vector Drawables
Der Vorteil von Vector-Grafiken ist, dass man soweit hineinzoomen kann, wie man will, ohne dass die Bilder an Qualität verlieren. Sie verden an API-Version 21 unterstützt. Hat das Gerät eine Version unter 19, so wird die Vektorgraphik von Gradle in ein png umgewandelt und dieses verwendet, welche aber klarerweise Speicherplatz benötigen. Durch den Befehl  `vectorDrawables.useSupportLibrary = true`, welchen man im build.gradle unter default contig im App Ordner einträgt werden diese png-Files nicht hinzugefügt. Außerdem verwendet man dann im Layout den Namespace `xmlns:app="http://schemas.android.com/apk/res-auto"`.
### 1.28 Recap
Zusammenfassung der Lesson.
## Lesson 2
### 2.1 Art with Aleks
Einleitung in das Thema Layout.
### 2.2 Introduction
Das Layout sollte dem Benutzer helfen, um die Funktionen der App klar zu machen. Das verbinden der Daten mit der View wird DataBinding genannt.
### 2.3 View Groups & View Hierarchy
Alle virtuellen Elemente der Android App sind Views. Diese haben einiges gemeinsam wie z.B. die einige Properties wie height und width. Beispiele für diese Views wären Textfelder, Imagefelder oder Buttons. Jede view hat eine Position auf dem Bildschirm. Die Unit um diese Position angeben zu können ist die Density Independent Pixel (dp). Android konvertiert automatisch den dp wert in einen Pixelwert, da dieser von der Bildschirmgröße abhängig ist. Das Layout sollte möglichst wenig verschachtelt werden, da dies mit schlechterer Performance bestraft wird.
* Linear Layout ist eine ViewGroup, wo man Views horizontal oder vertikal anordnen kann
* Mit der Scroll View kann man in der App scrollen. 
### 2.4 Exercise: Create the AboutMe Project
In dieser Sektion wird das Projekt erstellt. 
### 2.5 Exercise: Create the Layout File
In dieser Sektion erstellt man das Layout, welches zur MainActivity gehört. 
### 2.6 Layout Editor Basics
Wenn man in Android Studio das Layout xml File auswählt, kann man es auf 2 verschiedene Arten bearbeiten. Eine kombination zur Erstellung des Layouts der beiden Editoren ist empfehlenswert.
* Mit dem Design-Tab kann man die visuelle Präsentation der Oberfläche ansehen und bearbeiten
* Mit dem Text-Tab kann man den xml-Code der Oberfläche ansehen und bearbeiten
### 2.7 Adding a TextView
In dieser Sektion wird ein Textfeld auf die View hinzugefügt. Bei diesem stellt man einige Attribute wie Farbe, 
Alignment, Größe etc. ein. Außerdem ist es wichtig, dass man eine Stringressource hinzufügt, da man im dem string.xml File alle Strings speichert, die in der UI vorkommen. Das selbe wird mit der Schriftgröße gemacht, welche dann in res/values/dimens.xml gespeichert wird.
### 2.8 Styling a TextView
Für verschiedene Schrift argen kann man diese unter fontFamily auswählen welche dann in ein eigenes package unter res/font heruntergeladen werden. Margin als auch Padding werden wieder als Ressource angelegt. Den Style eines Textfields kann man nun exportieren und generell als Style in der App verwenden, indem man den Style exportiert. Dieser wird dann unter res/values/styles.xml gespeichert. 
* Margin: Platz rund um dem ELement
* Padding: Platz zwischen Außengrenze des Elements und dem Content
### 2.9 Exercise: Add a TextView, ImageView, and Styling
In dieser Übung fügt man ein ImageView zur UI hinzu. Android selbst bietet einige Bilder und Icons an, die man verwenden kann. Eine Contentdescription fügt man hinzu um das Bild kurz zu beschreiben.