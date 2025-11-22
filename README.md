# 🤖 SuperSport Betting Automation

Ovaj projekt je set Python skripti dizajniran za automatizaciju procesa prikupljanja tečajeva, analize ponude i automatskog popunjavanja listića na SuperSport web stranici.

Sustav radi u 4 koraka:
1. **Scraping:** Prikuplja svježu ponudu nogometa.
2. **Analiza:** (Opcionalno) Prikazuje statističke sisteme (favoriti, lov na X, value betovi).
3. **Filtriranje:** Odabire "zicere" prema zadanim rasponima kvota.
4. **Automatizacija:** Otvara preglednik i automatski klika odabrane parove na listić.

---

## 🛠️ Instalacija

### 1. Preduvjeti
* Python 3.x instaliran na računalu.
* Google Chrome (ili Chromium) preglednik.

### 2. Instalacija biblioteka
Kreiraj datoteku `requirements.txt` sa sadržajem ispod ili pokreni instalaciju direktno.

**Sadržaj `requirements.txt`:**
```text
pandas
playwright
beautifulsoup4
openpyxl
Naredba za instalaciju:

Bash

pip install -r requirements.txt
3. Instalacija Playwright preglednika
Nakon instalacije biblioteka, potrebno je preuzeti upravljačke programe za preglednik:

Bash

playwright install
🚀 Kako koristiti (Workflow)
Projekt je zamišljen da se skripte pokreću redom (numerirane su od 1 do 4).

Korak 1: Prikupljanje podataka
Pokreni scraper koji će otvoriti preglednik, skrolati ponudu i spremiti podatke u Excel.

Bash

python "1. scraper.py"
Izlaz: Kreira se datoteka supersport_ponuda.xlsx.

Korak 2: Brza analiza (Opcionalno)
Ako želiš vidjeti potencijalne sisteme prije igranja:

Bash

python "2. analiza.py"
Ispisuje tri kategorije (Sigurice, Lov na X, Value betovi) u konzolu.

Korak 3: Generiranje liste za bota
Ova skripta filtrira ponudu prema tvojim kriterijima i priprema datoteku koju bot čita.

Bash

python "3 .ziceri_exp.py"
⚙️ KONFIGURACIJA: Otvori ovu skriptu u editoru i na vrhu datoteke promijeni varijable ako želiš drugačiji raspon kvota:

Python

MIN_KVOTA = 1.10  # Donja granica
MAX_KVOTA = 1.45  # Gornja granica
Izlaz: Kreira se datoteka za_bot_igranje.xlsx.

Korak 4: Automatsko popunjavanje listića
Bot otvara SuperSport, traži parove iz generirane liste i dodaje ih na listić.

Bash

python "4. auto_listic.py"
⚙️ KONFIGURACIJA: Ako želiš promijeniti broj parova koji se stavljaju na listić, pronađi liniju koda unutar funkcije napuni_listic_sistem():

Python

# Uzmi prvih 15 parova (promijeni broj 15 u željeni broj)
parovi = df.head(15)
⚠️ Napomene i Odricanje od odgovornosti
Vremenski razmak: Scraper koristi time.sleep kako bi osigurao učitavanje stranice. Ako imate sporiji internet, možda ćete morati povećati te vrijednosti.

Odgovorno klađenje: Ovaj softver služi isključivo u edukativne svrhe za demonstraciju web automatizacije. Autor ne odgovara za gubitke nastale korištenjem ovih skripti. Kladite se odgovorno.
