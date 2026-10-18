

Wróć na Design Cart
Design Cart Tools

DC Cleaner


Wyczyść HTML
Narzędzia
DC Cleaner
 Edytuj treść po lewej — po prawej zobaczysz kod HTML. Opcje czyszczenia i zamiany są pod edytorem.


Kopiuj kod

Zamień w kodzie

Wyczyść HTML
Edytor treści

1005 słów











































ul
›
li
›
p
›
a
Press Alt+0 for help
1007 words
Kod źródłowy HTML

482 tagów
9341 znaków
do wyczyszczenia
<h1>Magic Energy Bolt — Three.js, WebGL &amp; GLSL</h1>
<p><strong>An interactive energy beam with three intertwined particle streams, procedural lightning, glowing sparks, and cinematic Bloom effects.</strong></p>
<p>I developed this project as a creative experiment in real-time particle effects and procedural animation using JavaScript, Three.js, WebGL, and GLSL shaders.</p>
<p>My goal was to create something more interesting than a straight laser beam or a glowing line.</p>
<p>I wanted the energy to feel alive: twisting, pulsing, branching, and constantly changing its shape.</p>
<p>The result is an interactive energy bolt inspired by magical spells, plasma streams, and science-fiction visual effects.</p>
<p> </p>
<p><strong><a href="https://pawelnosko.com/js-frontend-tools/how-i-created-a-magical-energy-bolt-in-three-js-triple-helix-particles-and-webgl-lightning">View Project Preview</a></strong></p>
<h2>✨ Features</h2>
<h3>Triple-Helix Energy Stream</h3>
<p>The main beam consists of three intertwined particle streams, each with its own color and rotational phase.</p>
<ul>
<li>
<p>Blue, green, and pink energy strands.</p>
</li>
<li>
<p>300 sampled points per strand.</p>
</li>
<li>
<p>Animated rotation around a shared central axis.</p>
</li>
<li>
<p>Smooth transitions between colors.</p>
</li>
<li>
<p>Dynamic changes in brightness and particle size.</p>
</li>
<li>
<p>A curved, constantly changing beam trajectory.</p>
</li>
</ul>
<p>Instead of following a perfectly straight path, the three strands wrap around an irregular backbone controlled by randomly shifting points.</p>
<h3>Procedural Lightning Network</h3>
<p>I created a system of short electrical discharges that appear around the main beam.</p>
<p>Each active energy bolt has a pool of 100 lightning branches.</p>
<p>The electrical effects include:</p>
<ul>
<li>
<p>Randomized branching paths.</p>
</li>
<li>
<p>Short-lived electrical arcs.</p>
</li>
<li>
<p>Animated changes in lightning geometry.</p>
</li>
<li>
<p>Secondary branches extending from the main discharges.</p>
</li>
<li>
<p>Connections between nearby branch endpoints.</p>
</li>
<li>
<p>Color variations and brightness fading.</p>
</li>
</ul>
<p>These connections produce an effect resembling a small, constantly changing neural network of electricity.</p>
<h3>Fast-Moving Energy Particles</h3>
<p>In addition to the main three strands, I added faster particles traveling along the beam.</p>
<p>Each fast particle is represented by three points, creating a short luminous trail.</p>
<p>Their movement speed can be adjusted through the interface.</p>
<h3>Glowing Embers and Sparks</h3>
<p>A separate particle pool handles up to 600 glowing embers.</p>
<p>Each ember receives an individual position, velocity, color, and lifetime.</p>
<p>I gradually reduce its velocity and brightness until it disappears.</p>
<h3>Interactive Shooting Modes</h3>
<p>The demonstration includes two shooting modes.</p>
<p><strong>From Point</strong></p>
<p>The energy beam starts from a fixed location and travels toward the mouse cursor.</p>
<p><strong>From Cursor</strong></p>
<p>The energy beam starts at the cursor position and follows the direction of the most recent pointer movement.</p>
<p>Holding the pointer keeps the energy stream active.</p>
<p>Releasing it causes the trailing end to catch up with the leading end, gradually dissolving the beam instead of instantly hiding it.</p>
<p>The system supports up to five active energy bolts.</p>
<h3>Bloom and Lighting</h3>
<p>I used Three.js postprocessing to create the glowing appearance.</p>
<p>The implementation includes <code>EffectComposer</code>, <code>RenderPass</code>, and <code>UnrealBloomPass</code>.</p>
<p>A custom GLSL shader controls soft particle rendering, while additive blending makes overlapping particles appear brighter.</p>
<p>The interface provides controls for Bloom strength and particle speed.</p>
<h2>🧠 How It Works</h2>
<p>The effect combines several independent systems.</p>
<p><strong>1. Dynamic beam backbone</strong></p>
<p>I generate a sequence of control points along the beam. Each point receives randomized offsets that are smoothly interpolated over time.</p>
<p>This produces a continuously changing, lightning-like path.</p>
<p><strong>2. Three intertwined helices</strong></p>
<p>I calculate particle positions around that backbone using sine and cosine functions.</p>
<p>Each strand is separated by 120 degrees, forming a triple-helix structure.</p>
<p><strong>3. Beam growth and release</strong></p>
<p>Two values control the visible length of the energy stream:</p>
<ul>
<li>
<p><code>head</code> — the leading edge of the beam.</p>
</li>
<li>
<p><code>tail</code> — the trailing edge.</p>
</li>
</ul>
<p>While the pointer is held, the beam grows and remains active.</p>
<p>After release, the tail moves forward faster than the head until the beam disappears.</p>
<p><strong>4. Procedural electrical branches</strong></p>
<p>Small lightning paths are generated around the main strands. Their geometry changes over time, creating the impression of unstable electrical discharges.</p>
<p><strong>5. Dynamic buffers and custom shaders</strong></p>
<p>I use <code>THREE.BufferGeometry</code>, <code>THREE.Points</code>, and <code>THREE.LineSegments</code> to render the effect.</p>
<p>Particle positions, colors, and sizes are updated through typed arrays in JavaScript, while GLSL shaders control the appearance and perspective-based size of the particles.</p>
<p><strong>6. Postprocessing</strong></p>
<p>Finally, Bloom enhances the bright elements and creates the glowing energy effect.</p>
<h2>🛠 Technologies</h2>
<ul>
<li>
<p>JavaScript</p>
</li>
<li>
<p>Three.js r128</p>
</li>
<li>
<p>WebGL</p>
</li>
<li>
<p>GLSL vertex and fragment shaders</p>
</li>
<li>
<p>HTML5 and CSS3</p>
</li>
<li>
<p>BufferGeometry and typed arrays</p>
</li>
<li>
<p>EffectComposer and UnrealBloomPass</p>
</li>
<li>
<p>Pointer Events API</p>
</li>
<li>
<p>requestAnimationFrame</p>
</li>
</ul>
<h2>🚀 Getting Started</h2>
<ol start="1">
<li>
<p>Download or clone the repository.</p>
</li>
<li>
<p>Open <code>index.html</code> in a modern browser with WebGL support.</p>
</li>
<li>
<p>Move your mouse and click to fire an energy bolt.</p>
</li>
<li>
<p>Hold the mouse button to maintain the stream.</p>
</li>
<li>
<p>Release it to let the energy gradually disappear.</p>
</li>
<li>
<p>Experiment with the shooting modes, Bloom intensity, and particle speed.</p>
</li>
</ol>
<p>No npm installation or build process is required for the original single-file demonstration.</p>
<p><strong>Note:</strong> The supplied HTML loads Three.js and its postprocessing scripts from external CDNs, so an internet connection is required unless those dependencies are stored locally.</p>
<h2>⚙️ Customization</h2>
<p>I placed the main parameters near the beginning of the JavaScript code.</p>
<table>
<tbody>
<tr>
<th>Parameter</th>
<th>Default</th>
<th>Description</th>
</tr>
<tr>
<td><code>R</code></td>
<td>70</td>
<td>Maximum beam length</td>
</tr>
<tr>
<td><code>SPEED</code></td>
<td>85</td>
<td>Leading-edge speed</td>
</tr>
<tr>
<td><code>NS</code></td>
<td>300</td>
<td>Points per main strand</td>
</tr>
<tr>
<td><code>NP</code></td>
<td>90</td>
<td>Fast particles per strand</td>
</tr>
<tr>
<td><code>NSP</code></td>
<td>100</td>
<td>Lightning branch pool per bolt</td>
</tr>
<tr>
<td><code>MAXB</code></td>
<td>5</td>
<td>Maximum simultaneous bolts</td>
</tr>
<tr>
<td><code>DL</code></td>
<td>2.6</td>
<td>Control-point spacing</td>
</tr>
<tr>
<td><code>NC</code></td>
<td>32</td>
<td>Number of backbone control points</td>
</tr>
<tr>
<td><code>EN</code></td>
<td>600</td>
<td>Global ember pool size</td>
</tr>
</tbody>
</table>
<p>The <code>PAL</code> array defines the energy colors.</p>
<p>By modifying the palette, movement speed, beam length, particle density, and Bloom intensity, I can turn the same system into a different visual effect.</p>
<h2>💡 Possible Applications</h2>
<p>I see several possible uses for this technique:</p>
<ul>
<li>
<p>Fantasy and magic-themed websites.</p>
</li>
<li>
<p>Interactive landing pages.</p>
</li>
<li>
<p>Browser-based games.</p>
</li>
<li>
<p>Sci-fi interfaces.</p>
</li>
<li>
<p>Plasma and electrical effects.</p>
</li>
<li>
<p>Interactive portfolio presentations.</p>
</li>
<li>
<p>Creative coding experiments.</p>
</li>
<li>
<p>Futuristic product presentations.</p>
</li>
</ul>
<p>The procedural system is not limited to a magic wand. With different colors, movement settings, and emitters, it can represent many forms of energy.</p>
<h2>👨‍💻 Author</h2>
<p><strong>Paweł Nosko — Design Cart</strong></p>
<p>I develop web applications, e-commerce extensions, interactive interfaces, and experimental JavaScript effects.</p>
<ul>
<li>
<p><a href="https://pawelnosko.com/">Paweł Nosko — Developer Blog</a></p>
</li>
<li>
<p><a href="https://www.designcart.pl/">Design Cart — Official Website</a></p>
</li>
<li>
<p><a href="https://pawelnosko.com/js-frontend-tools/how-i-created-a-magical-energy-bolt-in-three-js-triple-helix-particles-and-webgl-lightning">Project Preview</a></p>
</li>
</ul>
<h2>⭐ Support the Project</h2>
<p>If you find this experiment useful, consider starring the repository.</p>
<p>Feel free to explore the particle system, modify the shaders, experiment with the lightning generator, and create your own energy effects.</p>
<p><strong>Three intertwined streams. Hundreds of electrical branches. One living energy beam. ⚡</strong></p>
Opcje czyszczenia
Znajdź i zamień w kodzie HTML
Znajdź
Zamień na

