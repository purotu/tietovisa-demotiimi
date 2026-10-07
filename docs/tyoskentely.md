# Issue → haara → Pull Request

## 1. Valitse pieni tehtävä

Avaa **Issues → New issue** ja valitse pohja. Kirjaa tavoite, rajaus,
riippuvuudet ja todennettavat valmistumisehdot. Valitse tekijä kohdasta **Assignees**.
Jos tehtävä ei mahdu yhteen työskentelykertaan, pilko se pienemmäksi.

## 2. Tee oma haara

Esimerkissä tehtävän numero on 3. Korvaa se oman issuesi numerolla.
Aloita puhtaasta työtilasta: `git status` näyttää keskeneräiset muutokset.
Tallenna keskeneräinen työ omalle haaralleen ennen vaihtamista.

```bash
git switch main
git pull --ff-only
git switch -c 3-vastauksen-tarkistus
```

Jos päähaaranne nimi on muu kuin `main`, käyttäkää sitä.

## 3. Toteuta, kokeile ja tallenna

Tee rajattu muutos. Kokeile tavallinen tapaus ja olennaiset virhetilanteet.
Lisää vain tehtävään kuuluvat tiedostot. Esimerkkipolku syntyy vasta toteutuksenne yhteydessä:

```bash
git status
git add src/game.py
git diff --staged
git commit -m "Lisää vastauksen tarkistus"
git push -u origin 3-vastauksen-tarkistus
```

## 4. Avaa Pull Request

Valitse GitHubissa omasta haarasta Pull Request tiimin päähaaraan.
Täytä valmiiksi avautuva pohja: mitä muuttui, miten testasit ja `Closes #3`
(oman tehtäväsi numero). Pyydä toinen tiimiläinen tarkistajaksi.

Tarkistaja lukee muutokset ja kokeilee toimintaa. Korjatkaa havaitut puutteet
samaan haaraan. Yhdistäkää hyväksytty muutos päähaaraan.
`Closes #3` sulkee saman repositoryn tehtävän, kun Pull Request yhdistetään oletushaaraan.

## 5. Jatkakaa ajantasaisesta versiosta

Palaa päähaaraan ja päivitä se ennen uutta tehtävää:

```bash
git switch main
git pull --ff-only
```

Jos Git ilmoittaa ristiriidasta tai päivitys epäonnistuu, selvittäkää tilanne yhdessä.
Älkää poistako toisen muutoksia tai pakottako yhteisen haaran päivitystä.
Sopikaa etukäteen, kuka muokkaa yhteisiä tiedostoja kuten `main.py`.

## Työn seuranta

Issues-lista riittää aluksi. Halutessanne luokaa GitHub Project -taulu:
**Todo → In progress → Done**. Siirtäkää tehtävä valmiiksi vasta yhdistämisen
ja valmistumisehtojen tarkistamisen jälkeen. Taulu luodaan erikseen GitHubissa.
Kirjatkaa esteet issueen ja päivittäkää suunnitelmaa rajapintojen muuttuessa.
