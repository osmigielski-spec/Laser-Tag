# Automatyzacja faktur serwisu LaserWar - Instrukcja dla początkujących

**Czas wdrożenia:** 2-3 godziny (w spokojnym tempie)
**Koszt:** 0 zł
**Wymagana wiedza techniczna:** Żadna - wszystko jest opisane krok po kroku

---

## Co będziemy robić?

Stworzymy system z **DWOMA oddzielnymi arkuszami**:

| Arkusz | Kto ma dostęp | Co zawiera |
|--------|---------------|------------|
| **Arkusz Serwisanta** | Paweł (serwisant) | Tylko dane o naprawach i koszty Pawła |
| **Arkusz Właściciela** | Tylko Ty | Marże, ceny dla klientów, zestawienia do faktur |

**Dlaczego tak?**
- Paweł nie widzi Twoich marż ani cen dla klientów
- Paweł nie ma dostępu do zestawień fakturowych
- Ty masz pełną kontrolę nad danymi finansowymi

**Jak to działa:**
1. Paweł wpisuje do swojego arkusza: co naprawił, dla kogo, ile go to kosztowało
2. Ty klikasz jeden przycisk w swoim arkuszu
3. Dane się **automatycznie importują** z arkusza Pawła do Twojego
4. System **automatycznie liczy marże** i generuje zestawienie do faktur

---

# ETAP 1: Tworzenie arkusza dla serwisanta (Pawła)

## Krok 1.1: Utwórz nowy arkusz Google Sheets

1. Otwórz przeglądarkę (Chrome, Firefox, Safari - cokolwiek)
2. Wejdź na stronę: **sheets.google.com**
3. Zaloguj się na swoje konto Google (to samo co do Gmaila)
4. Kliknij duży przycisk **"+"** (Pusty arkusz) lub **"Blank spreadsheet"**
5. Arkusz się otworzy. U góry zobaczysz napis "Untitled spreadsheet" - **kliknij na niego**
6. Wpisz nazwę: **"Serwis LaserWar - SERWISANT"**
7. Naciśnij Enter

---

## Krok 1.2: Stwórz nagłówki kolumn dla serwisanta

Kliknij w komórkę **A1** i wpisuj po kolei (przechodząc klawiszem Tab):

| Komórka | Co wpisać |
|---------|-----------|
| A1 | `Data` |
| B1 | `Klient` |
| C1 | `Opis naprawy` |
| D1 | `Koszt robocizny` |
| E1 | `Koszt części` |
| F1 | `Uwagi` |

**Jak to zrobić:**
1. Kliknij w komórkę A1
2. Wpisz "Data"
3. Naciśnij klawisz **Tab** na klawiaturze (ten z dwiema strzałkami, nad Caps Lock)
4. Kursor przeskoczy do B1
5. Wpisz "Klient"
6. Naciśnij Tab
7. I tak dalej...

---

## Krok 1.3: Pogrub nagłówki

1. Kliknij w komórkę **A1**
2. Trzymając wciśnięty przycisk myszy, przeciągnij do komórki **F1**
3. Cały wiersz powinien być podświetlony na niebiesko
4. Na górze strony znajdź przycisk **B** (pogrubienie)
5. Kliknij go

---

## Krok 1.4: Zamroź pierwszy wiersz

1. W menu u góry kliknij **"Widok"** (albo **"View"**)
2. Najedź na **"Zablokuj"** (albo **"Freeze"**)
3. Kliknij **"1 wiersz"** (albo **"1 row"**)

---

## Krok 1.5: Dodaj przykładowe dane (do testów)

Wpisz kilka przykładowych napraw:

**Wiersz 2:**
- A2: `2025-01-15`
- B2: `ABC Laser Park Warszawa`
- C2: `Wymiana optyki w karabinie AK-12`
- D2: `150`
- E2: `80`
- F2: (możesz zostawić puste)

**Wiersz 3:**
- A3: `2025-01-15`
- B3: `ABC Laser Park Warszawa`
- C3: `Czyszczenie i kalibracja 5 szt.`
- D3: `200`
- E3: `0`