Znajdź
<div>
Zamień na

Znajdź
</div>
Zamień na

Znajdź
Zamień na


Dodaj pole zamiany
Design Cart Tools

Czyszczenie tekstu online
Większość opisów produktów, artykułów i podstron w sklepach internetowych powstaje w Wordzie, LibreOffice albo przez skopiowanie treści z innej witryny. W edytorze wszystko wygląda ładnie — ale pod spodem kryje się HTML, który potrafi rozwalić układ strony.

Do czego służy to narzędzie?
DC Cleaner powstał dla właścicieli sklepów i osób, które edytują treści w panelu administracyjnym, ale nie chcą (i nie muszą) znać się na HTML. Po lewej stronie masz edytor wizualny — wklejasz tekst tak jak w Wordzie. Po prawej od razu widzisz prawdziwy kod, który trafi na stronę: style inline, klasy, setki pustych <span> i często niezamknięte tagi.

Jednym kliknięciem możesz wyczyścić ten kod, naprawić strukturę tagów, usunąć śmieci z programów biurowych i skopiować gotowy fragment do opisu produktu, artykułu na blogu czy strony CMS.

Dlaczego czyścić kod skopiowany z Worda, LibreOffice lub innej strony?
Word i LibreOffice zapisują formatowanie w setkach atrybutów style="" i klasach typu MsoNormal, których Twój sklep nie używa — ale i tak je ładuje.
Kopiowanie ze strony www ciągnie za sobą cudze klasy CSS, identyfikatory, a czasem skrypty i atrybuty data-* z obcego szablonu.
Brudny HTML jest cięższy — opis produktu z 40 KB zamiast 4 KB spowalnia ładowanie i utrudnia pozycjonowanie.
Panel sklepu ma własne style — wklejony „syf” z Worda nadpisuje je inline'owymi stylami i psuje wygląd list, nagłówków i tabel.
Niedomknięte tagi — jak psują stronę?
Przeglądarka próbuje „domyślić się”, gdzie kończy się akapit, lista czy tabela. Gdy w kodzie brakuje </p> albo jest źle zagnieżdżony <div>, reszta strony może wylądować wewnątrz tego akapitu. Efekt? Stopka w środku opisu produktu, przycisk „Dodaj do koszyka” w kolumnie tekstu, rozjechana siatka na mobile.

