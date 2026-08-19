# 📚 Jurnalul Meu de Lectură

**Jurnalul Meu de Lectură** este o aplicație web dezvoltată în **Flask**, destinată gestionării cărților citite și a cărților planificate pentru citit (**TBR – To Be Read**).

Aplicația permite organizarea bibliotecii personale, urmărirea progresului de lectură, vizualizarea statisticilor și păstrarea unui jurnal automat al acțiunilor utilizatorului.

## ✨ Funcționalități principale

- 🔐 Autentificare cu sesiune pentru administrator
- ➕ Adăugare, editare și ștergere cărți
- 🔎 Căutare și filtrare a cărților
- 📚 Filtrarea cărților după gen (raft)
- 📅 Căutarea cărților citite într-un anumit interval de timp
- 📖 Gestionarea listei TBR (*To Be Read*)
- 🔄 Mutarea cărților din lista TBR în lista cărților citite
- 📝 Jurnal automat al acțiunilor utilizatorului

### 📊 Statistici

Aplicația oferă mai multe statistici și reprezentări grafice:

- ⭐ Rating mediu general
- ✍️ Rating mediu în funcție de autor
- 📚 Rating mediu în funcție de gen
- 📈 Histogramă cu numărul de cărți citite pe lună
- 📄 Histogramă cu numărul de pagini citite pe lună
- 📅 Diagramă privind anul publicării cărților citite
- 📖 Numărul de cărți citite într-un anumit interval
- 📄 Numărul de pagini citite într-un anumit interval

## 🛠️ Tehnologii utilizate

- **Python** – limbajul principal
- **Flask** – framework web
- **SQLite3** – bază de date locală
- **Pandas** – procesare și analiză a datelor
- **Plotly** – generarea graficelor interactive
- **HTML/CSS** – structurarea și stilizarea interfeței
- **Jinja2** – generarea dinamică a paginilor HTML
- **Bootstrap** – layout responsive și stilizare

## 🗂️ Structura aplicației – rute Flask

| Rută | Metode | Descriere |
|---|---|---|
| `/` | GET | Pagina principală cu listarea cărților |
| `/login` | GET, POST | Autentificare utilizator (admin) |
| `/logout` | GET | Delogare |
| `/adaugare_carte` | GET, POST | Adăugare carte în bibliotecă |
| `/editare_carte/<int:id>` | GET, POST | Editarea unei cărți existente |
| `/stergere_carte` | GET, POST | Ștergerea unei cărți |
| `/filtru_raft` | GET, POST | Filtrarea cărților după gen |
| `/listare_carti` | GET | Listarea tuturor cărților cu informații complete |
| `/avg_rating` | GET | Afișarea ratingului mediu general |
| `/avg_rating_raft` | GET, POST | Afișarea ratingului mediu pentru un gen |
| `/avg_rating_autor` | GET, POST | Afișarea ratingului mediu pentru un autor |
| `/pagini_luna` | GET | Afișarea numărului de pagini citite într-un interval |
| `/carti_luna` | GET | Afișarea numărului de cărți citite într-un interval |
| `/histograma_carti_luna` | GET | Histogramă cu numărul de cărți citite pe lună (2025) |
| `/histograma_pagini_luna` | GET | Histogramă cu numărul total de pagini citite pe lună |
| `/histograma_anul_publicarii` | GET | Diagramă privind anii de publicare ai cărților citite |
| `/anul_publicarii` | GET, POST | Setarea sau actualizarea anului de publicare al unei cărți |
| `/jurnal` | GET | Vizualizarea jurnalului acțiunilor utilizatorului |
| `/adaugare_carte_planificata` | GET, POST | Adăugarea unei cărți în lista TBR |
| `/listare_carti_tbr` | GET | Listarea cărților planificate pentru citit (TBR) |
| `/din_tbr_in_citita/<id>` | GET, POST | Mutarea unei cărți din TBR în lista cărților citite |

## 🚀 Instalare și rulare

### 1. Clonarea repository-ului

Clonează repository-ul și navighează în directorul proiectului:

```bash
git clone https://github.com/USERNAME/jurnalul-meu-de-lectura.git
cd jurnalul-meu-de-lectura
```

### 2. Instalarea dependențelor

Instalează pachetele necesare folosind `pip`:

```bash
pip install Flask pandas plotly
```

### 3. Pornirea aplicației

Rulează aplicația Flask:

```bash
python app.py
```

După pornire, aplicația poate fi accesată în browser la:

```text
http://127.0.0.1:5000/
```

## 🔐 Autentificare

Aplicația utilizează o autentificare simplă, bazată pe sesiune, fără o bază de date separată pentru utilizatori.

Datele de autentificare implicite sunt:

- **Username:** `admin`
- **Parolă:** `parola123`

> ⚠️ Aceste date sunt utilizate pentru rularea locală a proiectului și nu sunt recomandate pentru o aplicație destinată producției.

## 🗄️ Baza de date

Aplicația utilizează **SQLite3** pentru stocarea datelor.

Pentru adăugarea coloanei `anul_publicarii` în tabela `biblioteca`, a fost utilizată aplicația **DB Browser for SQLite** și următoarea comandă SQL:

```sql
ALTER TABLE biblioteca ADD COLUMN anul_publicarii INTEGER;
```

## 📌 Observații

- Aplicația este destinată rulării locale.
- Baza de date utilizată este SQLite3.
- Graficele sunt generate folosind Plotly.
- Analiza datelor este realizată cu Pandas.
- Interfața este auto-generată, construită folosind HTML, CSS, Jinja2 și Bootstrap.

## 👤 Autor

**Vlaiconi Daniel-Alexandru**

Proiect realizat folosind:

**Python · Flask · SQLite3 · Pandas · Plotly · HTML/CSS · Jinja2 · Bootstrap**


