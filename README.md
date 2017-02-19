<h1 style="color:red;">The Evolution</h1>
<p>
<i>ein Projekt von Leif Peters und Linus Reck</i>
</p>
<p>Das vorliegende Programm wurde mit Hilfe "<mark>Greenfoot's</mark>" geschrieben. Beim Bearbeiten orientierten wir uns an den Stride-Angaben und dem Greenfoot-Buch.</p>
<h2>Inhaltsverzeichnis</h2>
<ul>
<li><a href="#anf">Anfänge</a></li>
<li><a href="#sdp">Sinn des Programms</a></li>
<li><a href="#ads">Ablauf des Spiels</a></li>
<li><a href="#adp">Ablauf der Programmierung</a></li>
<ul>
<li><a href="#era">Erste Actor</a></li>
<li><a href="#nah">Nahrungskette</a></li>
<li><a href="#zas">Zuschauer als Spieler</a></li>
<li><a href="#mus">Musik</a></li>
<li><a href="#for">Fortpflanzung</a></li>
<li><a href="#evh">Einführung von Hunger</a></li>
<li><a href="#sch">Die Schlange</a></li>
<li><a href="#zom">Zombiekrabben</a></li>
<li><a href="#gao">Game Over</a></li>
<li><a href="#sco">Der Score</a></li>
</ul>
<li><a href="#pfz">PLäne für die Zukunft</a></li>
</ul>
<h2 style="color:green;" id="anf">
Anfänge
</h2>
<p>Unsere eigentliche Idee war es, mit einem RaspberryPi zu arbeiten. In den ersten Stunden probierten wir dies aus und installierten ein neues Betriebssystem auf einem dieser Computer. Da wir uns diese Arbeit allerdings anders vorgestellt hatten, hörten wir recht schnell mit diesem Projekt auf und ließen uns eine neue Idee einfallen. Unser Ziel war (und ist) es ein Doppelkopfspiel mit Greenfoot zu programmieren. Dafür müssten wir uns aber erstmal mit dem Programm und Programmierung allgemein auseinandersetzen. Wir begannen mit den Greenfoot-Stride Lernaktivitäten. Später haben wir auf Grundlage dieser, eigene Ideen in die Welt gebracht, woraus nach einer Zeit ein Spiel entstanden ist.</p>
<h2 style="color:darkorchid;" id="sdp">
Sinn des Programms
</h2>
<p>Dieses Programm dient der Einarbeitung in das Programm "Greenfoot", weswegen es sowohl Elemente eines Spiels der aktiven Steuerung eines "Actors", als auch Elemente eines sich selbst entwickelnden Programms (evolutionssimulierende Ansätze) enthält. So mag es einem Betrachter erscheinen, als könne man einige Befehlsketten anders ausdrücken.</p>
<h2 style="color:royalblue;" id="ads">
Ablauf des Spiels
</h2>
<p>In diesem Spiel steuert man mit den Pfeiltasten einen Wurm. Mit der rechten und linken Pfeiltaste dreht sich der Wurm, mit der oberen und unteren Taste bewegt sich der Wurm vorwärts und rückwärts. In der Spielwelt gibt es noch drei weitere Spielklassen, die vom Computer gesteuert werden. Die Krabben, die Hummer und die Seesterne sind die anderen Klassen in diesem Spiel. Sie fressen sich gegenseitig und vermehren sich, wenn sie jemanden gefressen haben. Wenn sie zu lange nichts fressen, verhungern sie. Der Wurm hat die Fähigkeit, jedes andere Tier zu fressen und kann von keinem anderen Tier getötet werden. Er verhungert aber auch, wenn er zu lange nichts gegessen hat. Wenn der Wurm eine Krabbe frisst, erscheint diese nach einer Zeit als Zombiekrabbe am Todesort wieder. Zombiekrabben sind doppelt so schnell, wie normale Krabben und stecken diese bei Berührung an. Treffen sie auf Hummer oder Seesterne, sterben beide Tiere. Ziel des Spiels ist es, so lange wie möglich mit dem Wurm zu überleben.</p>
<img src="aufstellung.png" alt="aufstellung">
<h2 style="color:indianred;" id="adp">
Ablauf der Programmierung
</h2>
<h3 style="color:darkturquoise;" id="era">
Erste Actor
</h3>
<p>Als Grundlage verwenden wir die "Crab-World" Vorlage. Wir haben damit angefangen, dass wir eine einfache Crab.class in die World eingefügt haben. Durch den Befehl "move (5)" bewegt sich diese <a href="#cr1">Crab.class</a> geradeaus. Da die World begrenzt ist, veränderten wir die Bewegungsrichtung beim Auftreffen auf die Wand (Äußeres Ende der Welt). Die Richtung sollte nicht konkret vorgegeben sein, sondern immer zufällig sein. Mit dem Befehl "if (isAtEdge()) { turn(Greenfoot.getRandomNumber(90) - 45); }" konnten wir dies umsetzen. Wir haben mehrere Objekte der <a href="#cr1">Crab.class</a> in die World hinzugefügt. Außerdem haben wir die starfish.class und die lobster.class mit gleichen Eigenschaften wie die <a href="#cr1">Crab.class</a> eingefügt.
<img src="crab.png" alt="crab" style="width:80px;height:49px;border:0;">
</p>
<h3 style="color:darkturquoise;" id="nah">
Nahrungskette
</h3>
<p>Unser vorläufiges Ziel war es nun, eine Art Evolutionssimulation zu erstellen. Die drei verschiedenen Klassen sollten je eine Klasse haben, die sie fressen (aus der Welt entfernen) und von einer Klasse gefressen werden (aus der Welt entfernt werden). Wenn die <a href="#cr1">Crab.class</a> die <a href="#sta">starfish.class</a> berührt, entfernt sie diese aus der World.</p>
<h3 style="color:darkturquoise;" id="zas">
Zuschauer als Spieler
</h3>
<p>Als nächstes haben wir eine <a href="#wor">worm.class</a> in das Spiel eingefügt, welche vom Spieler gesteuert werden soll. Mit Befehlen, wie zum Beispiel "{ if (Greenfoot.isKeyDown("left")) { turn(-4); }" haben wir die Pfeiltasten belegt. Die obere und untere lässt den Wurm sich vorwärts und rückwärts bewegen. Die rechte und linke Teste lässt den Wurm sich nach rechts oder links drehen. Der Wurm bekam die Eigenschaft, alle anderen Tiere zu fressen. Um das ganze Spiel etwas zufälliger zu machen, stellten wir in der World ein, dass jedes Objekt an einer zufälligen Stelle in der World erscheint.</p>
<h3 style="color:darkturquoise;" id="mus">
Musik
</h3>
<p>Wir haben Töne eingefügt, die immer dann erklingen, wenn zwei "Actor" gleicher Klasse aufeinander trafen. Da wir dies allerdings als relativ störend auf Dauer empfanden, haben wir diesen Programmabschnitt wieder entfernt.</p>
<h3 style="color:darkturquoise;" id="for">
Fortpflanzung
</h3>
<p>Neue Objekte zu erzeugen stand weiterhin im Fokus unserer Anstrengungen. Wir versuchten eine Art Fortpflanzung einzuführen, indem wir immer ein neues Objekt in die World einfügten, wenn zwei gleiche Objekte aufeinandertrafen. Dies führte allerdings zu einem unkontrollierten, exponentiellen Wachstum (auch Crab-Bomb genannt). Wir haben dieses Problem gelöst, indem wir immer ein neues Objekt eingeführt haben, wenn ein Objekt ein anderes frisst (mit Ausnahme von der <a href="#wor">worm.class</a>). Dazu gaben wir den Befehl an die World, dass immer wenn ein Objekt ein anderes entfernt, ein neuer Objekt mit der gleichen Klasse wie die des Entfernenden einzufügen. Dies haben wir mit folgendem Programmabschnitt gemacht: if (isTouching(starfish.class)) { World myworld; myworld = getWorld(); myworld.addObject( new Crab(), Greenfoot.getRandomNumber(600), Greenfoot.getRandomNumber(400)); removeTouching(starfish.class);</p>
<h3 style="color:darkturquoise;" id="evh">
Einführung von Hunger
</h3>
<p>Mit der Einführung von Variablen eröffneten sich uns neue Möglichkeiten um Zähler einzubauen. Wir konnten jetzt den Faktor Zeit in unser Spiel einbauen. Wir haben einen Hungerwert eingeführt, der ein Objekt aus der World entfernt, wenn es zu lang kein anderes Objekt mehr gefressen (aus der World entfernt) hat. Dazu stellten wir für jedes Objekt einen Zähler (eine Variable, die mit jeder Schleife +1 hochzählt) ein, der zurückgesetzt wird, wenn es ein anderes Objekt aus der World entfernt. Wenn dieser Zähler einen bestimmten Wert erreicht, gibt das Objekt der World den Befehl, dieses Objekt zu entfernen. private int TageSeitMahlzeit TageSeitMahlzeit = TageSeitMahlzeit + 1 if (TageSeitMahlzeit == 300) { getWorld().removeObject(this); } if (isTouching(starfish.class)) { removeTouching(starfish.class); TageSeitMahlzeit = 0; }</p>
<h3 style="color:darkturquoise;" id="sch">
Die Schlange
</h3>
<p>Um unser Programm mehr mit einem Spiel und der damit verbundenen Leistung in Verbindung zu bringen, haben wir eine Verlust-Simulation eingeführt. Eine Schlange frisst den Wurm, wenn dieser einige Zeit lang keine Nahrung mehr zu sich genommen hat. Um dies zu erreichen, haben wir der <a href="#wor">worm.class</a> befohlen, dass sie sich nur bewegen kann, wenn ihre Hungervariable ("tageSeitMahlzeit") unter dem Wert 300 liegt. Wenn dieser Wert erreicht ist, kann sie sich nur noch drehen und sie gibt ein Signal an die World, welche daraufhin eine <a href="#sna">Snake.class</a> auf die Position X=0 und der selben Position Y, wie die der worm.class eingeführt. Diese haben wir durch eine Variable bestimmt, welche die Y-Koordinate beim Erreichen des Hungerlevels (tageSeitMahlzeit=300) misst. private int tageSeitMahlzeit; private int Todesort if (Greenfoot.isKeyDown("up") && tageSeitMahlzeit größer 300) { move(5); } if (tageSeitMahlzeit == 300) { Todesort = getY(); getWorld().addObject( new Snake(), 0, Todesort); } } } Die Schlange bewegt sich parallel zur X-Achse auf den Wurm zu, frißt diesen und bewegt sich in der gleichen Richtung zurück, in der sie hergekommen ist. </p>
<img src="snake.png" alt="snake">
<h3 style="color:darkturquoise;" id="zom">
Zombiekrabben
</h3>
<p>In einer weiteren Programmergänzung behandelten wir das Problem, was mit toten Objekten passiert. Als weitere Spielherausforderung erschufen wir "Zombiekrabben". Crab-Objekte die von der <a href="#wor">Worm.class</a> gefressen wurden sollten nach einer gewissen Zeit "wiederauferstehen". Dies haben wir mit dem Zusammenspiel von mehreren Variablen und if-Schleifen gemacht. Wenn der Wurm eine Krabbe frisst, wird durch zwei Variablen ("TodesortCrabX" und "TodesortCrabY") festgehalten. Außerdem wird die Variable "Zombiecrab" um 1 erhöht. Wenn diese Variable größer als 0 ist, beginnt eine zweite Variable ("ToteCrab") hochzuzählen. Wenn diese bei dem Wert 200 angelangt ist, wird der World ein Befehl gegeben, eine <a href="#cr2">Crab2.class</a> an dem vorher bestimmten Todesort einzufügen. Die Variable "Zombiecrab" wird um 1 subtrahiert und "ToteCrab" wird auf 0 zurückgesetzt. private int Zombiecrab; private int TodesortCrabX; private int TodesortCrabY; private int ToteCrab removeTouching(Crab.class); Zombiecrab = Zombiecrab + 1; TodesortCrabX = getX(); TodesortCrabY = getY(); } if (Zombiecrab > 0) { ToteCrab = ToteCrab + 1; } if (ToteCrab == 200) { getWorld().addObject( new Crab2(), TodesortCrabX, TodesortCrabY); Zombiecrab = Zombiecrab - 1; ToteCrab = 0; } Gäbe es nur ein Objekt der <a href="#cr1">Crab.class</a>, hätte man auch mit einer booleanschen Variable arbeiten könne (True, wenn die <a href="#wor">worm.class</a> die <a href="#cr1">Crab.class</a> berührt hätte). Da es aber mehrere Krabben gibt, haben wir dieses Problem wie oben beschrieben gelöst. Die Crab2.class ist doppelt so schnell, wie die <a href="#cr1">Crab.class</a>. Wenn die <a href="#cr2">Crab2.class</a> auf die lobster.class oder die <a href="#sta">starfish.class</a> trifft, werden beide Objekte aus der World entfernt.</p>
<h3 style="color:darkturquoise;" id="gao">
Game Over
</h3>
<p>Zum Schluss haben wir ein "Game Over" Schriftzug in der World entstehen lassen. Die Grafik dazu haben wir selbst erstellt. Diese <a href="#gam">gameover.class</a> tritt in der Mitte des Spielfeldes auf, wenn die Schlange das linke Ende der Karte erreicht hab.</p>
<img src="game_over.png" alt="game_over">
<h3 style="color:darkturquoise;" id="sco">
Der Score
</h3>
<p> in Bearbeitung</p>
<h2 style="color:lime;" id="pfz">
Pläne für die Zukunft
</h2>
<p>Wie schon vorher gesagt, ist dieses Programm dazu da, sich in Greenfoot herein zu arbeiten. Unser finales Ziel ist immernoch ein Doppelkopfspiel zu entwickeln. Wann genau wir damit beginnen, ist jedoch noch unklar.</p>
<h2>Classes</h2>
<h3 id="cr1">Crab.class</h3>
<p><img src="crab_class_cut1.png" alt="crab_class">
</p>
<h3 id="lob">lobster.class</h3>
<p><img src="lobster_class_cut1.png" alt="lobster_class">
</p>
<h3 id="sta">starfish.class</h3>
<p><img src="starfish_class_cut1.png" alt="starfish_class">
</p>
<h3 id="wor">worm.class</h3>
<p><img src="worm1_class_cut1.png" alt="worm_class">
<img src="worm2_class_cut1.png" alt="worm_class">
<p>
<h3 id="sna">snake.class</h3>
<p><img src="snake_class_cut1.png" alt="snake_class">
</p>
<h3 id="cr2">crab2.class</h3>
<p><img src="crab2_class_cut1.png" alt="crab2_class">
</p>
<h3 id="gam">gameover.class</h3>
<p><img src="gameover_class_cut1.png" alt="gameover_class">
</p>
