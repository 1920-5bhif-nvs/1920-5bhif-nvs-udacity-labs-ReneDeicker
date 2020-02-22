# 1920-5bhif-nvs-udacity-labs-ReneDeicker
1920-5bhif-nvs-udacity-labs-ReneDeicker created by GitHub Classroom
Alle Informationen sowie Secreenshots sind von folgender Quelle erstellt worden:
https://classroom.udacity.com/courses/ud9012
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
### 2.10 Exercise: Add a ScrollView
Eine Scrollview wird dann verwendet, wenn der Inhalt, den man anzeigen möchte zu groß für das Display ist. Man vergibt auch hier eine ID, um beim Drehen des Handys die Scroll-position zu erhalten. 
### 2.11 Adding an EditText for Text Input
Um einen Textinput zu ermöglichen, muss man im Designtab unter Palette Text anklicken. Rechts daneben sind die verschiedenen Input Felder, die man auswählen kann. wenn das Ab unterstrichen ist, ist der Input editable. Bei gewissen Feldern sind sogar schon Validationen vorprogrammiert. 
### 2.12 Adding a Done Button to Accept Text Input
* Passt den Style an die App an: `style="@style/Widget.AppCompat.Button.Colored"`
* Zentriert den Button im Linear Layout `android:layout_gravity="center_horizontal"`

