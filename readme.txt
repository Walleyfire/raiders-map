RAIDERS – Live Gang Map
Tämä on RAIDERS-jengin sisäiseen käyttöön kehitetty reaaliaikainen karttajärjestelmä. Kartan avulla jengi voi hallinnoida alueita, merkitä kasvien sijainteja ja seurata kasvuajastimia reaaliajassa.

🚀 Ominaisuudet
Reaaliaikainen synkronointi: Kaikki muutokset näkyvät kaikille käyttäjille välittömästi Firebase Realtime Databasen ansiosta.

Aluevaltaus: Adminit voivat värittää ja merkitä ruudukosta hallitut alueet.

Kasvuajastimet:

🌿 Kasvi: Pysyvä sijaintimerkintä.

🔥 Kasvaa (14h): Laskuri huumeiden kasvulle.

🍍 Ananas (5h): Laskuri ananaksen kasvulle.

🚬 Sätkä (3h): Laskuri tupakan kasvulle.

✅ Valmis-tila: Emoji vaihtuu automaattisesti, kun aika on kulunut loppuun.

Koordinaatistojärjestelmä: Kalibroitava ruudukko, joka vastaa pelin sisäisiä koordinaatteja.

Anonyymit ehdotukset: Käyttäjät voivat jättää palautetta ja kehitysehdotuksia suoraan sovelluksen sisällä.

🛠 Tekniikka
Frontend: HTML5, CSS3, JavaScript (Canvas API).

Backend: Firebase (Authentication & Realtime Database).

Kartta: Paloiksi jaettu GTA-karttapohja korkealla resoluutiolla.

📋 Käyttöohjeet
Navigointi: Raahaa hiiren oikealla painikkeella, zoomaa rullalla.

Koordinaatit: Klikkaa mitä tahansa ruutua nähdäksesi sen pelikoordinaatit yläpalkissa.

Merkinnät: Vie hiiri markkerin päälle nähdäksesi tarkat kellonajat ja jäljellä olevan ajan.

Admin-paneeli: Kirjautumisen jälkeen voit lisätä/poistaa alueita ja siirtää ruudukkoa.

🛠 Asennus / Kehitys
Jotta kartta toimii, tarvitset Firebase-projektin. Päivitä firebaseConfig-asetukset koodiin:

JavaScript

const firebaseConfig = {
  apiKey: "OM-API-AVAIN",
  authDomain: "PROJEKTI.firebaseapp.com",
  databaseURL: "https://PROJEKTI.firebasedatabase.app",
  projectId: "PROJEKTI",
  // ...muut asetukset
};
📄 Versiohistoria
v2.2.3 - Lisätty Push-toiminnallisuus.

v2.3.5 - Lisätty ehdotusjärjestelmä.

v2.3.6 - Sätkä-laskuri päivitetty 3 tuntiin.

⚙️ Kalibrointi ja MatematiikkaKartan koordinaatisto perustuu lineaariseen muunnokseen pelimaailman ja Canvas-ruudukon välillä.KoordinaattimuunnosPelin koordinaatit lasketaan suhteessa ankkuripisteeseen (base_x, base_y), joka edustaa ruudukon nollapistettä (0,0).X-akseli: Kasvaa oikealle mentäessä (1 ruutu = 100 peliyksikköä).Y-akseli: Kasvaa ylöspäin mentäessä (pelissä), mutta Canvas-koordinaatistossa $y$ kasvaa alaspäin.Käytetty kaava koodissa:$$x_{peli} = base\_x + (gx \cdot 100)$$$$y_{peli} = base\_y - (gy \cdot 100)$$Missä $gx$ ja $gy$ ovat ruudukon indeksit.KalibrointitoimintoJos ruudukko siirtyy (esim. GRID_SIZE muuttuessa), admin voi kalibroida sen uudelleen:Valitse ruutu kartalta, jonka koordinaatit tiedät pelistä.Syötä pelin koordinaatit targetX ja targetY kenttiin.Paina ASETA RUUTUUN.Järjestelmä laskee uudet base_x ja base_y arvot siten, että valittu ruutu vastaa syötettyjä koordinaatteja.Push-logiikkaJotta kaikki käyttäjät saavat tiedon kriittisistä päivityksistä ilman sivun uudelleenlatausta, järjestelmä tarkkailee Firebasen version-kenttää. Kun admin painaa PUSH, versionumero päivittyy tietokantaan ja kaikille avoinna oleville sivuille ilmestyy välittömästi punainen päivityskehote.
