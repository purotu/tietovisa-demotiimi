# Opettajalle: GitHub-pohjan käyttöönotto

## Julkaise tämä pohja kerran

1. Pura zip. Luo GitHubiin tyhjä repository esimerkiksi nimellä
   `python-tiimiprojekti-template`. Älä lisää palvelussa README:tä tai .gitignorea,
   koska ne ovat paketissa valmiina.
2. Avaa pääte puretun `python-tiimiprojekti-template`-kansion sisällä.
3. Suorita alla olevat komennot. Korvaa `OMISTAJA` omalla GitHub-tunnuksella tai
   organisaatiolla ja repositoryn nimi tarvittaessa. GitHub-tunnistautumisen pitää toimia.

```bash
git init -b main
git add .
git commit -m "Lisää Python-tiimiprojektin opetuspohja"
git remote add origin https://github.com/OMISTAJA/python-tiimiprojekti-template.git
git push -u origin main
```

4. Avaa repositoryn **Settings → General** ja valitse **Template repository**.
5. Varmista **Settings → General → Features** -kohdassa, että **Issues** on käytössä.
6. Tarkista GitHubissa, että `.github/ISSUE_TEMPLATE/` näkyy repositorion juuressa
   ja **Issues → New issue** tarjoaa kolme pohjaa.
7. Jaa repositoryn linkki opiskelijoille. Tiimi valitsee **Use this template →
   Create a new repository**, antaa omalle projektilleen nimen ja kutsuu muut jäsenet.
   Tarkistakaa myös tiimin repositoryn Issues-asetus ja opettajan pääsy tarvittaessa.

`Template repository` on GitHubin asetus: sitä ei voi aktivoida pelkällä zipin tiedostolla.
Paketissa ei ole valmiiksi julkaistua repositorya eikä Git-historiaa.
Tiedostot on vietävä repositoryn juureen, ei ylimääräisen projektikansion alle.
`git add .` lisää myös pisteellä alkavat `.github`-kansion ja `.gitignore`-tiedoston.

## Mitä opiskelija saa?

Kopioituvat projektin tiedostot: käynnistysrunko, dokumenttipohjat, esimerkkiaineisto,
Issue-pohjat ja Pull Request -pohja. Varsinaista peliä ei ole toteutettu.
Tehtävälistaa, valmiita issueita tai projektitaulua tämä paketti ei luo.
Tiimi luo issuet itse suunnitteluharjoituksena. Pohjat eivät edellytä omia labeleita.

## Ehdotus ensimmäiselle tapaamiselle (60–90 min)

- 15 min: rajatkaa perusversio ja täyttäkää suunnitelman perustiedot.
- 20 min: nimetkää vastuut ja sopikaa yhteinen tietomuoto sekä 2–4 rajapintaa.
- 15 min: tehkää vähintään kuusi issuea ja jakakaa ensimmäiset tehtävät.
- 10–40 min: aloittakaa pienin toimiva ketju ja kokeilkaa ensimmäistä Pull Requestia.

Käykää tietovisaesimerkki yhdessä läpi ennen oman aiheen pilkkomista.
Älkää edellyttäkö luokkia, jos moduulit ja funktiot riittävät.
Arvioinnissa voi tarkastella vastuunjakoa, rajapintojen selkeyttä, yhteistoiminnan
testausta sekä kykyä perustella ratkaisut. Commitien määrä yksin ei kuvaa työn määrää.

Sopikaa palautustapa, näkyvyys, aikataulu ja arviointiperusteet erikseen.
Pohja tukee sekä repository-linkkiä että alkuperäisen tehtävänannon mukaista OneDrive-zipiä.

## GitHubin viralliset ohjeet

- [Template repositoryn luominen](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-template-repository)
- [Repositoryn luominen pohjasta](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)
- [Issue- ja Pull Request -pohjat](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/about-issue-and-pull-request-templates)