Bei einer Textview kann man die Visibilität auswählen
* visible: man sieht das Textfeld
* invisible: man sieht das Textfeld nicht, aber es braucht immer noch den gleichen Platz wie vorher
* gone: das Textfeld ist komplett verschwunden
### 2.13 Exercise: Add EditText, Done Button, ClickHandler
In dieser Lektion schreibt man den Code, welcher nach Klicken des Buttons  ausgeführt wird. In der OnCreate Methode muss man diese Methode als OnClickListener von dem Button registrieren.
```
findViewById<Button>(R.id.done_button).setOnClickListener {
    addNickname(it)
}
```
### 2.14 Data Binding
Das Zugreifen auf ein Element mit Hilfe von findViewById kann zu Performance Problemen führen. Alternativ dazu kann man mit Hilfe von Data Binding Binding Objekte zur Laufzeit erstellen lassen.
### 2.15 Data Binding: Views
Zu allererst muss man das DataBinding in build.gradle aktivieren
```
    dataBinding{
        enabled = true
    }
```
Dann fügt man rund um den geschriebenen xml Code in activity_main.xml ein Layout ein. Im Kotline File kann nun die Bindingvariable erstellt werden.
```
    private lateinit var binding: ActivityMainBinding
    binding = DataBindingUtil.setContentView(this, R.layout.activity_main)
```
Und auf Elemente über die Bindingvariable zugegriffen werden.
```
    binding.nicknameText.text = binding.nicknameEdit.text
    binding.nicknameEdit.visibility = View.GONE
    binding.doneButton.visibility = View.GONE
    binding.nicknameText.visibility = View.VISIBLE
```
### 2.16 Data Binding: Data
Bessere Performance ist eigentlich bei Databinding eine Nebensache. Viel wichtiger ist wie der Name schon sagt das Binden von Daten. Hierbei erstellen wir unsere eigene Klasse, wo sich die Daten befinden und speichern sie nicht mehr in Klassen wie strings.xml. Im activity_main.xlm File muss man nun einen Datenblock hinzufügen.
```
   <data>
        <variable
            name="myName"
            type="at.htl.aboutme.MyName" />
    </data>
```
Nun kann auf die Datenklasse zugegriffen werden
```
android:text="@={myName.name}"
```
### 2.17 Exercise: Implement Data Binding
Zusammenfassung der Umsetzung.
### 2.18 Google Interview: John Hoford and Nicolas Roard
Durchführung eines Interviews.
### 2.19 Constraint Layout: ColorMyViews App
Ein Constraint ist eine Verbindung oder eine Ausrichtung zu einem anderen UI - Element, zum Eltern Layout oder zu einer unsichtbaren RichtLinie.
### 2.20 Creating ColorMyViews Project
Erstellen eines neuen Projekts.
### 2.21 Exercise: Create ColorMyViews Project and One Box
Zu Beginn wird in dem neuen Projekt, im Layout File Autoconnect ausgeschaltet (Hufeisensymbol). Defaultmäßig kann man außerdem Margin einstellen im Design tab. So ist für jedes neue Element Margin bereits eingestellt. Anschließend modifiziert man die HelloWorldbox.
### 2.22 Constraints
In dieser Lektion wird etwas näher auf Constraints eingegangen. In der absoluten Position wird mit layout_margin gearbeitet, wobei relative Margins immer besser sind, weil sie responsive sind.
### 2.23 Ratios
In dieser Lektion werden Verhältnisse erklärt. Vorteil ist, dass man keine Höhen und Breiten hard codieren muss.
### 2.24 Chaining
Chaines verbinden horizontale oder vertikale Views. Dabei gibt es verschiedene Typen.
### 2.25 Adding Box Two Below Box One
Hinzufügen einer neuen Box und 2 Constraints sowie String-Ressources.
### 2.26 Adding Three Aligned Boxes
Hinzufügen 3 neuen Boxen sowie einige Constraints.
### 2.27 Exercise: Add Aligned Boxes with Click Handlers
Die Farbe nach clicken einer Box soll sich ändern. Dafür fügt man wieder für jeden Button einen OnClickListener hinzu.
### 2.28 Baseline Constraint
Hinzufügen von 2 textfeldern und deren Constraints.
### 2.29 Exercise: Add Baseline Constraint and Button Chain
Hinzufügen von 3 Buttons und deren Constraints. Per Click sollte die Farbe einer Box geändert werden.
### 2.30 Where to Go Next?
Ende der Lesson
## Lesson 3
### 3.1 The Guide and the Traveler
Einführung in das Thema Navigation.
### 3.2 Android Navigation Patterns
Vorstellung der App, die man in dieser Lesson programmieren wird.
### 3.3 Quiz: Navigation Terms
Quiz über die einzelnen Navigationskomponenten.
### 3.4 Fragments
Fragments wurden in dem API level 11 released, um eine flexiblere und dynamischere UI erstellen zu können. Eine Activity kann mehrere Fragments beinhalten. Zwischen den einzelnen Activities sowie Fragments kann man navigieren.
### 3.5 Quiz: Fragment Basics
Quiz
### 3.6 Exercise: Project Tour
Nähere Vorstellung des Projekts.
### 3.7 Exercise: Creating and Adding a Fragment
Erstellen eines Fragments sowie hinzufügen in dem main layout.
### 3.8 Navigation Component
Prinzipien der Navigation
* Es gibt immer einen Startupunkt, wo die App startet
* Man sollte immer zurück navigieren können
* Der Up-Button sollte immer da sein
### 3.9 Exercise: Let’s Navigate Already
In dieser Sektion wird ein Navigation Graph erstellt.
* Im res Ordner Navigation-File erstellen, um ein Fragment zu erstellen.
* In navigation.xml das Fragment mit dem Nav Host Fragment verbinden.
### 3.10 Principles of Navigation
Wiederholungen der Prinzipien der Navigation von 3.8.
### 3.11 Exercise: Conditional Navigation
Conditional Navigation ist eine Navigation abhängig von einer Bedingung (meist eine abhängige von dem User).
### 3.12 Exercise: Back Stack Manipulation
Wenn man nun den Zurück-Button des Handys betätigt kommt man wieder in das Spiel obwohl man eigentlich wieder auf dem Hauptscreen enden sollte. Deshalb fügt man eine "Pop Behaviour" bei der Navigation zu dem End-Screen ein und wählt das gewünschte Fragment aus.
### 3.13 Quiz: Back Stack Manipulation
Quiz
### 3.14 Exercise: Adding Support for the Up Button
Um nun nicht nur mit dem Handy-ZurückButton zurücknavigieren zu können fügt man den Up-Button hinzu.
Mit Strg. + O werden Methoden angezeigt, die man überschreiben kann.
### 3.15 Android Navigation - Up vs Back
Quiz
### 3.16 Google Interview: Ian Lake
Interview
### 3.17 Exercise: Adding a Menu
Hinzufügen des About Menüs. Durch das Hinzufügen der 3 oberen Punkte kann man auf diesen Button Drücken und zum About Menü navigieren. Dazu erstellt man im res Ordner ein eigenes Menu.
### 3.18 Quiz: Matching Menu Attributes
Quiz
### 3.19 Exercise: Adding Safe Arguments
Nun werden Argumente zwischen zwei Fragmenten übergeben. Safe Args ist ein Gradle Plugin. Dies wird benutzt, um zu vermeiden das es zu Bugs aufgrund von falschen Datentyp kommt
### 3.20 Why do we have Safe Arguments?
Quiz
### 3.21 Intents and Sharing
In diesem Video wird erklärt was Intenst und Sharing bedeutet. Durch Intents kann man von einer anderen App Ressourcen abfragen, wie zum Beispiel Kontakte oder auf die Kamera. Mit Hilfe von Sharing kann man z.B Texte in verschiedenen Apps teilen.
### 3.22 Quiz: Explicit vs Implicit Intents
Quiz
### 3.23 Exercise: Adding Sharing with an Intent
Umsetzen der Theorie in Praxis. Nach dieser Sektion kann man sein Ergebnis mit anderen teilen.
### 3.24 Exercise: Adding the Navigation Drawer
In dieser Sektion wird ein Navigation Drawer hinzugefügt, um besser navigieren zu können. Dieser kann durch swipen von links nach rechts oder klicken des drawer/hamburger icon in der Actionbar.
### 3.25 Summary of Navigation
Zusammenfassung über Navigation.
### 3.26 Quiz: How to Navigate
Quiz
### 3.27 Exercise: Using Navigation Listeners
Der "hamburger"-Button verschwindet nach wegnavigieren der Startseite, jedoch funktioniert das swipen von rechts nach links noch immer und der navigation drawer öffnet sich. Um dies zu verhindern muss man den navigation drawer sperren und wieder freigeben, jedes mal wenn auf eine andere Seite navigiert wird. 
### 3.28 Exercise: Animation with Navigation
In dieser Sektion werden Animations hinzugefügt. Man kann selbst welche erstellen und diese dann im navigation.xml File bei einem Navigationspfad eintragen.
### 3.29 Quiz: Animation Attributes
Quiz
## Lesson 4
### 4.1 The Case of the Missing Data
Einführung in das thema Lifecycles
### 4.2 Why Track Activity State?
Jede Activity und jedes Fragment hat ihren eigenen Lifecycle.
Der Lifecylcle hat verschiedene Stufen, welche für bessere Perfomance des Smartphones sorgen.
* initialized 
* created
* started 
* resumed 
* destroyed
### 4.3 Exercise: Introduction to the Activity Lifecycle Diagram
Die Lifecycles von Activities und Fragments sind sehr ähnlich.
Die jeweiligen Lifecycle Callback-Methoden werden immer dann aufgerufen wenn die Activity von einem Zustand in den nächsten bewegt.
![Diagram](/Images/LifecycleDiagram.png)
### 4.4 Exercise: Introduction to Logging
Erklärung der Lifecycle Methoden mit Hilfe der Android Logging API. Die Logs werden dann im Logcat Fenster angezeigt. 
 `Log.i("MainActivity", "onStart called")`
