# Kapitel 10: Testa, analysera och visa upp

> **I det här kapitlet lär du dig**
> - att planera och genomföra ett speltest
> - att prioritera vad som ska ändras efter testet
> - att analysera ett digitalt verk både estetiskt och tekniskt
> - att färdigställa, exportera och visa upp ditt arbete

Det är lätt att tro att spelet är tydligt, för du vet ju exakt hur det fungerar. Den viktigaste stunden i projektet är när någon annan får prova, och du tyst tittar på. Då upptäcker du hur spelet egentligen är. Det här kapitlet handlar om vad du gör med den informationen, och om hur du sätter ord på det du skapat.

## Speltest

Ett **speltest** är när någon annan provar spelet medan du observerar. Syftet är inte att få beröm utan att hitta problem medan det går att åtgärda dem.

### Planera testet

1. **Bestäm vad du vill veta.** "Förstår man hur oljan hämtas?" är bättre än "Är spelet bra?".
2. **Gör testuppgifter.** Till exempel: "Starta spelet och försök klara en runda."
3. **Välj testare.** Helst någon som inte sett spelet och som liknar målgruppen.

### Under testet

Be testaren **tänka högt**, alltså säga vad den tänker medan den spelar. Metoden är väl beprövad för att förstå hur människor tänker när de använder något. Den enklaste regeln är svår: **hjälp inte till**. När du förklarar eller pekar förlorar du informationen. Om testaren kör fast är det just det du ville få veta.

Anteckna det du **ser**, inte vad du tror. "Sprang förbi oljan tre gånger" är användbart. "Tyckte nog att spelet var svårt" är en gissning.

Efteråt kan du fråga: "Vad gick spelet ut på?", "När kände du dig osäker?" och "Vad skulle du ändra?".

Fråga alltid om lov innan du filmar eller spelar in någon, och dela inte materialet.

### Hur många testare?

Forskaren Jakob Nielsen beskriver en modell där andelen hittade problem beror på hur många som testar:

```text
hittade problem = 1 − (1 − L)^n
```

Här är *L* andelen problem en enskild testare hittar och *n* antalet testare. Med hans typiska värde *L* = 31 procent och 5 testare får vi:

```text
1 − (1 − 0,31)^5 = 1 − 0,69^5 ≈ 0,84
```

Modellen ger alltså att fem testare hittar omkring 84 procent av problemen. Siffran är en tumregel från studier av användbarhet, inte en naturlag, och den gäller bäst när testarna liknar varandra. Lärdomen är ändå tydlig: några få testare räcker långt, och flera små omgångar är bättre än en enda stor.

### Genomräknat exempel: tolka resultatet

Du låter 5 testare försöka med 4 uppgifter vardera. Det ger 20 försök, och 15 av dem lyckas.

```text
15 ÷ 20 = 0,75, alltså 75 procent
```

Men en siffra säger inte vad som är fel. Därför gör du också en lista över problem och ger dem poäng: hur många som drabbades, gånger hur allvarligt det var, på en skala 1 till 3.

| Problem | Drabbade | Allvar | Poäng |
|---|---:|---:|---:|
| Hittar inte oljedepån | 4 | 3 | 12 |
| Texten är svårläst | 2 | 2 | 4 |
| Musiken för stark | 3 | 1 | 3 |
| Spelet kraschar vid omstart | 1 | 3 | 3 |

Börja med oljedepån. Enligt poängen ligger kraschen lägre, men ett spel som kraschar ska ändå alltid åtgärdas. Poängen hjälper dig att tänka, men ersätter inte ditt omdöme. Efter ändringarna ska du testa igen, för att se att problemet faktiskt är löst.

## Att analysera digitala uttryck

Att analysera är något annat än att tycka. När du analyserar visar du **vad** verket gör, **hur** det gör det och **varför** det fungerar. Du kan använda samma arbetssätt på andras verk och ditt eget.

