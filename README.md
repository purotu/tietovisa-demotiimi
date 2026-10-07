# [Projektin nimi] – Python-tiimiprojekti

> Täytettävä pohja 2–3 opiskelijan tiimille. Korvatkaa hakasulkeissa olevat
> kohdat omilla tiedoillanne. Tietovisa on suunnitteluesimerkki, ei pakollinen aihe.

## Oma projektimme

- **Idea:** [Mitä ohjelma tekee ja kenelle?]
- **Tiimi:** [Nimet tai sovitut nimimerkit ja GitHub-tunnukset]
- **Aikataulu:** [Aloitus ja palautuspäivä]
- **Nykyinen tila:** Aloituspohja; omaa sovellusta ei ole vielä toteutettu.

## Aloittakaa tästä

1. Luokaa tiimille yksi yhteinen repository opettajan pohjasta toiminnolla
   **Use this template → Create a new repository**. Lisätkää tiimiläisille käyttöoikeudet.
2. Kloonatkaa tiimin repository jokaisen omalle koneelle.
3. Valitkaa aihe ja täyttäkää [suunnitelma](docs/suunnitelma.md) yhdessä.
4. Sopikaa moduulien vastuut sekä tärkeimpien funktioiden parametrit ja paluuarvot.
5. Luokaa vähintään kuusi pientä tehtävää: **Issues → New issue → Tehtävä**.
   Valitkaa jokaiselle tekijä kohdasta **Assignees**.
6. Toteuttakaa ensimmäiseksi yksi pieni toimiva ketju ja yhdistäkää muutoksia usein.

Opettajalle: [pohjan julkaisu ja käyttöönotto](docs/opettajalle.md).

## Käynnistys

Tarvitsette Python 3:n ja Gitin. Aloituspohja ei tarvitse ulkoisia Python-kirjastoja.
Avaa pääte projektin juurikansiossa ja suorita:

```bash
python main.py
```

Jos koneesi käyttää komentoa `python3` tai Windowsissa `py`, käytä sitä `python`-komennon tilalla.
Pohja tulostaa aloitusviestin. Se ei vielä käynnistä tietovisaa.
Päivittäkää tämä ohje, kun toteutatte oman ohjelman ja mahdolliset riippuvuudet.

## Kansiorakenne

```text
python-tiimiprojekti-template/
├── main.py                       # Oman ohjelman käynnistyspaikka
├── src/
│   ├── __init__.py
│   └── README.md                 # Ohje omien moduulien luomiseen
├── data/
│   ├── README.md
│   ├── esimerkkikysymykset.csv    # Viisi tietovisakysymystä
│   └── output/.gitkeep           # Paikallisesti syntyvät tulokset
├── tests/README.md               # Ohje testien lisäämiseen
├── docs/
│   ├── suunnitelma.md
│   ├── loppuraportti.md
│   ├── tietovisa-esimerkki.md
│   ├── tyoskentely.md
│   ├── testaus.md
│   └── opettajalle.md
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── 01-tehtava.md
│   │   ├── 02-virhe.md
│   │   ├── 03-suunnittelu.md
│   │   └── config.yml
│   └── pull_request_template.md
├── .gitignore
└── README.md
```

## Miten työ jaetaan?

Yksi moduuli vastaa yhdestä selkeästä asiasta. Moduulit ja funktiot riittävät;
luokkia ei tarvitse lisätä vain luokkien vuoksi.
[Tietovisaesimerkki](docs/tietovisa-esimerkki.md) näyttää vastuut,
yhteisen tietomuodon, rajapinnat ja pienet tehtävät. Soveltakaa mallia omaan aiheeseenne.

## Yhteinen työskentely

**Issue → oma haara → toteutus ja testaus → Pull Request → toisen tarkistus → yhdistäminen.**

[Työskentelyohje](docs/tyoskentely.md) sisältää komennot ja tarkistuslistan.
Issue-pohjat tarjoavat rakenteen uusille tehtäville; ne eivät luo tehtäviä automaattisesti.

## Valmis projekti ja palautus

- [ ] Ohjelman sovitut perustoiminnot toimivat.
- [ ] Ohjelma on jaettu moduuleihin tai luokkiin ja käyttää tiedostoja tietovarastona.
- [ ] Kaikki tiimiläiset ovat osallistuneet ohjelmointiin ja toisten työn tarkistamiseen.
- [ ] README sisältää ajantasaiset käynnistys- ja käyttöohjeet.
- [ ] Suunnitelma, työnjako, aikataulu, testaus ja loppuraportti on täytetty.
- [ ] Ohjelman käynnistys on kokeiltu myös puhtaasta kopiosta.
- [ ] Palautus on tehty opettajan ohjeen mukaan.

Jos palautatte zipin OneDriveen, sisällyttäkää lähdekoodi, tarvittava data ja dokumentaatio
sekä jakakaa se opettajan nimeämille vastaanottajille. Lisätkää loppuraporttiin
repositoryn ja tärkeiden issueiden sekä Pull Requestien linkit: GitHubin tehtävät,
keskustelut ja Git-historia eivät sisälly tavalliseen lähdekoodizipiin.
