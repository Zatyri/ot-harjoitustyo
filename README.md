# Ohjelmistotekniikka, kevät 2022

This repository is for course *TKT20002* at **Helsinki University**

# HuoltoSovellus

Sovellus antaa käyttäjälle mahdollisuuden luoda pienkiinteistölle huolto-ohjelman. Huolto-ohjelmaan voi lisätä huoltotoimenpitäitä joiden avulla on helppo pitää kirjaa milloin huollot on suoritettava. Sovellus muistaa myös, tehtyjä huoltotoimenpitäitä ja niistä voi luoda raportin josta näkee suoritettuja huoltoja

## Harjoitustyön dokumetaatio
[vaatimusmaarittely.md](https://github.com/Zatyri/ot-harjoitustyo/blob/master/dokumentaatio/vaatimusmaarittely.md)

[tuntikirjanpito.md](https://github.com/Zatyri/ot-harjoitustyo/blob/master/dokumentaatio/tuntikirjanpito.md)

[changelog.md](https://github.com/Zatyri/ot-harjoitustyo/blob/master/dokumentaatio/changelog.md)

[arkkitehtuuri.md](https://github.com/Zatyri/ot-harjoitustyo/blob/master/dokumentaatio/arkkitehtuuri.md)

[kayttoohje.md](https://github.com/Zatyri/ot-harjoitustyo/blob/master/dokumentaatio/kayttoohje.md)

[testausdokumentti.md](https://github.com/Zatyri/ot-harjoitustyo/blob/master/dokumentaatio/testaus.md)

## Julkaisut

[Viikko 5](https://github.com/Zatyri/ot-harjoitustyo/releases/tag/viikko5)

[Viikko 6](https://github.com/Zatyri/ot-harjoitustyo/releases/tag/viikko6)

[Loppupalautus](https://github.com/Zatyri/ot-harjoitustyo/releases/tag/viikko7)

## Komentorivitoiminnot

Mene ensin kansioon "Huoltosovellus"
```
cd Huoltosovellus/
```

Ohjelman käynnistys
```
mvn compile exec:java -Dexec.mainClass=pienkiinteistohuoltosovellus.ui.UserInterface
```

jar tiedoston luonti
```
mvn package
```

JavaDoc luonti
```
mvn javadoc:javadoc
```
JavaDocia voi tarkastella avaamalla selaimella tiedosto target/site/apidocs/index.html

# Testaus

Ohjelman testaus
```
mvn test
```

Testikattavuusraportti
```
mvn jacoco:report
```

Checkstyle
```
mvn jxr:jxr checkstyle:checkstyle
```

