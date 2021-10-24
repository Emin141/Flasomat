# Informacije o djelovanju projekta

## Korisnik

Pod korisnikom se podrazumjeva osoba koja ima privatni račun na google play ili iOS appstore. Korisnik ima aplikaciju na telefonu koja je povezana sa njegovim računom stranice sa koje je skinuo aplikaciju. Skidanjem te aplikacije dobija jedinstveni ID koji je poznat korisniku, i dobija neki drugi interni ID za identifikaciju u bazi podataka. Ovaj prvi ID, od sad **Korisnički ID** je poznat korisniku. Kada dođe do prese koja je locirana na nekom javnom mjestu ukuca svoj korisnički ID i stavlja PET boce u otvor, i nakon uspješnog presovanja dobija jedan poen na svoj ID u bazi podataka (od sada **Interni ID**).

Dužnost korisnika je da u presu stavi praznu PET bocu. Na presi su locirani moduli koji su namjenjeni da pomognu pri tome:

* U slučaju da boca nije prazna a jest PET boca, presa ispisuje korisniku da je treba isprazniti. U presi se nalazi modul koji je spremnik za tekućine, tako da korisnik može istresti sadržaj.
* U slučaju da boca nije PET boca, presa ne prima bocu i javlja korisniku. Dužnost korisnika je da je izvadi i stavi u drugi modul koji je spremnik za komunalni otpad. Ovo bi trebalo da spriječi situacije gdje korisnik dođe sa, npr., 50 boca od kojih 10 nije PET, i onda da neodgovorno ih baci u okolinu nakon što ih ne želi nositi sa sobom na drugo mjesto namjenjeno za komunalni otpad.
* Presa ima pored sebe i modul koji je spremnik za PP čepove, namjenjene za reciklažu čepova u invalidska kolica. Ovo je proizvoljno - korisnik može birati da skloni čep sa PET boce sam, a i ne mora. Primarna separacija olakšava dalju reciklažu, ali separacija PET/PP nije neophodna.

Prosječna vrijednost PET ambalaže je u odnosu flaša:KM = 22000:500. Prema tome, 44 flaše, odnosno poena koji su spremljeni na interni ID, su ekvivalent vrijednosti od 1 KM. Ipak, pošto je nezgodno pratiti vrijednost u odnosu 44:1, a i da bi se podsticalo korištenje i održavanje prese i projekta, ta vrijednost je **50:1**.

Korisnik sa svojim korisničkim ID-om može doći do uslužitelja, i koristiti te poene kao vid vaučera. Npr. 500 poena bi se moglo zamijeniti za 10 KM usluga. Korisnik to može uraditi samo na mjestima gdje su usluge omogućene preko projekta, i to koristeći svoj korisnički ID ili QR kod (zavisno od implementacije).

## Uslužitelj

Uslužitelj u svojoj filijali ima program na računaru (može se napraviti i na telefonu) koji pri skeniranju koda (ili slanju ID-a, ali to je složenije sigurnosno pitanje opisano u folderu "app") šalje na glavni server zahtjev da se umanji broj bodova za uslugu. Korisnik gubi bodova koliko je iskoristio sa svoj ID-a, a uslužitelj dobija na svoj **Uslužiteljski ID**. Na taj način se prati koliko novčane vrijednosti je uslužitelj izdao, i toliko se kompenzira na kraju *operativni ciklus* (vidjedi poglavlje). U prvom operativnom ciklusu uslužitelji dobijaju određeni depozit novca za izvršavanje usluga.

Uslužitelj obezbjeđuje uslugu nakon plaćanja bodovima. Npr., gorivo, telefonski kredit, hrana, ulaznica, autobuska karta i sl.

## Presa

### Hardver

Presa je kvadar dimenzija v:š:d = 140cm:80cm:50cm. Detaljniji dijagram i izgled se može naći u folderu "3d_model". Na visini od 120cm se nalazi otvor sa automatiziranim poklopcem. U taj otvor se stavljaju PET flaše. Ispod tog otvora nalazi se latica sa rešetkom koja se otvara pod uglom od 45° prema gore, koja je namjenjena za istresanje tečnosti. Sa lijeve ili desne strane se nalazi mali pretinac sa ostavljanje čepova, LED ekran sa uputstvom za korisnika, i info ploča sa fizički naslikanim informacijama (kao npr. gdje se mogu trošiti bodovi, za šta se koristi reciklat, informacije o projektu i sl.) Pored prese se nalazi i kanta za komunalni otpad. U unutrašnjosti prese se nalaze ispod visine 100cm na strani gdje je otvor za flaše barel za tečnosti, a na drugoj strani se nalazi komora za sakupljanje presovanog PET-a.

U otvoru prese se nalazi šuplji cilindar sa rupicama u stijenci. Flaša se položi u njega, i time djeluje gravitacijom na vagu ispod cilindra. Cilindar učitava težinu i ako prelazi određenu granicu, boca je ili puna ili nije PET boca. Osim toga, na jednoj strani cilindra se nalazi infracrveni emiter sa IR filterom od 730nm (i 745nm ako uspijemo naći takav filter, vrlo je skup za namjensko pravljenje...). Signal putuje kroz bocu i mjeri se intenzitet zračenja. Poredi se sa referentnim senzorom i provjerava se da li je signal slabiji kad prolazi kroz predmet. Ako je u pitanju PET boca, frekvencije 730nm i 745nm pokazuju karakterističnu apsorpciju i flaša jest PET. Ako je flaša PET ali teška, korisnik dobija signal da je treba isprazniti. Ako nije PET, korisnik dobija signal da je odstrani. Ovo je izvršeno preko ekrana pored otvora za presu. 

U slučaju da je predmet prošao PET test, poklopac od otvora se zatvara, boca se probuši sa donje strane, i hidraulička presa je pritisne od poklopac otvora. Tečnost se iz nje iscjedi kroz rupice na cilindru prese, a flaša se pri povratku poklopca prebaci u pretinac za presovani PET. Korisnik dobija signalizaciju da je presovanje u toku, i kada je završeno. 

U slučaj da predmet nije prošao PET test radi toga što je PET boca puna, korisnik dobija uputu da je isprazni. Otključava se otvor od lijevka za tečnost. Teško je opisati kako izgleda taj modul, pa se više informacija može naći vizuelno u folderu "3d_model".

U slučaju da predmet nije prošao PET test jer nije PET, korisnik dobija uputu da odstrani otpad u kantu za komunalni otpad.

### Softver

*To do*

## Operativni ciklus

*To do*