## Luokkakaavio Monopoli

```mermaid
 classDiagram
    Peli <-- "2..8" Pelaaja
	Peli <-- "2" Noppa
	Peli <-- "1" Pelilauta
	Pelilauta --> "40" Ruutu
	Pelaaja "1" <--> "1" Nappula
	Ruutu "1" <--> "1" Nappula
	Aloitusruutu <|-- Ruutu : Inheritance
	Vankila <|-- Ruutu : Inheritance
	Sattuma <|-- Ruutu : Inheritance
	Yhteismaa <|-- Ruutu : Inheritance
	Asema <|-- Ruutu : Inheritance
	Laitos <|-- Ruutu : Inheritance
	Katu <|-- Ruutu : Inheritance
	Sattuma <-- "*" Kortti
	Yhteismaa <-- "*" Kortti
	Pelaaja <-- "*" Rahaa
	
	class Ruutu{
		+Ruutu seuraavaRuutu
		+Ruutu edellinenRuutu
		+jokinToiminto() toiminto
		}
	class Katu {
		+String nimi
		+Int taloja
		+Boolean onHotelli
		+Pelaaja omistaja
		+mahtuukoTaloja() Boolean
		+rakennaTalo() void
		+rakennaHotelli() void
		}
	class Peli{
		+Ruutu Aloitusruutu
		+Ruutu Vankila
		}
	class Kortti{
		+jokinToiminto() toiminto
		}
	class Pelaaja{
		+Int rahaMaara
		}
```

## Sekvenssikaavio Machine

```mermaid
sequenceDiagram
	Caller->>Machine: Ohjelman ulkopuolinen kutsuja
	Machine->>FuelTank: new FuelTank()
	FuelTank->>Machine: FuelTank
	Machine->>FuelTank: tank.fill(40)
	Machine->>Engine: new Engine(tank)
	Engine->>Machine: Engine
	Caller->>Machine: drive()
	Machine->>Engine: start()
	Engine->>FuelTank: consume(5)
	Machine->> Engine: isRunning()
	Engine->> Machine: boolean
	Machine->>Engine: useEnergy()
	Engine->>FuelTank: consume(10)
```

## Sekvenssikaavio HSL
```mermaid
sequenceDiagram
	Main->>HKLLaitehallinto: new HKLLaitehallinto()
	HKLLaitehallinto->>Main: HKLLaitehallinto
	Main->>Lataajalaite: rautatietori = new Lataajalaite()
	Lataajalaite->>Main: Lataajalaite
	Main->>Lukijalaite: ratikka6 = new Lukijalaite()
	Lukijalaite->>Main: Lukijalaite
	Main->>Lukijalaite: bussi244 = new Lukijalaite()
	Lukijalaite->>Main: Lukijalaite
	Main->>HKLLaitehallinto: lisaaLataaja(rautatietori)
	Main->>HKLLaitehallinto: lisaaLukija(ratikka6)
	Main->>HKLLaitehallinto: lisaaLukija(bussi244)
	Main->>Kioski: lippuluukku = new Kioski()
	Kioski->>Main: Kioski
	Main->>Kioski: artonKortti = lippuLuukku.ostaMatkakortti("Arto")
	Kioski->>Matkakortti: uusiKortti = new Matkakortti("Arto")
	Matkakortti->>Kioski: Matkakortti
	Kioski->>Main: uusiKortti
	Main->>Lataajalaite: lataaArvoa(artonKortti, 3)
	Lataajalaite->>Matkakortti: artonKortti.kasvataArvoa(3)
	Main->>Lukijalaite: ratikka6.ostaLippu(artonKortti, 0)
	Lukijalaite->>Matkakortti: artonKortti.getArvo()
	Matkakortti->>Lukijalaite: double (3)
	Lukijalaite->>Matkakortti: artonKortti.vahennaArvoa(1.5)
	Lukijalaite->>Main: boolean (true)
	Main->>Lukijalaite: bussi244.ostaLippu(artonKortti, 2)
	Lukijalaite->>Matkakortti: artonKortti.getArvo()
	Matkakortti->>Lukijalaite: double (1.5)
	Lukijalaite->>Main: boolean (false)


```
