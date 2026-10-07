# Testit

Tähän voitte lisätä automaattisia testejä esimerkiksi Pythonin `unittest`-moduulilla.
Pohjassa ei ole valmiita testejä. Kirjatkaa käsin tehdyt kokeilut tiedostoon
[docs/testaus.md](../docs/testaus.md).

Kun lisäätte `unittest`-testejä nimillä `test_*.py`, ajakaa projektin juuresta:

```bash
python -m unittest discover -s tests -v
```

Nolla löydettyä testiä ei osoita ohjelman toimivuutta. Aloittakaa esimerkiksi
vastauksen tarkistuksesta: oikea vastaus ja väärä vastaus tuottavat eri tulokset.
