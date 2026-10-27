# Kościół pw. Wniebowzięcia NMP w Żukowie — Prezentacja Multimedialna

Interaktywna, nowoczesna prezentacja slajdowa (w stylu Apple Keynote / Pitch.com) poświęcona zabytkowemu kościołowi pw. Wniebowzięcia Najświętszej Maryi Panny w Żukowie (powiat kartuski, Kaszuby).

Projekt jest w pełni samowystarczalny, nie wymaga żadnego procesu budowania (zero build steps) i jest przystosowany do natychmiastowego hostingu na Cloudflare Pages / Cloudflare Workers przy użyciu narzędzia Wrangler.

## Struktura projektu

```text
.
├── public/
│   ├── index.html       # Główna prezentacja (HTML5, CSS, JS)
│   └── assets/          # Zoptymalizowane lokalne zasoby graficzne
├── wrangler.toml        # Konfiguracja Cloudflare Workers / Static Assets
├── LICENSE              # Licencja MIT
└── README.md            # Dokumentacja projektu
```

## Slajdy w prezentacji

1. **Położenie i Lokalizacja** – mapa z zaznaczonym kościołem w Żukowie, dane administracyjne i geograficzne.
2. **Historia** – dzieje norbertanek od XIV wieku, fundacja książęca, kasata pruska w 1834 r. oraz ocalałe obiekty.
3. **Architektura** – gotycka bryła z cegły, wyniki badań archeologicznych z 1999 r., wymiary (38 m × 9 m × 14 m) i sklepienia.
4. **Wyposażenie** – XVII-wieczny ołtarz główny Hermana Hana, ołtarze boczne, tryptyk antwerpski, empora z 1766 r., dzwony i organy.

## Źródła materiałów i fotografii

Wszystkie fotografie zostały zoptymalizowane i umieszczone lokalnie w katalogu `public/assets/`, dzięki czemu strona nie wykonuje zewnętrznych zapytań o multimedia.

| Slajd | Plik lokalny | Opis | Źródło / Licencja |
| :--- | :--- | :--- | :--- |
| **Slajd 1** | `assets/slide1_map.jpg` | Mapa gminy Żukowo z oznaczonym kościołem | Opracowanie własne na bazie mapy lokalizacyjnej [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:%C5%BBukowo_location_map.svg) (OpenStreetMap / CC BY-SA 3.0) |
| **Slajd 2** | `assets/slide2_klasztor.jpg` | Panorama zespołu poklasztornego w Żukowie | Oficjalny portal turystyczny [Szwajcaria Kaszubska](https://szwajcariakaszubska.com/media/photos/1414/original.jpg) |
| **Slajd 3** | `assets/slide3_kosciol.jpg` | Gotycka ceglana bryła kościoła w Żukowie | [Wikimedia Commons: File:Zukowo1.jpg](https://commons.wikimedia.org/wiki/File:Zukowo1.jpg), autor: *Cezary p* (CC BY-SA 3.0) |
| **Slajd 4** | `assets/slide4_oltarz.jpg` | Wczesnobarokowy ołtarz główny Hermana Hana | [Wikimedia Commons: File:Zukowo Kosciol Norbertanow oltarz glowny.jpg](https://commons.wikimedia.org/wiki/File:Zukowo_Kosciol_Norbertanow_oltarz_glowny.jpg), autor: *Przykuta* (CC BY-SA 4.0) |

### Źródła tekstowe
Treści merytoryczne dotyczące historii, architektury i wyposażenia opracowano na podstawie artykułu w [Wikipedii: Kościół Wniebowzięcia Najświętszej Marii Panny w Żukowie](https://pl.wikipedia.org/wiki/Ko%C5%9Bci%C3%B3%C5%82_Wniebowzi%C4%99cia_Naj%C5%9Bwi%C4%99tszej_Marii_Panny_w_%C5%BBukowie) (udostępnianego na licencji CC BY-SA 4.0).

## Funkcje i sterowanie

- **Nawigacja klawiaturą**:
  - `Strzałka w prawo` / `Spacja`: Następny slajd
  - `Strzałka w lewo`: Poprzedni slajd
  - `1` – `4`: Bezpośredni skok do danego slajdu
  - `F`: Tryb pełnoekranowy (Fullscreen)
  - `P`: Włącz / wyłącz automatyczne odtwarzanie (Autoplay)
  - `?` / `H`: Okno pomocy ze skrótami
- **Nawigacja dotykowa**: obsługa gestów przesunięcia (swipe) na urządzeniach mobilnych.
- **Płynne animacje**: sprzętowo akcelerowane przejścia slajdów i kaskadowe pojawianie się elementów.

## Uruchomienie lokalne

```bash
# Uruchomienie lokalnego serwera HTTP (np. Python):
cd public
python3 -m http.server 3000
```

Prezentacja będzie dostępna pod adresem: `http://localhost:3000`

## Wdrożenie (Cloudflare)

Projekt konfiguruje plik `wrangler.toml` do hostowania zasobów statycznych z folderu `./public`:

```bash
npx wrangler deploy
```

## Licencja

Projekt udostępniany na warunkach licencji [MIT](LICENSE).
