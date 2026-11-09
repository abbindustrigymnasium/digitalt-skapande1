# Projekt: 2D-Spel

## Syfte

I det här projektet gör du ett eget 2D-spel i spelmotorn Godot. Du får gå igenom hela skapandeprocessen, från idé och skiss till ett färdigt spel som andra provar. I kursen Digitalt skapande ligger tyngdpunkten på det du gestaltar: idén, den visuella formen, ljudet, spelarens upplevelse och hur du dokumenterar och värderar arbetet.

Projektet delas med kursen Programmering nivå 1, där programmeringen är det centrala. Här behöver koden fungera, men det är dina skapande val som står i fokus.

## Koppling till kursen

**Betygskriterierna i vanliga ord.** Bedömningen utgår från Skolverkets kriterier, som finns ordagrant i [kursplanen](../../kursplan.md). I det här projektet handlar de om att du

- känner till och kan beskriva skapandeprocessens olika faser
- planerar och genomför ett digitalt projekt och dokumenterar hur det gick till
- hanterar digitala verktyg och gestaltar uttryck med bild, ljud och rörelse
- analyserar digitala gestaltningar, även ditt eget spel, med relevanta begrepp ur estetiskt och tekniskt perspektiv

Kriterierna nämner arbete både ensam och i grupp. Läraren berättar hur grupparbete ingår i kursen.

**Centralt innehåll som projektet tar upp.** Analoga och digitala skapandeprocesser, skissarbete, digital samverkan, genomförande och dokumentation, presentationsvägar, gränslandet mellan konst och teknik, programvara och arbetsflöden, kombinationer av estetiska uttryck samt analys av digitala uttryck. Hela kopplingen finns i [täckningsmatrisen](../../kursplan.md).

**Kapitel som förbereder.**

| Kapitel | Används till |
|---|---|
| [1. Skapandeprocessen](../../kapitel/01-skapandeprocessen.md) | Att arbeta i faser och föra processlogg |
| [2. Spelidé och berättande](../../kapitel/02-spelide-och-berattande.md) | Pitch, kärnloop, målgrupp |
| [3. Skissa och planera](../../kapitel/03-skiss-och-plan.md) | Planeringsdokumentet |
| [4. Verktyg och samarbete](../../kapitel/04-verktyg-och-samarbete.md) | Godot, filer, GitHub |
| [5. Assets, upphovsrätt och etik](../../kapitel/05-assets-och-upphovsratt.md) | Lånat material och krediter |
| [6. Bild och animation i 2D](../../kapitel/06-bild-och-animation.md) | Sprites, palett, animation |
| [7. Ljud och musik](../../kapitel/07-ljud-och-musik.md) | Ljudeffekter och musik |
| [8. Gränssnitt och spelarens upplevelse](../../kapitel/08-granssnitt-och-upplevelse.md) | Menyer och återkoppling |
| [10. Testa, analysera och visa upp](../../kapitel/10-testa-analysera-visa.md) | Testspelning, export och redovisning |

## Vad du ska göra

Du utvecklar ett eget 2D-spel i Godot och programmerar det i GDScript. Du får återskapa ett känt spel eller hitta på ett eget, men du får inte hämta färdig kod från nätet.

1. Gå igenom Godots tutorial för ditt första 2D-spel.
2. Planera spelet i ett dokument med beskrivning, skiss och gärna pseudokod eller flödesschema, och få det godkänt av läraren.
3. Bygg spelmekanik, grafik, gränssnitt, ljud, spelelement och scenbyten.
4. Låt andra testa spelet och förbättra det utifrån deras synpunkter.
5. Exportera spelet till en körbar `.exe`-fil, lämna in koden på GitHub och redovisa.

## Krav och leverabler