### 4.5 Exercise: The Application Class and Timber
Timber ist ebenfalls eine bekannte logging API.
* Timber in build.gradle eintragen: `implementation 'com.jakewharton.timber:timber:4.7.1'`
* Timber log Statement: `Timber.i("onStart called")`
### 4.6 Lifecycle: Open and Close
Erklärung der Reihenfolge der Callbackmethoden.
Quiz
### 4.7 Lifecycle: Share dialog
Beim Sharen wird die Callbackmethode onPause aufgerufen und bei Rückkehren in die App onResume.
OnStart wird aufgerufen, wenn die Activity sichtbar ist und onStop wenn sie nicht mehr sichtbar ist. 
![Diagram](/Images/LifecycleDiagramVisibleFocus.png)
### 4.8 onCreate vs onStart
Beim Verlassen und wieder Öffnen der App durch den rechten unteren Handy button onStart wird aufgerufen.
### 4.9 Activity Lifecycle States and Callbacks Summary
Zusammenfassung der Lifecyclemethoden.
### 4.10 Lifecycle: Navigate Away
Durch klicken des Homebuttons wird die Activity nicht zerstört sondern nur in den Hintergrund verschoben.
Quiz
### 4.11 Google Interview: Dianne Hackborn
Interview
### 4.12 Exercise: Setup and Teardown
Starten eines Timers, der nur zählen soll, wann das Spiel sichtbar ist 
-> Starten in onStart
-> Stoppen in onStop
### 4.13 Introduction to the Lifecycle Library
Einführung in das Thema Lifecycle Library.
### 4.14 Exercise: Lifecycle Observation
Implementation des Timers mit der Lifecycle Library. Der Timer kümmert sich nun selbst mit Hilfe des Observer Patterns um das Starten und Stoppen des Timers.
### 4.15 Process Shutdown
Das Betriebssystem teilt Apps in wichtig ein und unwichtig. Eine App die zuletzt vor 3 Tagen geöffnet wurde ist nicht so wichtig wie eine App die gerade im vordergrund läuft. Manchmal wird die App im Hintergrund sogar vom OS beendet. Diese wird aber später wirder meist automatisch vom OS geöffnet.
### 4.16 Process Shutdown Demo
Wenn das OS eine App beendet versucht es immer die Daten zu sichern. Manchmal gelingt dies jedoch nicht und man muss das gesicherte Bundle selbst annehmen über die Callbackmethode OnSaveInstanceState.
### 4.17 Exercise: onSaveInstanceState
OnSaveInstanceState ist eine Callbackmethode, die Hilfreich sein kann, um Daten wiederherzustellen, wenn das OS die Applikation beendet hat. Sie wird aufgerufen, nachdem die Activity gestoppt wurde (nach onStop). In dem Bundle befinden sich Key-Value Paare. Die Super-Methode sollte immer aufgerufen werden, da einige Daten automatisch gesichert werden können. Selbst kann man Variablen mit `outState.putInt("key_revenue", revenue)` speichern. Diese Daten können dann in den Methoden onRestoreInstanceState oder onCreate wiederhegestellt werden. onRestoreInstanceState wird nach onStart aufgerufen
```
if(savedInstanceState != null){
    revenue = savedInstanceState.getInt(KEY_REVENUE)
}
```
### 4.18 Configuration Changes
Beim Drehen des Telefons und somit der Activity, wird die Activity zerstört und wieder neu erstellt.
### 4.19 The Future of Lifecycles
Ende der Lifecycle Lesson.
## Lesson 5
### 5.1 Architecting on the Fly
Einführung in das Thema App Architecture.
### 5.2 Lesson Introduction
Einige Android Teams halten Standard Designregeln ein. 
In der Lifecycle Library gibt es noch andere Klassen wie ViewModel und LiveData.
### 5.3 Exercise: Tour of the App
Vorstellung der App
### 5.4 Where the App Falls Short
Nach Rotieren des Telefons verliert man das Wort sowie den aktuellen Punktestand.
### 5.5 What is Architecture
Diesen Bug könnte man wieder durch die Methode saveInstanceState lösen. Die dafür benötigten Bundles haben aber auch ihre Nachteile:
* Man muss extra Code für sie schreiben, um Daten zu speichern
* Sie haben begrenzten Speicherplatz, überschreitet man diesen wird eine Exception geworfen.

