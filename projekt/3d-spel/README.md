# Projekt: 3D-Spel

## Syfte

I det här projektet gör du individuellt ett valfritt 3D-spel i Godot. Du bygger vidare på det du kan från 2D-spelet och får arbeta med att gestalta en plats: modeller, material, ljus, kamera, ljud och ett gränssnitt som är lätt att använda. Spelet visas på en mässa där ni provar varandras spel.

Projektet delas med kursen Gränssnittsdesign, där gränssnittet är det centrala. I kursen Digitalt skapande ligger tyngdpunkten på hela skapandeprocessen och på dina estetiska och tekniska val.

## Koppling till kursen

**Betygskriterierna i vanliga ord.** Bedömningen utgår från Skolverkets kriterier, som finns ordagrant i [kursplanen](../../kursplan.md). I det här projektet handlar de om att du

- känner till och kan beskriva skapandeprocessens olika faser
- planerar och genomför ett digitalt projekt och dokumenterar hur det gick till
- hanterar digitala verktyg och gestaltar uttryck i 3D med bild, ljud och rörelse
- analyserar digitala gestaltningar, även ditt eget spel, med relevanta begrepp ur estetiskt och tekniskt perspektiv

Kriterierna nämner arbete både ensam och i grupp. Det här projektet görs individuellt, och läraren berättar hur grupparbete ingår i kursen.

**Centralt innehåll som projektet tar upp.** Analoga och digitala skapandeprocesser, skissarbete, digital samverkan, genomförande och dokumentation, presentationsvägar, gränslandet mellan konst och teknik, programvara och arbetsflöden, kombinationer av estetiska uttryck samt analys av digitala uttryck. Hela kopplingen finns i [täckningsmatrisen](../../kursplan.md).

**Kapitel som förbereder.**

| Kapitel | Används till |
|---|---|
| [3. Skissa och planera](../../kapitel/03-skiss-och-plan.md) | Projektplan, kravlista, värdering av planen |
| [4. Verktyg och samarbete](../../kapitel/04-verktyg-och-samarbete.md) | Filer, GitHub och Git LFS |
| [5. Assets, upphovsrätt och etik](../../kapitel/05-assets-och-upphovsratt.md) | 3D-modeller, texturer och krediter |
| [7. Ljud och musik](../../kapitel/07-ljud-och-musik.md) | Ljud, musik och stämning |
| [8. Gränssnitt och spelarens upplevelse](../../kapitel/08-granssnitt-och-upplevelse.md) | Menyer, tillgänglighet, återkoppling |
| [9. Att gestalta i 3D](../../kapitel/09-gestalta-i-3d.md) | Modeller, material, ljus, kamera, vägvisning |
| [10. Testa, analysera och visa upp](../../kapitel/10-testa-analysera-visa.md) | Användartest, export och mässa |

Kapitel 1, 2 och 6 är också användbara. De förbereder processen, idén och den visuella formen.

## Vad du ska göra

Du utvecklar individuellt ett valfritt 3D-spel i Godot med GDScript. Du får återskapa ett känt spel eller hitta på ett eget, men inte hämta färdig kod från nätet.

1. Gå igenom Godots tutorial för ditt första 3D-spel.
2. Skriv en projektplan med spelidé, målgrupp, skisser, kravlista och tekniska förutsättningar, och få den godkänd.
3. Bygg spelet: 3D-modeller och material, rörelse, kamera, kollisioner, mål och vinst- och förlustvillkor.
4. Skapa startmeny, HUD och game over-skärm samt ljud, scenbyten och respawn.
5. Testa spelet på andra, förbättra det och exportera det till en `.exe`-fil.

## Krav och leverabler

