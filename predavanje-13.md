# Predavanje 13

## Pointerski uredjaji
- Sluze za pointiranje (lol)

### Pointerski uredjaji indirektne kontrole 
- Njegov posrednik se dovede na graficki prikaz pa se onda upotrebi (mis - dovedemo kursor na poziciju pa onda upravljamo; touchpad)
- Manje gresaka jer je precizniji (lakse misom pogoditi nesto na ekranu nego jagodicom prsta na touch screen ekranu)
- Mis moze duze da se koristi bez umora ruke (nego touch screen ekran)

##### Svetlosno pero
- Prvi pointerski uredjaj direktne kontrole
- Problem drzanja ruke u istoj poziciji duze vremena
- Kada drzimo ruku duze na istom mestu ona krene da pada pa ono gde pokazujemo krene da "driftuje" ka dole - resenje je bilo dugme koje kada pritisnemo (hold dugme) ostaje pointer na istoj tacki
- Land On tehnika - pogadjam onu tacku na koju spustim ruku - medjutim tesko je pogoditi tacku koju zelimo na ovaj nacin
- Lift Off tehnika - tek kada podignemo ruku onda se selektuje, a ne prilikom pritiska - pomaze pri korekciji problema iznad

##### Ekrani osetljivi na dodir
- Nema vise drzanja pera
- Rezistivni touch senzitivni ekrani - Sastavljeni od vise folija izmedju kojih se nalazi "zele" koji je providan. Kada se pritisne, malo se deformise i menja svoju otpornost i tako se odrazava dodir. Danas se ne koriste
- Danasnji ekrani su zasnovani na kapacitivnim ekranima - Dovoljno je samo da dodirnemo, ne moramo da pritiskamo. Dielektrik izmedju folija je mali kondenzator kome se menja kapacitivnost prilikom dodira pa se tako odrazava dodir
- Lakse je napraviti providne kondenzatore nego providne otpornike. Vise struje treba kod rezistivnog zbog potrosnje struje (povecamo osvetljenost da bi bolje videli providnost)
- Minus kod kapacitivnog je sto npr ne mozemo rukavicama da koristimo jer rukavice ne provode nasu kapacitivnost - zato koristimo stajlus (Strahinjina olovka kao primer stajlusa)
- Bilo je ideja i sa akusticnom implementacijom gde imamo zvucnike pa kada dodirnemo ekran onda prekinemo zvucnike pa se tako odrazi dodir. Problem je buka iz okoline koja moze da smeta
- Rezistivni ekrani su otporniji na hemikalije (npr kod automehanicara, negde napolju...; otproniji su na udarac i jako pritiskanje)
- Mogu reagovati na vise dodira u isto vreme (multi-touch)

### Pointerski uredjaji direktne kontrole 
- Direktno poentiram na ekran bez posrednika (touch screen ekran)
- Intuitivnije za ljude koji su manje upoznati sa tehnologijom
- Mana je sto recimo na touch screen ekranu kada pritiskamo, pokrivamo rukom deo ekrana pa ne vidimo ceo ekran
- Slobodni pokret (crtanje) je dosta laksi kod direktnih (graficka tabla je jedini indirektni uredjaj kod kog je slobodan pokret prirodan)

##### Mis
- Prvo su dolazili sa kuglicom - problem je bio sto udje prasina kod kuglice, tesko je da se izvadi i ocisti
- Pa su posle dosli laserski - problem je sto je neophodna dobra podloga (npr nece raditi na staklu)
- Danas imamo opticke
- Prvo su dolazili sa po 1, 2 i 3 tastera; danas imamo i sa dosta vise tastera; mozemo namestati i tegove u misu da kontrolisemo senzitivnost prilikom kretanja

##### Trackball
- Veca lopta, manje naporno od misa
- Zauzima dosta manje radne povrsine
- Problem je sto opet moze uci prasina i prljavstina unutra
- Moze se lako integrisati u tastaturu/laptop

##### Joystick
- Uzet iz vojske; u obliku palice sa tasterima
- Joypad za konzole i igrice

##### Trackpoint
- Ono crveno malo na thinkpadu (kriminalno beskorisno)
- Mali je, staje izmedju tastera, integrisan na tastaturu
- Mana je sto je poprilicno osetljiv
- Taktilni trackpoint - mozemo osetiti kako kursor prelazi preko nekih povrsina usled iglica koje se nalaze unutar trackpointa; mana je mali zivotni vek i jako je skup

##### Graficka tabla
- Elektronska, akusticna ili kontaktna tabla (ova poslednja vise uopste nije u upotrebi)

##### Touchpad
- Kapacitivni

## Cika Fic
- HCI prica
- Sproveo istrazivanje o motorici i mentalnoj snazi pri kontrolisanju pokreta
- Slike ispod ako nekog zanima
![Fitts](img/fitts-1.png)
- Ideja je da se pomocu parametara poboljsava kontrola i produktivnost kod koriscenja pointerskog uredjaja
- U sustini, kada na misu stavimo tegove, mi podesavamo ove parametre iznad i prilagodjavamo da nama bude sto bolje
- Dzojstik vs Mis
![Fitts](img/fitts-2.png)
- Na osnovu Ficovog zakona je predlozen pie meni koji je dosta efikasniji od danasnjeg pravougaonog menija sa opcijama (brzi)
![Pie menu](img/pie-menu.png)