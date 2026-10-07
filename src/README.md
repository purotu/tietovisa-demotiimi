# Ohjelman moduulit

Luokaa tähän oman ohjelman vastuiden mukaiset Python-tiedostot.
Tietovisassa ne voisivat olla `questions.py`, `game.py` ja `results.py`.
Pohjassa näitä ei ole toteutettu: sopikaa rajapinnat ensin yhdessä.

Kun esimerkiksi `src/questions.py` sisältää `lataa_kysymykset`-funktion,
`main.py` voi tuoda sen muodossa `from src.questions import lataa_kysymykset`.
Käynnistäkää ohjelma projektin juuresta komennolla `python main.py`.

Vinkki: käsitelkää tiedostopolut `pathlib.Path`-olioina. Projektin juuren saa
`main.py`:ssä lausekkeella `Path(__file__).resolve().parent`, kun `Path` on tuotu
`pathlib`-moduulista. Välittäkää tiedostopolut niitä tarvitseville funktioille.
