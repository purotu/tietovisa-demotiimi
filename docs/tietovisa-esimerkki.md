# Esimerkki: tietovisan pilkkominen

Tämä on suunnittelumalli. Pelin toteutus jää opiskelijoille.
Omassa projektissa vaihtakaa vastuut ja tiedot aiheeseenne sopiviksi.

## Perusversio ja vastuut

Perusversio kysyy nimen, lukee viisi kysymystä tiedostosta, hyväksyy vastaukset 1–4,
antaa oikeasta vastauksesta pisteen, näyttää loppupisteet ja tallentaa tuloksen.
Valikko, satunnaistus ja ennätyslista ovat myöhempiä lisätehtäviä.

| Moduuli | Vastuu | Ensimmäinen tekijä kolmen hengen tiimissä |
|---|---|---|
| src/questions.py | Lukee kysymystiedoston yhteiseen tietomuotoon | A |
| src/game.py | Kysyy vastaukset ja laskee pisteet | B |
| src/results.py | Lisää tuloksen tiedostoon | C |
| main.py | Kokoaa nämä yhdeksi ohjelmaksi | Yhdessä |

Kahden hengen tiimissä A voi tehdä kysymykset ja tallennuksen, B pelin kulun;
tasatkaa työtä pienillä issueilla. Vastuut eivät ole pysyviä henkilökohtaisia alueita.

## Yhteinen tietomuoto

Yksi kysymys on sanakirja. Kysymykset välitetään listana tällaisia sanakirjoja:

```python
{
    "teksti": "Mikä on Suomen pääkaupunki?",
    "vaihtoehdot": ["Turku", "Tampere", "Helsinki", "Kuopio"],
    "oikea": 3,
}
```

`oikea` on kokonaisluku 1–4, mutta listan indeksit ovat 0–3.
Esimerkiksi oikean vaihtoehdon teksti löytyy indeksillä `oikea - 1`.
CSV:n tekstimuotoinen oikean vastauksen numero muunnetaan kokonaisluvuksi lukuvaiheessa.

## Sovitut rajapinnat

| Funktio | Parametrit | Palauttaa | Sopimus |
|---|---|---|---|
| questions.lataa_kysymykset(polku) | pathlib.Path | list[dict] | Lukee UTF-8 CSV:n, erotin `;`; ei kysy syötettä eikä tulosta |
| game.tarkista_vastaus(kysymys, vastaus) | dict, int (1–4) | bool | Vertaa vastausta `oikea`-arvoon; ei muuta kysymystä |
| game.pelaa(kysymykset) | list[dict] | int | Näyttää annetut kysymykset, kysyy vastaukset ja palauttaa pisteet |
| results.tallenna_tulos(polku, nimi, pisteet) | pathlib.Path, str, int | None | Lisää yhden tuloksen UTF-8 CSV:hen; aiemmat rivit säilyvät |

Lukija tarkistaa, että teksti ja neljä vaihtoehtoa ovat ei-tyhjiä sekä `oikea` on 1–4.
Puuttuva kysymystiedosto aiheuttaa `FileNotFoundError`-poikkeuksen, virheellinen sisältö
`ValueError`-poikkeuksen. Myös tyhjä kysymysaineisto on virhe.
`main.py` ottaa nämä kiinni, näyttää ymmärrettävän viestin ja lopettaa pelin käynnistyksen.

`pelaa` kysyy uudelleen, jos syöte on tyhjä, tekstiä tai alueen 1–4 ulkopuolella.
Virheellinen syöte ei kuluta kysymystä. Jokaisesta oikeasta vastauksesta saa yhden pisteen.

Tallennus luo tarvittaessa tuloskansion ja tiedoston. Tulostiedostossa on
otsikko `nimi;pisteet`, joka kirjoitetaan vain uuteen tai tyhjään tiedostoon.
Käyttäkää `csv`-moduulia, jotta myös nimen sisältämä puolipiste käsitellään oikein.
`main.py` kysyy ei-tyhjän nimimerkin ja käsittelee tallennuksen `OSError`-virheen:
näyttää pisteet ja kertoo, ettei tallennus onnistunut.

Nämä ovat tämän esimerkin päätöksiä. Sopikaa omalle projektille vastaavat käytännöt.

## Ensimmäinen yhdistettävä ketju

Lukekaa tiedoston ensimmäinen kysymys, näyttäkää se ja tarkistakaa vastaus.
Sen jälkeen laajentakaa viiteen kysymykseen ja tuloksen tallentamiseen.
Pelin tekijä voi aloittaa yllä olevalla käsin kirjoitetulla sanakirjalla,
vaikka tiedoston lukeminen ei ole vielä valmis.

## Kopioitavat tehtäväehdotukset

Luokaa näistä erilliset GitHub-issuet **Tehtävä**-pohjalla. Tunnukset T1–T8
ovat tämän dokumentin tunnuksia; korvatkaa ne todellisilla issue-linkeillä.

| Tunnus ja otsikko | Valmis kun | Riippuvuus |
|---|---|---|
| T1: Sovi tietomuoto ja rajapinnat | Parametrit, paluuarvot ja virhetilanteet kirjattu suunnitelmaan; kaikki hyväksyneet | Ei riippuvuutta |
| T2: Lue kysymykset CSV:stä | Viisi kysymystä palautuu sovitussa muodossa; puuttuva ja virheellinen tiedosto kokeiltu | T1 |
| T3: Tarkista vastaus | Oikea vastaus tuottaa True ja väärä False; kokeiltu molemmat | T1 |
| T4: Kysy yksi kysymys | Vaihtoehdot näkyvät ja vain 1–4 hyväksytään; tyhjä, kirjain, 0 ja 5 kokeiltu | T1 |
| T5: Yhdistä yhden kysymyksen ketju | Tiedostosta luettu kysymys voidaan pelata ja palaute näkyy | T2, T3, T4 |
| T6: Pelaa viisi kysymystä | Jokainen kysytään kerran; pisteet välillä 0–5 ja lopuksi näytetään tulos | T5 |
| T7: Tallenna tulos | Uusi tiedosto syntyy; kaksi tallennusta säilyy; puolipiste nimessä toimii | T1 |
| T8: Viimeistele kokonaisuus ja ohje | Nimi kysytään, peli pelataan ja tulos tallentuu; virheet käsitellään; uusi kopio toimii ohjeilla | T6, T7 |

Esimerkkitehtävä T3:

- **Tavoite:** pelin kulku voi selvittää, oliko vastaus oikein.
- **Rajaus:** vain `tarkista_vastaus` tiedostossa `src/game.py`; ei vielä käyttöliittymää.
- **Rajapinta:** `tarkista_vastaus(kysymys, vastaus) -> bool`.
- **Valmis kun:** yllä olevalla kysymyksellä vastaus 3 palauttaa `True`, 1 palauttaa `False`
  ja kysymyksen sisältö säilyy muuttumattomana.
- **Riippuvuus:** yhteinen tietomuoto sovittu (T1).

T2, T3–T4 ja T7 voidaan aloittaa rinnakkain T1:n jälkeen.
Sopikaa T3:n ja T4:n yhteisestä tiedostosta: sama tekijä peräkkäin tai yhteinen toteutus.
