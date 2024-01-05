# Predavanje 3

### Rasterska grafika
- Scan line - redovi piksela; piksel po piksel se gleda koje boje bi trebalo da se upali (ili da se ne upali uopste)

### Vektorska grafika
- Ne prikazuje tackicu po tackicu (kao rasterska), nego citave krive

### Koja je bolja?
- Rasterski je preovladao iako je vektorski stariji
- Rasterski sistem lakse i bolje prikazuje fotografije (zna da oboji)
- Vektorski prikaz moze kvalitetnije da prikaze oblike (onaj trougao sa predavanja), ali mu je dosta teze da boji (sporo)

### Osnovne karakteristike rasterskog hardvera
- Rezolucija - broj redova i kolona (piksela)
- Gustina - broj piksela po inch-u
- Velicina monitora
- Broj boja
- Brzina osvezavanja - broj frejmova po sekundi koji moze da se prikaze

### Osnovne karakteristike vektorskog hardvera
- Broj vektora koje moze da iscrta (ekvivalentno rezoluciji)
- Broj boja (note: puno vektora mu treba da bi obojio nesto - crta sve manje i manje vektore dok ne oboji pocetni; zato su ranije samo srafirali vektore umesto bojenja)

### Softverske karatkeristike
- Na nivou instrukcija; instrukciono-logicki (piksel po piksel - rasterski; linija po linija - vektorski)
    - **Pitanje za usmeni**: Sedi za laptopom i koristi neki rasterski ili vektorski softver. Kako bi zakljucili na osnovu posmatranja kakav softver koristi? - Za vektorski ce vise misa da koristi (drag and drop) za prevlacenje/crtanje linija. Za rasterski bi bilo "klik klik klik ko ludak" (lol)
    - Primer za rasterski softver na nivou instrukcija - PhotoShop, Paint
    - Primer za vektorski softver na nivou instrukcija - AutoCAD, Illustrator
- Na nivou podataka - gleda se kako se opis tog grafickog prikaza cuva; zapis na nivou piksela - softver je rasterski na nivou podataka; inace vektorski
    - Rasterski - svaki piksel opisan u fajlu. Npr jpg, png, tiff, bmp...
    - Vektorski - svaki vektor opisan (npr xmlom sa predavanja). Npr svg
    - Vektorski ce zauzeti manje prostora (jer se cuva opis vektora, a ne informacije svakog piksela na slici)
    - Ako je neki softver na instrukcijskom nivou rasterski, onda on na nivou podataka (mora/moze) biti (rasterski/vektorski) - Pitanje na testu. Mora biti rasterski
    - Onaj koji je na ulazu vektorski, moze biti i jedno i drugo na izlazu (vektorski opis se da rasterizovati)
    - *.wmf - Windows Meta File - Moze cuvati i rasterski i vektorski sadrzaj u sebi. Mora imati oznaku pocetka i kraja razlicitih sekcija (raster begin i end ili vektorski begin i end). Mora se zapisati tako da graficki podsistem operativnog sistema - prikazace ga na najbolji/najbrzi moguci nacin (jer je nativan; jer je samo za taj operativni sistem). Primer: novine - slova su skupovi vektora (true type fontovi), a slike su rasterskog oblika. Mana je sto je vezan za operativni sistem

### Hardverske karatkeristike
- Rasterski i vektorski hardver (rasterski preovladjuje)
- Postoje dva "koloseka":
    - Treba mi grafika ali ne tako mocna (kasa u prodavnici)
    - Treba mi ozbiljna grafika (projektovanje, animiranje...)
- Rasterski hardver:
    - bez GPU (deljena ili izolovana memorija) - za manje zahtevne korisnike (jer zasto bi placao za nesto sto mu ne treba)
    - sa GPU (deljena ili izolovana memorija) - animacije, modelovanje...
    - GPU mora uz CPU! CPU-u moze i bez GPU
    - Vektorski zapis je nativan za vektorski hardver dok je rasterski zapis nativan za rasterski hardver

### Hardverska arhitektura - bez GPU
- Video kontroler cita iz frame buffera, dograbi sve pa polako crta na ekran
- Sa deljenom memorijom - frame buffer je u RAM-u, a inace je u VRAM-u
- Nema smisla VRAM jer nemamo GPU - logicki moguce da imamo VRAM bez GPU, al prakticno nemoguce jer nema ko da joj pristupa
- Proces
    - Sa perifernih uredjaja dodje kod
    - Taj kod CPU dostavi u RAM
    - CPU uzme iz RAM-a i cita kod i procesira
    - Nakon rasterizacije ga salje u frame buffer (tj RAM jer je deljena memorija)
    - Video kontroler uzima iz frame buffera i crta na ekran

### Hardverska arhitektura - sa GPU
- Najzastupljeniji oblik (logicno)
- Razlikujemo GPU bez VRAM-a i GPU sa VRAM-om
- Proces
    - Sa perifernih uredjaja ode kod u RAM
    - GPU pita CPU da pristupi RAM-u
    - GPU prebaci iz RAM-a kod sebe u VRAM
    - GPU krene da radi i da rasterizuje frame-ove koje stavlja u frame-buffer
    - Video kontroler uzima iz frame buffer-a i prikazuje frame po frame na ekran

### Video kontroler klasicne arhitekture
- Kontroler cita RGB za svaki piksel 
- Kontroler konvertuje digitalni RGB signal u analogni signal za monitor
- Memorije se citaju s leva na desno, odozgo na dole (da bi bilo lakse kontroleru i monitoru da komuniciraju)
- Sken kontroler video kontrolera - ima increment (adresa sledece lokacije) i reset

### Video kontroler LUT arhitekture
- LUT - Look Up Table
- Sken kontroler i dalje postoji
- LUT tablea - cuva paletu boja koje se zaista nalaze na slici
- U frame buffer-u se cuva samo indeks boje iz LUT tabele
- Tabela se generise ponovo za svaki frejm samo ako ima razlike u boji
- Usteda u memoriji je fantasticna. To smo platili brzinom (mora se proci kroz celu sliku i izdvojiti paletu boja za LUT)
- Ali postoje graficki formati koji imaju to u sebi zapisano (imaju tabelu boja) - gif
- Svakako postoji jedan korak vise od klasicne arhitekture