Für die Richtige Architektur gibt es keinen eindeutigen Weg. Es kommt immer darauf an welchen Zweck die App hat. In dieser Lesson wird das Pattern Model-View-ViewModel vorgestellt.
### 5.6 Our App Architecture
Seperation of Concerns: Aufteilen des Codes in Klassen - jede hat verschiedene definierte Verantwortungen.
* UI Controller - Anzeigen von Daten sowie Annehmen von Daten (UI-bezogene Dinge)
* View Model - Speichern und Vorbereiten der Daten die für die UI benötigt werden
* LiveData - Bringt die Daten vom ViewModel in den UI-Controller
### 5.7 ViewModel
Ein ViewModel ist eine abstrakte Klasse, welche die UI Daten sammelt. Diese Daten überleben Konfigurationsänderung wie z.B. das Drehen des Geräts. Es gibt außerdem keine Beschränkung des Speicherplatzes, wie bei onSaveInstanceState.
### 5.8 Exercise: Create the GameViewModel
Implementation eines ViewModels
* Hinzufügen in build.gradle der App: `implementation 'androidx.lifecycle:lifecycle-extensions:2.0.0' `
* Erstellen des ViewModels
* Instanzierung des ViewModels, sodass nur beim ersten Mal ein neues ViewModel instanziert wird: `viewModel = ViewModelProviders.of(this).get(GameViewModel::class.java)`
### 5.9 What Belongs in the GameViewModel?
Quiz
### 5.10 Exercise: Populate the GameViewModel
In dieser Sektion werden nun Variablen sowie Logikfunktionen in das ViewModel ausgelagert. Alles was jedoch mit Navigation zu tun hat bleibt im Fragment.
### 5.11 The Benefits of a Good Architecture
Vorteile des ViewModels
* Code ist organisierter
* Lifecycleprobleme und bugs treten nicht mehr auf 
* UI kann neu designed werden und das alte ViewModel kann immer noch verwendet werden.
* ViewModels sind leichter Testbar
### 5.12 The Power and Limits of the ViewModel
Durch das Implementieren eines ViewModels wurde das Problem mit dem Rotieren des Handys gelöst, jedoch sind auch neue Probleme entstanden und es wurde uneffiezienter. Die Daten sind außerdem noch immer verloren, wenn die App vom OS gekillt wird.
### 5.13 LiveData
Da man vom ViewModel nicht in den UI-Controller kommunizieren kann, gibt es LiveData. LiveData ist eine observalble Datenhaltungsklasse, welche Lebenszyklen überlebt.
### 5.14 Exercise: Add LiveData to GameViewModel
Ändern der Datenfelder auf observable
* Änderung des Datentyps: `var score = MutableLiveData<Int>()`
* Setzen eines DefaultValues: `score.value = 0`
* Anmelden der Observer: `viewModel.score.observe(this, Observer{newScore-> binding.scoreText.text = newScore.toString()})`
### 5.15 Lifecycle Awareness
LiveData weiß in welche Lifecycle Zustand seine UI-Controller Observer sind. So kann diese Information genutzt werden und intelligent mit den Fragments und Activities kommuniziert werden.
### 5.16 Exercise: Add LiveData Encapsulation to GameViewModel
### 5.17 Event vs. State
### 5.18 Exercise: Add End Game Event
### 5.19 Google Interview: Yigit Boyar
### 5.20 Adding a Timer
### 5.21 Exercise: Add CountDownTimer
### 5.22 Exercise: Add a ViewModelFactory
### 5.23 Exercise: Add ViewModel to Data Binding
### 5.24 Exercise: Add LiveData Data Binding
### 5.25 Exercise: LiveData Map Transformation
### 5.27 Recap of Architecture and Lifecycles