Kraven kommer från [guiden till projektet](https://github.com/abbjetmus/Godot-3D-Spel).

| Del | Krav |
|---|---|
| 0. Planering | Dokument med beskrivning och skiss, godkänt av läraren |
| 1. Spelmekanik | Rörelse med tangentbord eller joystick, kollisioner, en kamera som följer spelaren, ett grundläggande mål samt vinst- och förlustvillkor |
| 2. 3D-grafik | 3D-modeller för spelare, miljö och fiender (kan vara enkla former), grundläggande texturer eller färger, minimala animationer |
| 3. Gränssnitt | Startskärm med Starta-knapp, game over-skärm. HUD är valfritt enligt guiden, men ingår i projektbeskrivningen. |
| 4. Ljud | Ljud för rörelse, hopp, kollisioner eller insamling, bakgrundsmusik eller atmosfärljud |
| 5. Spelelement | Fiender som patrullerar eller jagar, samlarföremål, enkel fysik |
| 6. Scener | Scenövergångar, respawn eller återställning |
| 7. Distribution | Körbar `.exe` som andra kan testa |

**Det här lämnar du in:** projektplanen, spelet som `.exe` och projektet på GitHub Classroom med Git LFS, enligt [guiden](https://github.com/abbjetmus/Godot-3D-Spel). Läraren delar länken till uppgiften.

## Arbetsgång

| Lektion | Innehåll |
|---|---|
| 1 | Projektstart: genomgång av projektet och kraven. Repetition av Godot med noder och scener i 3D (`Node3D`, `Camera3D`). |
| 2 | Starta tutorialen Your first 3D game i Godot Docs och få en spelare som rör sig i en 3D-scen. |
| 3–8 | Lektionsplanen anger inget innehåll för dessa lektioner. Enligt projektbeskrivningen behöver tutorialen och projektplanen (kapitel 3) vara klara innan du bygger spelet. Läraren anger vad som ska göras varje lektion. |
| 9 | Bygg grundmekaniken: spelarens rörelse, en kamera som följer spelaren och kollisioner. |
| 10 | 3D-grafik: bygg miljön med 3D-modeller, material och texturer, egna enkla former eller assets. (Kapitel 5 och 9) |
| 11 | Lektionsplanen anger inget innehåll. Läraren anger vad som ska göras. |
| 12 | Gränssnitt: startmeny, HUD och game over-skärm. Fundera på vilken information spelaren behöver och var den kommer ifrån. (Kapitel 8) |
| 13 | Eget arbete: fiender som patrullerar eller jagar och enkel fysik som hopp och fall. Avstämning med läraren. |
| 14 | Ljud och spelflöde: ljudeffekter, bakgrundsmusik, scenövergångar och respawn. (Kapitel 7) |
| 15 | Användartest: låt klasskamrater testa ditt spel och anteckna deras feedback om tydlighet och användbarhet. (Kapitel 10) |
| 16 | Åtgärda feedbacken och förbättra tillgängligheten, till exempel kontrast, textstorlek och kontroller. Värdera din projektplan. (Kapitel 3 och 8) |
| 17 | Färdigställ spelet: exportera till `.exe`, pusha till GitHub Classroom med Git LFS och förbered mässan. (Kapitel 4 och 10) |
| 18 | Redovisning: mässa där ni testar och ger feedback på varandras spel. |

## Bedömning

Spelet redovisas på en mässa där ni testar varandras spel. I kursen Digitalt skapande bedöms arbetet utifrån Skolverkets [betygskriterier](../../kursplan.md):

| Vad som bedöms | Så kan du visa det |
|---|---|
| Kunskaper om skapandeprocessens faser | Du beskriver hur arbetet gick genom faserna, och hur testen ändrade spelet |
| Planering, genomförande och dokumentation | Projektplanen, hur du värderar den, processloggen och att spelet blev klart |
| Hantering av digitala verktyg och kvaliteten på gestaltningen | 3D-objekt, material, ljus, ljud och hur väl de samspelar |
| Analys ur estetiskt och tekniskt perspektiv | Du förklarar dina val och analyserar spelet med begrepp från boken |

Bedömning som rör gränssnitt, användbarhet och tillgänglighet på djupet hör till kursen Gränssnittsdesign. Läraren anger vad som gäller i varje kurs.

## Material

- [Guide och krav: Godot-3D-Spel](https://github.com/abbjetmus/Godot-3D-Spel)
- [Godot Docs: Your first 3D game](https://docs.godotengine.org/en/stable/getting_started/first_3d_game/index.html)
- [Godot Docs: exportera för Windows](https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_windows.html)
- [Kursrepo Gränssnittsdesign](https://github.com/abbindustrigymnasium/granssnittsdesign)
- [Kursplan och täckningsmatris](../../kursplan.md)

## Tips

- Bygg en grå prototyp med enkla former först. Sätt stämning med ljus och dimma innan du lägger in detaljer.
- Börja med `KREDITER.md` dag ett, om du använder färdiga modeller eller texturer.
- Ställ in Git LFS innan du lägger till stora filer. Guiden i repot visar hur, och det är besvärligt att rätta i efterhand.
- Tänk på skalan: en enhet i Godot är en meter.
- Kontrollera att spelet går att se på en sämre skärm, särskilt om det är mörkt.
- Guiden i projektets repo använder i vissa exempel äldre nodnamn. I Godot 4 heter noden för en styrbar figur `CharacterBody3D`, inte `KinematicBody3D`, och `move_and_slide()` används utan argument. Följ Godots aktuella dokumentation när de skiljer sig.
- Inför mässan: spelet ska förstås på en minut. Ha en kort text med titel, kontroller och krediter bredvid.