DC Cleaner przy włączonej opcji „Napraw niezamknięte i uszkodzone tagi” przepuszcza kod przez parser HTML przeglądarki, domyka brakujące elementy, usuwa tagi biurowe (<o:p> z Worda) i zwraca poprawną strukturę. Nad edytorem kodu zobaczysz też ostrzeżenie, jeśli wykryjemy niedopasowane tagi jeszcze przed czyszczeniem.

Przykład: co generuje Word lub LibreOffice
Taki fragment po wklejeniu z dokumentu .docx często wygląda niewinnie w edytorze, ale kod źródłowy to:

<p class="MsoNormal" style="margin:0cm;font-size:12.0pt;font-family:"Calibri",sans-serif">
  <span style="font-size:14.0pt;color:#1F4E79;mso-ansi-language:PL">
    <b>Opis produktu</b>
  <span style="color:red">— promocja!</p>
<p class="MsoNormal">&nbsp;</p>
<p class="MsoListParagraph" style="margin-left:36.0pt;text-indent:-18.0pt;
  mso-list:l0 level1 lfo1"><!--[if !supportLists]--><span>·<span>
  </span></span><!--[endif]-->Materiał: bawełna 100%</p>
<o:p></o:p>
Zwróć uwagę na:

niezamknięty <span> i <b> — zamknięty jest dopiero </p>,
dziesiątki atrybutów style i klas Mso*, których sklep nie zna,
komentarze warunkowe Worda <!--[if !supportLists]-->,
pusty akapit z &nbsp; i tag <o:p> — typowy „śmieć” Office.
Po użyciu DC Cleaner ten sam tekst może wyglądać tak:

<p>
  <strong>Opis produktu</strong>
  <span>— promocja!</span>
</p>
<p>Materiał: bawełna 100%</p>
Krótko, czytelnie, bez śmieci — i co najważniejsze: każdy tag jest domknięty, więc reszta szablonu sklepu nie „wpadnie” do środka opisu.

Jak korzystać?
Wklej treść w lewy panel (edytor wizualny).
Sprawdź kod po prawej — zobaczysz, co naprawdę trafi na stronę.
Ustaw opcje czyszczenia i ewentualnie zamiany tekstu (np. usuń class="MsoNormal").
Kliknij Wyczyść HTML i skopiuj gotowy kod do panelu sklepu.
Całe przetwarzanie odbywa się w Twojej przeglądarce — treść nie jest wysyłana na żaden serwer.

DC Cleaner — edytor WYSIWYG + czyszczenie HTML. Wszystko działa lokalnie w przeglądarce.