## Lesson 6
### 6.1 Architecting on the Fly
### 6.2 Introduction
### 6.3 SQLite Primer
### 6.4 Designing Entities
### 6.5 Exercise: Creating the SleepNight Entity
### 6.6 Data Access Object (DAO)
### 6.7 Exercise: DAO - SleepDatabaseDao
### 6.8 Creating a Room Database
### 6.9 Exercise: Creating a Room Database
### 6.10 Testing the Room Database
## 6.11 Displaying Sleep Data
## 6.12 Adding A ViewModel
## 6.13 Exercise: Adding a ViewModel
## 6.14 Multithreading and Coroutines
## 6.15 Exercise: Coroutines for Long-running Operations
## 6.16 Googler Interview: Florina Muntenescu
## 6.17 Navigation and Sleep Quality
## 6.18 Exercise: Recording Sleep Quality
## 6.19 Transformation Maps
## 6.20 Exercise: Button States and SnackBar
## 6.21 Where to go next?

## Lesson 7
### 7.1 Recycle Woman
### 7.2 Introduction
### 7.3 Your first RecyclerView
### 7.4 Exercise: Add a RecyclerView
### 7.5 Exercise: Display SleepQuality Data
### 7.6 Exercise: Recycling ViewHolders
### 7.7 Displaying Sleep Quality
### 7.8 Exercise: Display the SleepQuality List
### 7.9 Exercise: Refactor onBindViewHolder
### 7.10 Exercise: Refactor onCreateViewHolder
### 7.11 Improving Data Refresh
### 7.12 Exercise: Refresh Data with DiffUtil
### 7.13 Exercise: Add DataBinding to the Adapter
### 7.14 Exercise: Add Binding Adapters
### 7.15 Finishing Your First RecyclerView
### 7.16 Googler Interview: Romain Guy and Chet Haase
### 7.17 Using GridLayout
### 7.18 Exercise: Change LinearLayout to GridLayout
### 7.19 Interacting with List Items
### 7.20 Exercise: Implement a Click Listener
### 7.21 Exercise: Navigate on Click
### 7.22 Adding Headers to the RecyclerView
### 7.23 Extra Credit: Add a List Header
### 7.24 Headers in GridLayout
### 7.25 Extra Credit: Add a Header to the GridLayout
### 7.26 Summary

## Lesson 8
### 8.1 Greetings Earth Friends!
### 8.2 Introduction
### 8.3 RESTful Services
### 8.4 Libraries
### 8.5 App Walkthrough and Starter Code
### 8.6 Exercise: Connecting to the Internet
### 8.7 Permissions
### 8.8 Exercise: Parsing the JSON Response
### 8.9 Exercise: Coroutines and Deferred
### 8.10 Googler Interview: Jake Wharton
### 8.11 Exercise: Display an Internet Image
### 8.12 Exercise: Display Images in a Grid
### 8.13 Exercise: Error Handling with RecyclerView
### 8.14 Parcel and Parcelables
### 8.15 Exercise: Add the Detail Screen
### 8.16 Exercise: Add a Filter
### 8.17 Summary

## Lesson 9
### 9.1 Offline Movie Night
### 9.2 Exercise: Introduction
### 9.3 What’s in a Cache