| Steg | Fråga |
|---|---|
| Beskriv | Vad finns? Vad händer? |
| Analysera | Hur är det gjort? Vilka medel används? |
| Tolka | Vad betyder det? Vilken känsla skapas? |
| Värdera | Fungerar det, och varför? Vad skulle kunna bli bättre? |

Du behöver betrakta verket utifrån två perspektiv, och de hänger ihop.

| Estetiskt perspektiv | Tekniskt perspektiv |
|---|---|
| Stil, form, palett | Upplösning, format, texturstorlekar |
| Stämning och dramaturgi | Bildfrekvens, laddtider |
| Ljudets känsla | Ljudformat, mixning |
| Berättande | Spelmekanik, logik, styrning |
| Användarupplevelse | Stabilitet, vilka datorer det körs på |

Använd **begrepp** från kapitlen. Skriver du "bakgrunden har låg kontrast i valör så att spelaren blir det första ögat fångar" visar du mer än om du skriver "det ser bra ut".

### Genomgånget exempel: tre nivåer av analys

Här är samma iakttagelse om Fyrvaktaren skriven på tre sätt. Exemplen är påhittade och visar skillnaden. Hur din analys bedöms avgör läraren utifrån kursens kriterier.

**Enkel:** Spelet är mörkt och det ser spännande ut. Ljuset från lamporna är fint och musiken passar.

**Utvecklad:** Spelet använder en mörk blå palett där lampornas gula ljus får hög valörkontrast. Det gör att spelaren ser vad som är viktigt. Musiken blir starkare när stormen tilltar, vilket gör att spelet känns mer stressigt.

**Välutvecklad:** Den mörkblå paletten och det gula ljuset gör att valörkontrasten leder blicken till lamporna, så att det estetiska valet också fungerar som information. När lamporna blir fler stiger ljudet genom musikens lager. Dramaturgin bärs alltså av både mekanik och ljud. Tekniskt krävs dock fler ljuskällor i takt med att lamporna blir fler, och i tester sjönk bildfrekvensen på en äldre dator. Därför minskade jag antalet ljus som kastar skuggor, vilket gjorde skuggorna enklare men spelet smidigare.

Skillnaden är att den sista texten binder ihop val, orsak och konsekvens, använder begrepp och väger estetiska mot tekniska hänsyn.

## Färdigställa och dokumentera

Mot slutet ska du hålla tillbaka. Lägg inte till nya funktioner sista veckan. Prioritera att spelet går att spela från början till slut, och putsa sedan på ljudnivåer, texter, fel och menyer.

Sammanställ din dokumentation:

- Plan, skisser och moodboard.
- Processloggen.
- `KREDITER.md`.
- Speltestets anteckningar och vad du ändrade.
- Reflektionen: vad blev bra, vad blev inte som planerat, vad skulle du göra om?

## Exportera

Att **exportera** är att göra om projektet till ett program som fungerar utan Godot. Du behöver först installera **exportmallar** via **Editor → Manage Export Templates**. Under **Project → Export** lägger du till en förinställning för Windows Desktop, väljer plats och exporterar. Godot skapar då en `.exe` och en `.pck`-fil som innehåller spelets data, och den går att bädda in i `.exe`-filen med ett val i exportinställningarna.

Testa alltid på en annan dator än din. Filer som råkat ligga utanför projektet, eller felaktiga stora och små bokstäver i sökvägar, brukar visa sig här. Windows kan också varna när en okänd `.exe` startas, eftersom den inte är signerad, och då behöver testaren veta att det kan hända.

## Presentations- och spridningsvägar

Hur du visar ett verk påverkar hur det uppfattas. Vilken väg passar ditt spel?

