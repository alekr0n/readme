# Find Your Cocktail!
Aplikacja wieloplatformowa do wyszukiwania, dodawania i generowania koktajli, a także przechowywania historii z nimi związanych. Aplikacja stworzona dla profesjonalnych barmanów i miłośników, aby ułatwić wyszukiwanie pomysłów na nowe koktajle oraz zapisywanie własnych przepisów. Ponadto, w przyszłości ta aplikacja może stać się nową siecią społecznościową podobną do Instagramu, gdzie każdy będzie mógł wspominać swoje imprezy i dowiedzieć się, jak bawią się inni.

Status: opracowywanie aktualizacji.

## Spis treści
- [Technologie](#technologie)
- [Architektura](#architektura)
- [Funkcji](#funkcji)
- [Używanie](#używanie)
- [Oczekiwane aktualizacje](#oczekiwane-aktualizacje)
- [Zespół deweloperów](#zespół-deweloperów)
- [FAQ](#faq)

## Technologie
- [Vue.js](https://vuejs.org/)
- [Node.js](https://nodejs.org/)
- [Express](https://expressjs.com/)
- [MongoDB](https://www.mongodb.com/)

## Architektura

Nasz projekt korzysta ze stosu MEVN (MongoDB, Express.js, Vue.js, Node.js).

### Część serwerowa (Backend)
- **Node.js**: Serwerowa platforma JavaScript.
- **Express.js**: Framework dla Node.js ułatwiający tworzenie aplikacji webowych i API.
- **Mongoose**: Biblioteka do modelowania danych dla MongoDB w Node.js.

### Część kliencka (Frontend)
- **Vue.js**: Framework JavaScript do budowy interfejsów użytkownika.
- **Axios**: Biblioteka do wykonywania zapytań HTTP z przeglądarki.

### Komunikacja
- Frontend i backend komunikują się poprzez **REST API**, obsługując zapytania typu **GET, POST, PUT, DELETE**.

### Wdrożenie
- Projekt jest wdrożony na **Render.com**.
- Wykorzystuje pliki **.env** do zarządzania konfiguracją.

## Funkcji
- **Obejrzenie bazę z koktejlami.** Użytkownik może przejść na zakładkę "Base", aby zobaczyć listę przepisów wszystkich koktajli dostępnych w aplikacji.
- **Dodawanie własnych przepisów.** Użytkownik może dodać swój własny przepis na koktajl i nadać napojowi nazwę. Jest również możliwość wybrania ikony dla koktajlu spośród dostępnych w aplikacji. 
    
    Na przykład:
    > <h4>Enter cocktail name</h4>
    > <p>Ice Monster</p>
    > <h4>Enter cocktail ingredients</h4>
    > <p>-ice -gin -sugar -energies</p>
    > <p>(wybierz ikonę pod numerem)1-8</p>
    > <h4>(naciskni "Add")</h4>

- **Usuwanie przepisów.** Użytkownik może usuwać koktajle z listy bez możliwości ich przywrócenia, jednak u innych użytkowników wszystko pozostanie bez zmian. 
    
    Aby to zrobić, należy kliknąć krzyżyk w prawym górnym rogu karty koktajlu.

- **Wyszukiwanie koktajlu po nazwie.** W prawym górnym rogu znajduje się pole wyszukiwania, gdzie użytkownik może wpisać nazwę poszukiwanego koktajlu i zobaczyć na liście zamiast wielu kart, kartę wybranego koktajlu.

    Aby rozpocząć wyszukiwanie: wpisz nazwę poszukiwanego koktajlu i naciśnij przycisk "Find". Aby szybko zresetować wyszukiwanie i wrócić się do listy wszystkich koktajli, naciśnij "Reset".

- **Dodawanie koktajli do ulubionych.** Użytkownik może dodać koktajl do ulubionych. Przeglądać wszystkie ulubione napoje można, przechodząc do zakładki "Favourite". Ponadto w lewym górnym rogu karty koktajlu znajduje się serduszko – jeśli jest ono wypełnione na czerwono, koktajl jest w ulubionych, a jeśli serduszko nie jest wypełnione – koktajl nie znajduje się na liście ulubionych.

    <p>Aby dodać przepis do ulubionych, należy kliknąć na serduszko w lewym górnym rogu karty koktajlu. Jeśli serduszko jest wypełnione na czerwono – koktajl jest w ulubionych.</p>
    <p>Aby usunąć przepis z ulubionych, należy tak samo jak przy dodawaniu kliknąć na serduszko w lewym górnym rogu karty koktajlu. Jeśli serduszko nie jest wypełnione – koktajl nie jest w ulubionych.</p>

- **Zapis historii, związanych z koktajlami, notatek, komentarzy lub poprawek w przepisie.** Użytkownik może dodać swoje historie, komentarze, notatki lub poprawki do określonego koktajlu. Ważnym warunkiem dodania zapisu jest dodanie koktajlu do ulubionych. Komentarze można zostawiać tylko do ulubionych przepisów. Przechodząc do zakładki "Favourite" użytkownik zobaczy rozszerzoną wersję kart koktajli. W dolnej części każdej karty na stronie "Favourite" znajduje się pole do zapisu historii, komentarza, notatka lub poprawki.

    Na przykład:
    > To ulubiony koktajl Anny

    <p>Aby zapisać wpis, należy kliknąć przycisk "Add" na karcie koktajlu.</p>
    <p>Aby usunąć wpis, należy kliknąć przycisk "Delete" na karcie koktajlu.</p>
    <p>Aby edytować wpis: popraw wpis w polu tekstowym, a następnie kliknij przycisk "Add". (Ważne jest, aby pamiętać, że można pozostawić tylko jedą notatkę, historię, komentarz lub poprawkę, jednak zawsze można uzupełnić poprzedni wpis).</p>

- **Obejrzenie historii, notatek, komentarzy lub poprawek w przepisie.** Użytkownik może przeglądać wcześniej zapisane historie, komentarze, notatki, poprawki. Można to zrobić w zakładce "Favourite" i w razie potrzeby edytować, a także w zakładce "Base".

    <p>Aby zobaczyć wpis w zakładce "Base", należy kliknąć na gwiazdkę w lewym dolnym rogu karty koktajlu. Wpis pojawi się przed zawartością strony w osobnym polu.</p>
    <p>Aby zamknąć pole z wpisem, należy kliknąć krzyżyk w prawym górnym rogu pola.</p>


- **Automatyczne generowanie nowych koktajli.** Użytkownik może wygenerować napój z losowych składników. Funkcja ta została dodana w celu urozmaicenia swoich preferencji smakowych i możliwego ich rozszerzenia. Funkcja generuje najbardziej odpowiednią nazwę, najbardziej odpowiednią ikonę oraz dobiera składniki tak, aby powstał nowy napój. Generowanie koktajli można przeprowadzić w zakładce "Generator".

    <p>Aby wygenerować nowy koktajl, należy w zakładce "Generator" kliknąć przycisk "Generate" znajdujący się pod kartą z generowanym koktajlem.</p>
    <p>Po wygenerowaniu można wygenerować kolejny nowy koktajl.</p>
    <p>Aby dodać wygenerowany koktajl do ogólnej bazy, należy kliknąć przycisk "Add to Base" na karcie z przepisem.</p>

<p>Aplikacja jest dość intuicyjna, jednak dla większej łatwości użytkowania dodaliśmy małe wskazówki wewnątrz aplikacji. Pracujemy również nad tym, aby dodać ich jeszcze więcej, dla maksymalnej wygody korzystania z Find Your Cocktail!</p>

## Używanie

Naciskni na ten link [Find Your Cocktail](https://find-your-cocktail-2.onrender.com/)

<p>lub</p>

<p>Wpis do przeglądarki https://find-your-cocktail-2.onrender.com/ i zobać naszą aplikację Find Your Cocktail!</p>

## Oczekiwane aktualizacje
- [x] Generator
- [ ] Dodawanie zdjęć do historii
- [ ] Generowanie koktajli z wykorzystaniem konkretnego składnika
- [ ] Rozszerzenie bazy koktajli
- [ ] Interakcje z innymi użytkownikami
- [ ] ...

## Zespół deweloperów
- **[Vadym Foteniuk](https://github.com/vxdosick)** — Head Lead, Front-End Engineer, Data Base Engineer
- **[Mikhail Ramanchyk](https://github.com/alekr0n)** — Back-End Engineer, Documientation & Presentation

## FAQ 
...