**Wiersz 4:**
- A4: `2025-01-16`
- B4: `Fun Arena Poznań`
- C4: `Wymiana akumulatora`
- D4: `50`
- E4: `120`

---

## Krok 1.6: Skopiuj link do arkusza (WAŻNE!)

Ten link będzie potrzebny do połączenia z Twoim arkuszem.

1. Popatrz na **pasek adresu** w przeglądarce (tam gdzie jest https://...)
2. Zobaczysz coś takiego:
   ```
   https://docs.google.com/spreadsheets/d/1AbCdEfGhIjKlMnOpQrStUvWxYz/edit
   ```
3. Skopiuj **ŚRODKOWĄ CZĘŚĆ** - ten długi ciąg znaków między `/d/` a `/edit`
   W przykładzie powyżej to: `1AbCdEfGhIjKlMnOpQrStUvWxYz`
4. **Zapisz to gdzieś** (w notatniku, na kartce) - będzie potrzebne za chwilę!

**Ten ciąg znaków to ID arkusza - będzie nam potrzebny w kroku 2.6**

---

## Krok 1.7: Udostępnij arkusz serwisantowi (Pawłowi)

1. Kliknij zielony przycisk **"Udostępnij"** (Share) w prawym górnym rogu
2. W polu "Dodaj osoby i grupy" wpisz **adres email Pawła**
3. Po prawej stronie od emaila kliknij na rozwijane menu i wybierz **"Edytujący"** (Editor)
4. Kliknij **"Wyślij"** (Send)

**Paweł dostanie email z linkiem do arkusza i będzie mógł go edytować.**

---

# ETAP 2: Tworzenie Twojego arkusza (właściciela)

## Krok 2.1: Utwórz DRUGI arkusz Google Sheets

1. Otwórz **nową kartę** w przeglądarce
2. Wejdź znowu na: **sheets.google.com**
3. Kliknij **"+"** (nowy arkusz)
4. Nazwij go: **"Serwis LaserWar - FAKTURY (poufne)"**

**WAŻNE: Tego arkusza NIE udostępniaj nikomu!**

---

## Krok 2.2: Stwórz nagłówki kolumn

Kliknij w komórkę **A1** i wpisuj po kolei:

| Komórka | Co wpisać |
|---------|-----------|
| A1 | `Data` |
| B1 | `Klient` |
| C1 | `Opis naprawy` |
| D1 | `Koszt robocizny (Paweł)` |
| E1 | `Koszt części (Paweł)` |
| F1 | `Cena robocizny (klient)` |
| G1 | `Cena części (klient)` |
| H1 | `SUMA dla klienta` |
| I1 | `Status` |
| J1 | `Uwagi` |

---

## Krok 2.3: Pogrub nagłówki

1. Zaznacz komórki od A1 do J1
2. Kliknij przycisk **B** (pogrubienie)

---

## Krok 2.4: Zamroź pierwszy wiersz

1. Menu: **Widok → Zablokuj → 1 wiersz**

---

## Krok 2.5: Otwórz edytor skryptów

1. W menu u góry kliknij **"Rozszerzenia"** (Extensions)
2. Kliknij **"Apps Script"**

Otworzy się nowa karta z edytorem kodu.

---

## Krok 2.6: Wklej kod skryptu

1. **Zaznacz CAŁY tekst** który tam jest (Ctrl+A / Cmd+A)
2. **Usuń go** (Delete)
3. **Skopiuj poniższy kod** i wklej:

```javascript
// ============================================
// AUTOMATYZACJA FAKTUR SERWISU LASERWAR
// Wersja 2.0 - Dwa arkusze (serwisant + właściciel)
// ============================================

// =============================================
// >>> KONFIGURACJA - UZUPEŁNIJ SWOJE DANE <<<
// =============================================

// ID arkusza serwisanta (ten długi ciąg znaków z linku)
// Znajdziesz go w adresie arkusza: https://docs.google.com/spreadsheets/d/TUTAJ_JEST_ID/edit
const ID_ARKUSZA_SERWISANTA = 'WKLEJ_TUTAJ_ID_ARKUSZA_SERWISANTA';

// Twoje marże (w procentach)
const MARZA_ROBOCIZNA = 40;  // 40% marży na robociznę
const MARZA_CZESCI = 30;     // 30% marży na części

// =============================================
// >>> KONIEC KONFIGURACJI <<<
// =============================================


/**
 * Importuje dane z arkusza serwisanta do Twojego arkusza
 */
function importujZArkuszaSerwisanta() {
  // Sprawdź czy ID zostało uzupełnione
  if (ID_ARKUSZA_SERWISANTA === 'WKLEJ_TUTAJ_ID_ARKUSZA_SERWISANTA') {
    SpreadsheetApp.getUi().alert(
      'BŁĄD KONFIGURACJI!\n\n' +
      'Musisz wkleić ID arkusza serwisanta w kodzie.\n\n' +
      'Otwórz: Rozszerzenia → Apps Script\n' +
      'Znajdź linię z "WKLEJ_TUTAJ_ID_ARKUSZA_SERWISANTA"\n' +
      'Zamień na ID z linku arkusza Pawła.'
    );
    return;
  }

  try {
    // Otwórz arkusz serwisanta
    const arkuszSerwisanta = SpreadsheetApp.openById(ID_ARKUSZA_SERWISANTA);
    const daneSerwisanta = arkuszSerwisanta.getSheets()[0]; // Pierwszy arkusz

    // Otwórz Twój arkusz (właściciela)
    const mojArkusz = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();

    // Pobierz dane z arkusza serwisanta (od wiersza 2)
    const ostatniWierszSerwisanta = daneSerwisanta.getLastRow();

    if (ostatniWierszSerwisanta < 2) {
      SpreadsheetApp.getUi().alert('Arkusz serwisanta jest pusty (brak danych do importu).');
      return;
    }

    // Pobierz istniejące dane z Twojego arkusza (żeby nie duplikować)
    const ostatniWierszMoj = mojArkusz.getLastRow();
    const istniejaceDane = new Set();

    if (ostatniWierszMoj >= 2) {
      for (let i = 2; i <= ostatniWierszMoj; i++) {
        const klucz = mojArkusz.getRange(i, 1).getValue() + '|' +
                      mojArkusz.getRange(i, 2).getValue() + '|' +
                      mojArkusz.getRange(i, 3).getValue() + '|' +
                      mojArkusz.getRange(i, 4).getValue() + '|' +
                      mojArkusz.getRange(i, 5).getValue();
        istniejaceDane.add(klucz);
      }
    }

    // Importuj nowe dane
    let licznikNowych = 0;
    let nastepnyWiersz = Math.max(2, ostatniWierszMoj + 1);

    for (let i = 2; i <= ostatniWierszSerwisanta; i++) {
      const data = daneSerwisanta.getRange(i, 1).getValue();
      const klient = daneSerwisanta.getRange(i, 2).getValue();
      const opis = daneSerwisanta.getRange(i, 3).getValue();
      const kosztRobocizny = daneSerwisanta.getRange(i, 4).getValue();
      const kosztCzesci = daneSerwisanta.getRange(i, 5).getValue();
      const uwagi = daneSerwisanta.getRange(i, 6).getValue();

      // Pomiń puste wiersze
      if (!klient && !opis) continue;

      // Sprawdź czy już istnieje
      const klucz = data + '|' + klient + '|' + opis + '|' + kosztRobocizny + '|' + kosztCzesci;
      if (istniejaceDane.has(klucz)) continue;

      // Dodaj do Twojego arkusza
      mojArkusz.getRange(nastepnyWiersz, 1).setValue(data);
      mojArkusz.getRange(nastepnyWiersz, 2).setValue(klient);
      mojArkusz.getRange(nastepnyWiersz, 3).setValue(opis);
      mojArkusz.getRange(nastepnyWiersz, 4).setValue(kosztRobocizny);
      mojArkusz.getRange(nastepnyWiersz, 5).setValue(kosztCzesci);
      mojArkusz.getRange(nastepnyWiersz, 9).setValue('Do faktury');
      mojArkusz.getRange(nastepnyWiersz, 10).setValue(uwagi);

      nastepnyWiersz++;
      licznikNowych++;
    }

    if (licznikNowych > 0) {
      SpreadsheetApp.getUi().alert(
        'Import zakończony!\n\n' +
        'Zaimportowano ' + licznikNowych + ' nowych pozycji.\n\n' +
        'Teraz kliknij "2. Przelicz marże" aby obliczyć ceny dla klientów.'
      );
    } else {
      SpreadsheetApp.getUi().alert(
        'Brak nowych danych do importu.\n\n' +
        'Wszystkie pozycje z arkusza serwisanta są już w Twoim arkuszu.'
      );
    }

  } catch (error) {
    SpreadsheetApp.getUi().alert(
      'BŁĄD!\n\n' +
      'Nie udało się otworzyć arkusza serwisanta.\n\n' +
      'Sprawdź:\n' +
      '1. Czy ID arkusza jest poprawne\n' +
      '2. Czy masz dostęp do arkusza serwisanta\n\n' +
      'Szczegóły błędu: ' + error.message
    );
  }
}


/**
 * Przelicza koszty na ceny dla klienta (z marżą)
 */
function przeliczMarze() {
  const arkusz = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  const ostatniWiersz = arkusz.getLastRow();

  if (ostatniWiersz < 2) {
    SpreadsheetApp.getUi().alert('Brak danych do przeliczenia!\n\nNajpierw zaimportuj dane z arkusza serwisanta.');
    return;
  }

  let licznikPrzeliczonych = 0;

  for (let i = 2; i <= ostatniWiersz; i++) {
    const kosztRobocizny = arkusz.getRange(i, 4).getValue();
    const kosztCzesci = arkusz.getRange(i, 5).getValue();

    // Pomiń wiersze bez kosztów
    if (!kosztRobocizny && !kosztCzesci) continue;

    // Oblicz ceny dla klienta
    const cenaRobocizny = kosztRobocizny * (1 + MARZA_ROBOCIZNA / 100);
    const cenaCzesci = kosztCzesci * (1 + MARZA_CZESCI / 100);
    const suma = cenaRobocizny + cenaCzesci;

    // Wpisz obliczone wartości
    arkusz.getRange(i, 6).setValue(Math.round(cenaRobocizny * 100) / 100);
    arkusz.getRange(i, 7).setValue(Math.round(cenaCzesci * 100) / 100);
    arkusz.getRange(i, 8).setValue(Math.round(suma * 100) / 100);

    licznikPrzeliczonych++;
  }

  SpreadsheetApp.getUi().alert(
    'Gotowe!\n\n' +
    'Przeliczono marże dla ' + licznikPrzeliczonych + ' pozycji.\n\n' +
    'Marża na robociznę: ' + MARZA_ROBOCIZNA + '%\n' +
    'Marża na części: ' + MARZA_CZESCI + '%'
  );
}


/**
 * Generuje zestawienie do faktur (per klient)
 */
function generujZestawienie() {
  const arkusz = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  const ostatniWiersz = arkusz.getLastRow();

  if (ostatniWiersz < 2) {
    SpreadsheetApp.getUi().alert('Brak danych do zestawienia!');
    return;
  }

  // Zbierz dane per klient
  const klienci = {};

  for (let i = 2; i <= ostatniWiersz; i++) {
    const status = arkusz.getRange(i, 9).getValue();

    // Przetwarzaj tylko "Do faktury"
    if (status !== 'Do faktury') continue;

    const klient = arkusz.getRange(i, 2).getValue();
    const opisNaprawy = arkusz.getRange(i, 3).getValue();
    const suma = arkusz.getRange(i, 8).getValue();

    if (!klient) continue;

    if (!klienci[klient]) {
      klienci[klient] = {
        naprawy: [],
        suma: 0
      };
    }

    klienci[klient].naprawy.push({
      opis: opisNaprawy,
      kwota: suma || 0
    });
    klienci[klient].suma += (suma || 0);
  }

  // Sprawdź czy są dane
  if (Object.keys(klienci).length === 0) {
    SpreadsheetApp.getUi().alert(
      'Brak pozycji do zestawienia!\n\n' +
      'Upewnij się, że:\n' +
      '1. W kolumnie "Status" masz wpisane "Do faktury"\n' +
      '2. Kolumna "SUMA dla klienta" jest wypełniona (kliknij "Przelicz marże")'
    );
    return;
  }

  // Utwórz lub wyczyść arkusz "Zestawienie"
  let zestawienie = SpreadsheetApp.getActiveSpreadsheet().getSheetByName('ZESTAWIENIE DO FAKTUR');
  if (zestawienie) {
    zestawienie.clear();
  } else {
    zestawienie = SpreadsheetApp.getActiveSpreadsheet().insertSheet('ZESTAWIENIE DO FAKTUR');
  }

  // Nagłówek
  zestawienie.getRange(1, 1).setValue('ZESTAWIENIE DO FAKTUR - POUFNE');
  zestawienie.getRange(1, 1).setFontWeight('bold');
  zestawienie.getRange(1, 1).setFontSize(16);
  zestawienie.getRange(1, 1).setFontColor('#cc0000');

  zestawienie.getRange(2, 1).setValue('Wygenerowano: ' + new Date().toLocaleDateString('pl-PL') + ' ' + new Date().toLocaleTimeString('pl-PL'));
  zestawienie.getRange(3, 1).setValue('Marża robocizna: ' + MARZA_ROBOCIZNA + '% | Marża części: ' + MARZA_CZESCI + '%');

  let wiersz = 5;
  let sumaCalkowita = 0;

  // Dla każdego klienta
  for (const nazwaKlienta in klienci) {
    const daneKlienta = klienci[nazwaKlienta];

    // Nagłówek klienta
    zestawienie.getRange(wiersz, 1).setValue('KLIENT: ' + nazwaKlienta);
    zestawienie.getRange(wiersz, 1, 1, 3).setBackground('#1a73e8');
    zestawienie.getRange(wiersz, 1, 1, 3).setFontColor('#ffffff');
    zestawienie.getRange(wiersz, 1, 1, 3).setFontWeight('bold');
    wiersz++;

    // Nagłówki kolumn
    zestawienie.getRange(wiersz, 1).setValue('Lp.');
    zestawienie.getRange(wiersz, 2).setValue('Opis naprawy / usługi');
    zestawienie.getRange(wiersz, 3).setValue('Kwota netto (zł)');
    zestawienie.getRange(wiersz, 1, 1, 3).setFontStyle('italic');
    zestawienie.getRange(wiersz, 1, 1, 3).setBackground('#e8f0fe');
    wiersz++;

    // Lista napraw
    let lp = 1;
    for (const naprawa of daneKlienta.naprawy) {
      zestawienie.getRange(wiersz, 1).setValue(lp + '.');
      zestawienie.getRange(wiersz, 2).setValue(naprawa.opis);
      zestawienie.getRange(wiersz, 3).setValue(Math.round(naprawa.kwota * 100) / 100);
      wiersz++;
      lp++;
    }

    // Suma dla klienta
    zestawienie.getRange(wiersz, 1, 1, 2).setValue('SUMA DO FAKTURY:');
    zestawienie.getRange(wiersz, 3).setValue(Math.round(daneKlienta.suma * 100) / 100 + ' zł');
    zestawienie.getRange(wiersz, 1, 1, 3).setFontWeight('bold');
    zestawienie.getRange(wiersz, 1, 1, 3).setBackground('#fff2cc');

    sumaCalkowita += daneKlienta.suma;
    wiersz += 2;
  }

  // Suma całkowita
  wiersz++;
  zestawienie.getRange(wiersz, 1, 1, 2).setValue('SUMA WSZYSTKICH FAKTUR:');
  zestawienie.getRange(wiersz, 3).setValue(Math.round(sumaCalkowita * 100) / 100 + ' zł');
  zestawienie.getRange(wiersz, 1, 1, 3).setFontWeight('bold');
  zestawienie.getRange(wiersz, 1, 1, 3).setFontSize(12);
  zestawienie.getRange(wiersz, 1, 1, 3).setBackground('#d9ead3');

  // Dopasuj kolumny
  zestawienie.setColumnWidth(1, 50);
  zestawienie.setColumnWidth(2, 400);
  zestawienie.setColumnWidth(3, 120);

  SpreadsheetApp.getUi().alert(
    'Zestawienie wygenerowane!\n\n' +
    'Liczba klientów: ' + Object.keys(klienci).length + '\n' +
    'Suma do zafakturowania: ' + Math.round(sumaCalkowita * 100) / 100 + ' zł\n\n' +
    'Znajdziesz je w zakładce "ZESTAWIENIE DO FAKTUR" na dole arkusza.'
  );
}


/**
 * Oznacza pozycje jako zafakturowane
 */
function oznaczJakoZafakturowane() {
  const arkusz = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  const ostatniWiersz = arkusz.getLastRow();

  let licznik = 0;

  for (let i = 2; i <= ostatniWiersz; i++) {
    const status = arkusz.getRange(i, 9).getValue();

    if (status === 'Do faktury') {
      arkusz.getRange(i, 9).setValue('Zafakturowane');
      arkusz.getRange(i, 9).setBackground('#b7e1cd');
      licznik++;
    }
  }

  if (licznik > 0) {
    SpreadsheetApp.getUi().alert('Oznaczono ' + licznik + ' pozycji jako zafakturowane.');
  } else {
    SpreadsheetApp.getUi().alert('Brak pozycji do oznaczenia (nie znaleziono statusu "Do faktury").');
  }
}


/**
 * Dodaje menu do arkusza
 */
function onOpen() {
  const ui = SpreadsheetApp.getUi();
  ui.createMenu('⚡ Serwis LaserWar')
    .addItem('1. 📥 Importuj z arkusza serwisanta', 'importujZArkuszaSerwisanta')
    .addItem('2. 🧮 Przelicz marże', 'przeliczMarze')
    .addItem('3. 📋 Generuj zestawienie do faktur', 'generujZestawienie')
    .addSeparator()
    .addItem('4. ✅ Oznacz jako zafakturowane', 'oznaczJakoZafakturowane')
    .addSeparator()
    .addItem('ℹ️ Informacje o konfiguracji', 'pokazKonfiguracje')
    .addToUi();
}


/**
 * Pokazuje aktualną konfigurację
 */
function pokazKonfiguracje() {
  const idSkrocone = ID_ARKUSZA_SERWISANTA.substring(0, 20) + '...';

  SpreadsheetApp.getUi().alert(
    'AKTUALNA KONFIGURACJA\n\n' +
    '📄 ID arkusza serwisanta: ' + idSkrocone + '\n\n' +
    '💰 Marża na robociznę: ' + MARZA_ROBOCIZNA + '%\n' +
    '💰 Marża na części: ' + MARZA_CZESCI + '%\n\n' +
    'Aby zmienić konfigurację:\n' +
    'Rozszerzenia → Apps Script → edytuj wartości na górze kodu'
  );
}
```

---

## Krok 2.7: Wklej ID arkusza serwisanta (BARDZO WAŻNE!)

1. W kodzie który wkleiłeś, znajdź linię (jest blisko góry):
   ```javascript
   const ID_ARKUSZA_SERWISANTA = 'WKLEJ_TUTAJ_ID_ARKUSZA_SERWISANTA';
   ```

2. Pamiętasz ten długi ciąg znaków który zapisałeś w kroku 1.6?
   **Wklej go zamiast** `WKLEJ_TUTAJ_ID_ARKUSZA_SERWISANTA`

3. **UWAGA:** Zostaw apostrofy! Powinno wyglądać tak:
   ```javascript
   const ID_ARKUSZA_SERWISANTA = '1AbCdEfGhIjKlMnOpQrStUvWxYz';
   ```
   (oczywiście z Twoim prawdziwym ID)

---

## Krok 2.8: Ustaw swoje marże

W tym samym miejscu w kodzie znajdziesz:

```javascript
const MARZA_ROBOCIZNA = 40;  // 40% marży na robociznę
const MARZA_CZESCI = 30;     // 30% marży na części
```

**Zmień liczby na swoje marże:**
- Jeśli chcesz 50% marży na robociznę, zmień `40` na `50`
- Jeśli chcesz 25% marży na części, zmień `30` na `25`

---

## Krok 2.9: Zapisz skrypt

1. Kliknij ikonę dyskietki u góry **ALBO** naciśnij Ctrl+S (Cmd+S na Mac)
2. Jeśli pojawi się okno z prośbą o nazwę, wpisz: **"Skrypt Faktury LaserWar"**
3. Kliknij **OK**

---

## Krok 2.10: Uruchom skrypt pierwszy raz (autoryzacja)

**WAŻNE:** Przy pierwszym uruchomieniu Google zapyta o uprawnienia. To normalne!

1. W edytorze skryptów, u góry znajdź listę rozwijaną
2. Wybierz z niej: **"onOpen"**
3. Kliknij przycisk **▶ Uruchom** (trójkąt jak Play)

**Pojawi się okno autoryzacji:**

4. Kliknij **"Przejrzyj uprawnienia"** (Review permissions)
5. Wybierz swoje konto Google
6. Pojawi się ostrzeżenie "Google hasn't verified this app"
7. Kliknij **"Advanced"** (Zaawansowane) w lewym dolnym rogu
8. Kliknij **"Go to Skrypt Faktury LaserWar (unsafe)"**
9. Kliknij **"Allow"** (Zezwól)

**Gotowe! Zamknij kartę z edytorem skryptów.**

---

## Krok 2.11: Odśwież arkusz i sprawdź menu

1. Wróć do karty z Twoim arkuszem (tym z fakturami)
2. **Odśwież stronę** (F5)
3. Poczekaj 10-15 sekund

**Powinieneś zobaczyć nowe menu u góry:** "⚡ Serwis LaserWar"

---

# ETAP 3: Testowanie systemu

## Krok 3.1: Zaimportuj dane z arkusza serwisanta

1. Kliknij: **⚡ Serwis LaserWar → 1. 📥 Importuj z arkusza serwisanta**
2. Poczekaj chwilę (może potrwać kilka sekund)
3. Pojawi się komunikat ile pozycji zaimportowano
4. Kliknij OK

**Sprawdź arkusz - powinny pojawić się dane które wpisałeś w arkuszu Pawła!**

---

## Krok 3.2: Przelicz marże

1. Kliknij: **⚡ Serwis LaserWar → 2. 🧮 Przelicz marże**
2. Poczekaj chwilę
3. Pojawi się komunikat z informacją o marżach

**Sprawdź kolumny F, G, H - powinny być wypełnione cenami dla klientów!**

---

## Krok 3.3: Wygeneruj zestawienie do faktur

1. Kliknij: **⚡ Serwis LaserWar → 3. 📋 Generuj zestawienie do faktur**
2. Poczekaj chwilę
3. Pojawi się komunikat z podsumowaniem

**Na dole arkusza pojawi się nowa zakładka "ZESTAWIENIE DO FAKTUR"** - kliknij na nią!

Zobaczysz:
- Zestawienie pogrupowane per klient
- Lista napraw z cenami
- Suma do faktury dla każdego klienta
- Suma wszystkich faktur

---

## Krok 3.4: Oznacz jako zafakturowane

Po wystawieniu faktur:

1. Kliknij: **⚡ Serwis LaserWar → 4. ✅ Oznacz jako zafakturowane**
2. Pozycje zmienią status na "Zafakturowane" i podświetlą się na zielono

---

# ETAP 4: Codzienne użytkowanie

## Co robi Paweł (serwisant):

Paweł ma dostęp TYLKO do arkusza "Serwis LaserWar - SERWISANT" i wpisuje tam:

| Kolumna | Co wpisuje |
|---------|------------|
| A - Data | Kiedy zrobił naprawę |
| B - Klient | Nazwa firmy klienta |
| C - Opis naprawy | Co naprawił |
| D - Koszt robocizny | Ile Cię kasuje za robociznę |
| E - Koszt części | Ile kosztowały części |
| F - Uwagi | Dodatkowe informacje (opcjonalne) |

**Paweł NIE widzi:**
- Twoich marż
- Cen dla klientów
- Zestawień do faktur

---

## Co robisz Ty (workflow):

**Raz w tygodniu / miesiącu (jak często fakturujesz):**

1. Otwórz swój arkusz "Serwis LaserWar - FAKTURY (poufne)"
2. Kliknij: **⚡ Serwis LaserWar → 1. 📥 Importuj z arkusza serwisanta**
3. Kliknij: **⚡ Serwis LaserWar → 2. 🧮 Przelicz marże**
4. Kliknij: **⚡ Serwis LaserWar → 3. 📋 Generuj zestawienie do faktur**
5. Przejdź do zakładki "ZESTAWIENIE DO FAKTUR"
6. Przepisz dane do programu do faktur (Fakturownia, inFakt, etc.)
7. Wystaw faktury klientom
8. Wróć do głównego arkusza
9. Kliknij: **⚡ Serwis LaserWar → 4. ✅ Oznacz jako zafakturowane**

**Cały proces: 5-10 minut zamiast godziny!**

---

# ETAP 5: Rozwiązywanie problemów

## Problem: "Nie udało się otworzyć arkusza serwisanta"

**Rozwiązanie:**
1. Sprawdź czy ID arkusza jest poprawne (skopiowałeś właściwy ciąg znaków)
2. Upewnij się, że Ty (Twoje konto Google) masz dostęp do arkusza serwisanta
3. Sprawdź czy apostrofy w kodzie są na miejscu: `'ID_TUTAJ'`

---

## Problem: Nie widzę menu "⚡ Serwis LaserWar"

**Rozwiązanie:**
1. Odśwież stronę (F5)
2. Poczekaj 15-20 sekund
3. Jeśli dalej nie ma - otwórz Apps Script i uruchom funkcję "onOpen"

---

## Problem: Import nie znajduje nowych danych

**Rozwiązanie:**
- System sprawdza czy dane już istnieją (żeby nie duplikować)
- Jeśli dana naprawa jest już w Twoim arkuszu, nie zostanie dodana ponownie
- Sprawdź czy Paweł wpisał nowe naprawy po ostatnim imporcie

---

## Problem: Zestawienie jest puste

**Rozwiązanie:**
1. Sprawdź czy kolumna "Status" (I) zawiera dokładnie tekst: `Do faktury`
2. Wielkość liter ma znaczenie!
3. Upewnij się, że uruchomiłeś "Przelicz marże" przed generowaniem zestawienia

---

# Podsumowanie

## Co masz teraz:

| Element | Opis |
|---------|------|
| **Arkusz serwisanta** | Paweł wpisuje naprawy (widzi tylko koszty) |
| **Twój arkusz** | Import danych, marże, zestawienia (poufne) |
| **Automatyczne marże** | System liczy za Ciebie |
| **Zestawienie do faktur** | Gotowe do przepisania |
| **Rozdzielenie dostępu** | Paweł nie widzi Twoich cen |

## Oszczędność:
- **Czas:** ~8-10 godzin miesięcznie
- **Koszt:** 0 zł
- **Bezpieczeństwo:** Paweł nie ma dostępu do Twoich marż

---

*Instrukcja przygotowana dla Laser Tag Poznań | Styczeń 2025*