| Väg | Passar för | Att tänka på |
|---|---|---|
| Mässa med testspelning | Direkt respons från folk | Spelet ska förstås på en minut, utan instruktioner |
| Muntlig redovisning | Visa din process och dina val | Berätta om beslut, inte bara funktioner |
| Körbar fil | Klasskamrater, vänner | Testa på en annan dator |
| GitHub | Att visa projekt och kod | Skriv en bra README, kontrollera att assets får delas |
| Spelsidor som [itch.io](https://itch.io/) | Publik spridning | Du behöver rätt till allt innehåll, och läraren bör veta om det |
| Webb | Spela direkt i webbläsaren | Godot kan exportera till webben, men alla funktioner stöds inte överallt |

Inför en mässa eller visning bör du ha skärmbilder, en kort presentation och en bra första minut i spelet. Skriv en kort text med titel, pitch, kontroller och krediter. Om du publicerar något, kontrollera en gång till att du har rätt till allt du delar, att ingen annans uppgifter syns, och att det passar målgruppen.

## Begrepp

- **Speltest:** när andra provar spelet medan du observerar.
- **Tänka högt:** testmetod där testaren säger vad den tänker medan den spelar.
- **Analys:** att visa vad ett verk gör, hur och varför.
- **Estetiskt perspektiv:** att se till stil, stämning och upplevelse.
- **Tekniskt perspektiv:** att se till format, prestanda och konstruktion.
- **Exportera:** att bygga ett körbart program av projektet.
- **Exportmall:** färdig kod från Godot som krävs för att bygga ett spel för en viss plattform.
- **Spridningsväg:** det sätt ett verk når sin publik.

## Testa dig själv

1. Varför ska du inte hjälpa testaren under ett speltest?
2. Vad är skillnaden mellan att anteckna vad du ser och vad du tror?
3. Hur kan du använda poäng för att prioritera problem, och när räcker poängen inte?
4. Vad är skillnaden mellan att analysera och att tycka?
5. Ge ett exempel på ett estetiskt och ett tekniskt perspektiv på samma del av ett spel.
6. Varför ska du testa det exporterade spelet på en annan dator?
7. Vad måste du kontrollera innan du publicerar spelet offentligt?

## Övningar

**Grund.** Skriv en testplan med tre frågor du vill ha svar på och tre uppgifter till testaren.

**Grund.** Under ett test gör 6 testare vardera 5 uppgifter, och 24 försök lyckas. Hur många procent är det?

<details><summary>Svar</summary>

6 × 5 = 30 försök. 24 ÷ 30 = 0,80, alltså 80 procent.

</details>

**Vidare.** Använd Nielsens formel med *L* = 31 procent. Hur stor andel av problemen beräknas hittas med 3 testare?

<details><summary>Svar</summary>

1 − 0,69³ = 1 − 0,3285 ≈ 0,67, alltså omkring 67 procent.

</details>

**Vidare.** Välj ett kort spel och skriv en analys enligt de fyra stegen, med minst fem begrepp från boken.

**Utmaning.** Skriv en analys av ditt eget spel som binder ihop minst ett estetiskt val med en teknisk konsekvens. Föreslå också vad du skulle ändra med mer tid.

## Koppling till projektet

I [2D-spelet](../projekt/2d-spel/README.md) testspelar en klasskamrat ditt spel, du åtgärdar feedbacken, exporterar och redovisar. I [3D-spelet](../projekt/3d-spel/README.md) genomför du användartester, åtgärdar dem, värderar din plan och visar spelet på en mässa där ni provar varandras spel.

## Läs mer

- [Why You Only Need to Test with 5 Users (Nielsen Norman Group)](https://www.nngroup.com/articles/why-you-only-need-to-test-with-5-users/)
- [Thinking Aloud (Nielsen Norman Group)](https://www.nngroup.com/articles/thinking-aloud-the-1-usability-tool/)
- [Godot: att exportera projekt](https://docs.godotengine.org/en/stable/tutorials/export/exporting_projects.html)
- [Godot: exportera för Windows](https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_windows.html)
- [Godot: exportera för webben](https://docs.godotengine.org/en/stable/tutorials/export/exporting_for_web.html)

[← Föregående](09-gestalta-i-3d.md) | [Innehåll](../README.md)
