\# 🗺️ RAIDERS – Live Gang Map



Tämä on \*\*RAIDERS\*\*-jengin sisäinen työkalu pelimaailman hallintaan. Järjestelmä mahdollistaa alueiden reaaliaikaisen seurannan, huumeiden kasvuajastimet ja jengin välisen kommunikoinnin ehdotusjärjestelmän kautta.







\## 🚀 Keskeiset Ominaisuudet



\* \*\*Reaaliaikaisuus:\*\* Kaikki merkinnät ja valtaukset synkronoituvat välittömästi kaikille käyttäjille (Firebase Realtime DB).

\* \*\*Älykkäät Laskurit:\*\* Järjestelmä laskee automaattisesti, milloin tuote on kerättävissä ja muuttaa ikonin tilaa.

&nbsp;   \* 🌿 \*\*Kasvi:\*\* Pysyvä paikkamerkki.

&nbsp;   \* 🔥 \*\*Kasvaa (14h):\*\* Suuri huumekasvi.

&nbsp;   \* 🍍 \*\*Ananas (5h):\*\* Hedelmäkasvusto.

&nbsp;   \* 🚬 \*\*Sätkä (3h):\*\* Tupakkaviljelmä.

&nbsp;   \* ✅ \*\*Valmis:\*\* Ilmestyy automaattisesti, kun aika on kulunut umpeen.

\* \*\*Koordinaattityökalu:\*\* Klikkaa karttaa nähdäksesi suoraan pelin sisäiset koordinaatit (X, Y).

\* \*\*Admin-työkalut:\*\* Alueiden väritys, ruudukon kalibrointi ja ehdotusten hallinta.



---



\## 🛠️ Tekninen Toteutus



\### Kalibrointilogiikka

Kartan tarkkuus perustuu dynaamiseen ankkuripisteeseen. Pelin koordinaatit lasketaan suhteessa `base\_x` ja `base\_y` arvoihin:



$x\_{peli} = base\\\_x + (gx \\cdot 100)$

$y\_{peli} = base\\\_y - (gy \\cdot 100)$



\*Missä $gx$ ja $gy$ ovat ruudukon indeksit.\*



Admin voi kalibroida koko ruudukon valitsemalla yhden tunnetun pisteen ja syöttämällä sen pelikoordinaatit. Järjestelmä hoitaa loput.



\### Versiohallinta (Push)

Sovelluksessa on sisäänrakennettu \*\*Push\*\*-toiminto. Kun koodiin tehdään kriittisiä muutoksia, admin voi päivittää version tietokantaan, jolloin kaikille käyttäjille ilmestyy välittömästi ilmoitus:

> ⚠️ KARTASTA ON UUSI VERSIO! Päivitä sivu (CTRL + F5).



---



\## 📖 Käyttöohjeet



\### Käyttäjät

1\.  \*\*Liikkuminen:\*\* `Hiiren oikea painike` (raahaa) ja `Rulla` (zoomaa).

2\.  \*\*Ehdotukset:\*\* Klikkaa vasemman reunan \*\*💡 Ehdotukset\*\* -nappia. Voit lukea muiden ideoita ja jättää oman anonyymin ehdotuksesi.

3\.  \*\*Tiedot:\*\* Vie hiiri minkä tahansa markkerin päälle nähdäksesi tarkan valmistumisajan ja "Valmis" -ennusteen.



\### Adminit

1\.  Kirjaudu sisään yläkulman \*\*Admin\*\*-napista.

2\.  Valitse väri tai markkerityyppi oikeasta paneelista.

3\.  Klikkaa karttaa asettaaksesi tai poistaaksesi merkintöjä.

4\.  Käytä \*\*PUSH\*\*-nappia, kun haluat pakottaa käyttäjät päivittämään selaimeen uuden koodiversion.



---



\## 📦 Asennus



1\.  Kloonaa repo.

2\.  Luo projekti \[Firebase Consoleen](https://console.firebase.google.com/).

3\.  Ota käyttöön \*\*Authentication\*\* (Email/Password) ja \*\*Realtime Database\*\*.

4\.  Päivitä `firebaseConfig` koodin alkuun.

5\.  Aseta tietokannan säännöiksi:

&nbsp;   ```json

&nbsp;   {

&nbsp;     "rules": {

&nbsp;       ".read": true,

&nbsp;       ".write": "auth != null"

&nbsp;     }

&nbsp;   }

&nbsp;   ```



---



\*\*Kehittäjä:\*\* Raiders Dev Team  

\*\*Versio:\*\* 2.3.6 (Build 2026)