Kraven kommer från [guiden till projektet](https://github.com/abbjetmus/Godot-2D-Spel).

| Del | Krav |
|---|---|
| 0. Planering | Dokument med beskrivning och skiss, godkänt av läraren |
| 1. Spelmekanik | Spelarens rörelse, kollisioner, ett grundläggande mål samt vinst- och förlustvillkor |
| 2. Grafik | Sprites för spelare, fiender och bakgrund, minst en enkel animation. Tileset är valfritt. |
| 3. Gränssnitt | Startskärm med Starta-knapp, game over-skärm. HUD är valfritt. |
| 4. Ljud | Ljudeffekter, till exempel för hopp, insamling eller kollision, och bakgrundsmusik |
| 5. Spelelement | Fiender som rör sig, samlarföremål, enkel fysik vid behov |
| 6. Scener | Scenövergångar, omstart eller respawn |
| 7. Distribution | Körbar `.exe` som andra kan testa |

**Det här lämnar du in:** planeringsdokumentet, spelet som `.exe` och projektets kod på GitHub.

## Arbetsgång

| Lektion | Innehåll |
|---|---|
| 1 | Projektstart: genomgång av projektet och kraven. Installera Godot och lär dig noder, scener och ditt första GDScript. Starta din processlogg. |
| 2 | Tutorialen Your first 2D game i Godot Docs: skapa spelaren och styr den med tangentbordet. |
| 3 | Fortsätt tutorialen: fiender, signaler, HUD och poäng. Gör klart ditt första spel. |
| 4 | Vi bygger ett enkelt spel tillsammans och repeterar variabler, villkor och kollisioner i GDScript. |
| 5 | Planering: skriv ett dokument med spelidé, skiss och pseudokod eller flödesschema för spelets logik. Få planen godkänd av läraren. (Kapitel 2 och 3) |
| 6 | Bygg grundläggande spelmekanik: spelarens rörelse, kollisioner, spelets mål och vinst- och förlustvillkor. |
| 7 | Grafik: lägg in sprites för spelare, fiender och bakgrund och gör minst en enkel animation. (Kapitel 5 och 6) |
| 8 | Gränssnitt: startskärm med Starta-knapp, game over-skärm och gärna en HUD med poäng eller tid. (Kapitel 8) |
| 9 | Eget arbete och avstämning: visa ditt spel för läraren och bocka av kraven du har klarat. |
| 10 | Spelelement: fiender som rör sig, samlarföremål och enkel fysik som hopp och gravitation. |
| 11 | Ljud: lägg till ljudeffekter för till exempel hopp och kollision samt bakgrundsmusik. (Kapitel 7) |
| 12 | Scen- och nivåhantering: byt mellan nivåer och låt spelaren starta om. |
| 13 | Eget arbete: felsök, kommentera koden och låt en klasskamrat testspela ditt spel. (Kapitel 10) |
| 14 | Färdigställande: åtgärda feedbacken från testspelningen och putsa grafik, ljud och menyer. |
| 15 | Exportera spelet till en `.exe`-fil, pusha koden till GitHub och förbered redovisningen. (Kapitel 10) |
| 16 | Redovisning: visa ditt spel, låt andra testa det och berätta hur du löste spelmekaniken och vilka skapande val du gjorde. |

## Bedömning

Du redovisar spelet och låter andra testa det. I kursen Digitalt skapande bedöms arbetet utifrån Skolverkets [betygskriterier](../../kursplan.md):

| Vad som bedöms | Så kan du visa det |
|---|---|
| Kunskaper om skapandeprocessens faser | Du beskriver i loggen och på redovisningen hur arbetet gick genom faserna, och var du gick tillbaka och ändrade |
| Planering, genomförande och dokumentation | Planeringsdokumentet, processloggen och att spelet blev klart |
| Hantering av digitala verktyg och kvaliteten på gestaltningen | Spelets bild, ljud och gränssnitt och hur väl de hänger ihop |
| Analys ur estetiskt och tekniskt perspektiv | Du förklarar dina val och analyserar spelet med begrepp från boken |

Bedömningen av programmeringen hör till kursen Programmering. Läraren anger vad som gäller i varje kurs.

## Material

- [Guide och krav: Godot-2D-Spel](https://github.com/abbjetmus/Godot-2D-Spel)
- [Godot Docs: Your first 2D game](https://docs.godotengine.org/en/stable/getting_started/first_2d_game/index.html)
- [GDScript-tutorials](https://gdscript.com/tutorials/)
- [Kursplan och täckningsmatris](../../kursplan.md)

## Tips

- Gör en spelbar version med grå rutor innan du lägger tid på grafik, och kontrollera att kärnloopen är rolig.
- Bestäm stil och palett tidigt. Det sparar mycket omarbetning.
- Börja med `KREDITER.md` dag ett, och lägg till en rad varje gång du hämtar något.
- Låt testaren spela utan att du förklarar. Anteckna det du ser.
- Guiden i projektets repo använder i vissa exempel äldre nodnamn. I Godot 4 heter noden för en styrbar figur `CharacterBody2D`, inte `KinematicBody2D`, och `move_and_slide()` används utan argument. Följ Godots aktuella dokumentation när de skiljer sig.
- Skriv i loggen varje gång du stryker något och varför. Det är en del av din dokumentation.
