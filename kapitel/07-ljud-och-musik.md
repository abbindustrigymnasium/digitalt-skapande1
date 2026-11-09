# Kapitel 7: Ljud och musik

> **I det här kapitlet lär du dig**
> - vad ljud gör i ett spel, utöver att låta bra
> - hur du spelar in, redigerar och väljer ljudfiler
> - hur du bygger musik som kan loopa
> - hur du mixar ljud med decibel

Stäng av ljudet och spela ett spel du tycker om. Plötsligt känns det halvdant, och du missar saker som händer bakom din rygg. Ljud är en stor del av upplevelsen, men det hamnar ofta sist på listan. I det här kapitlet får du verktyg för att göra det med avsikt.

## Vad gör ljud i ett spel?

Ljud har flera uppgifter samtidigt:

| Uppgift | Exempel i Fyrvaktaren |
|---|---|
| Återkoppling, bekräftar att något hänt | Ett lågt "klunk" när oljan hälls i |
| Information, varnar eller hjälper | En sprakande låga när en lampa är nära att slockna |
| Stämning | Stormen dånar i bakgrunden |
| Identitet | Ett kort tema som kännetecknar spelet |

Bra ljud gör att spelet känns responsivt. Även en liten handling behöver ett svar, annars undrar spelaren om den räknades.

## Ljudets roll i berättandet

I film och spel skiljer man mellan två sorters ljud:

- **Diegetiskt ljud** finns i spelets värld och kan höras av figurerna, till exempel fotsteg och storm.
- **Icke-diegetiskt ljud** finns bara för spelaren, till exempel menyljud och bakgrundsmusik.

Att flytta något från den ena sorten till den andra ger starka effekter. Om musiken från början är bakgrundsmusik, men du i slutet hittar en radio som spelar den, är det plötsligt en del av världen.

Ljudet kan också kombineras med bild för att berätta. Ett dovt dån som bara hörs på avstånd skapar en hotfull känsla av något som är på väg, även om spelaren inte ser något. Att ljud och bild kombineras så att de tillsammans säger mer än var för sig är kärnan i den här kursen.

Tystnad är också ett verktyg. En kort stund utan musik före något stort gör att det stora känns ännu större.

## Från ljudvåg till fil

Ljud är tryckvågor i luften. En mikrofon omvandlar dem till en elektrisk signal, och en dator mäter sedan signalen med jämna mellanrum. Det kallas **sampling**. Ett mätvärde kallas sample.

- **Samplingsfrekvens:** hur många mätningar per sekund. 44 100 per sekund, skrivet 44,1 kHz, är vanligt. Det räcker för att återge frekvenser upp till drygt 22 kHz, vilket täcker det människor normalt hör.
- **Bitdjup:** hur noggrant varje mätning lagras. 16 bitar är vanligt.
- **Kanaler:** ett (mono) eller två (stereo).

### Genomräknat exempel: filstorlek

Hur mycket plats tar en minut okomprimerat ljud i 16-bitars stereo med 44,1 kHz?

```text
44 100 mätningar/s × 2 byte × 2 kanaler × 60 s = 10 584 000 byte ≈ 10,6 MB
```

Komprimerar du till Ogg Vorbis med 128 kilobit per sekund blir det i stället:

```text
128 000 bit/s ÷ 8 × 60 s = 960 000 byte ≈ 0,96 MB
```

Ungefär en elftedel av storleken. Därför används ofta komprimerade format för musik. Godot kan importera WAV, Ogg Vorbis och MP3. WAV tar stor plats men är lätt för datorn att spela upp, och passar korta ljudeffekter. Ogg Vorbis är litet men kräver mer av processorn, och passar musik.

## Skapa och hitta ljud

Du har flera vägar, och de går att kombinera:

| Väg | Arbetssätt | Passar för |
|---|---|---|
| Spela in själv | Mobil eller mikrofon, redigera i Audacity | Eget uttryck, unika ljud |
| Generera | sfxr eller Bfxr | Retroeffekter |
| Hämta | Freesound, Kenney | När tiden är knapp, läs licensen |
| Komponera | LMMS, MuseScore, eget instrument | Musik |

### Ljud med vardagssaker

Ljudeffekter görs ofta med helt andra föremål än det ljudet föreställer. Det kallas **foley** i filmvärlden. Att krama en plastpåse kan låta som eld. Selleri som bryts kan låta som något som knäcks. Att skaka en tunn plåtskiva kan låta som åska. Övergången från det analoga till det digitala blir tydlig här: du spelar in något fysiskt och bearbetar det sedan.

Spela in i ett tyst rum, nära mikrofonen men inte så nära att det spricker. I [Audacity](https://www.audacityteam.org/) klipper du bort tystnad i början och slutet och normaliserar ljudet så att det inte är för svagt. En kort tystnad i början gör att ljudet känns försenat i spelet.

### Variation

Hör du samma ljudfil hundra gånger blir det enformigt och maskinellt. Två knep ger variation:

- Spela in tre till fem varianter av fotsteg och slumpa vilken som spelas.
- Slumpa tonhöjden lite varje gång.

```gdscript
extends Area2D

@onready var ljud: AudioStreamPlayer2D = $Ljud

func _on_body_entered(_body):
    # Lite olika tonhöjd varje gång
    ljud.pitch_scale = randf_range(0.9, 1.1)
    hide()
    $CollisionShape2D.set_deferred("disabled", true)
    ljud.play()
    # Vänta tills ljudet spelat klart, annars klipps det av
    await ljud.finished
    queue_free()
```

Koden visar en vanlig fälla: tar du bort ett föremål direkt försvinner också ljudet. Då döljer du det först och tar bort det när ljudet är slut. I den här koden är signalen `body_entered` kopplad till funktionen i Godots editor. `AudioStreamPlayer2D` gör dessutom att ljud blir svagare på avstånd, något som `AudioStreamPlayer` inte gör.

## Musik som loopar

Musik i spel spelas ofta i **loop**, alltså om och om igen utan avbrott. En bra loop har inga hörbara skarvar. Enklast är att göra musiken i exakt ett helt antal takter. Godots importinställningar har ett val som aktiverar loop.

Musik räknas i **slag per minut**, BPM.

### Genomräknat exempel: hur lång blir loopen?

En låt i 4/4-takt går i 120 BPM, med 4 slag per takt. Du vill ha en loop på 8 takter.

```text
Tid per slag:  60 ÷ 120 = 0,5 s
Tid per takt:  4 × 0,5 = 2 s
Hela loopen:   8 × 2 = 16 s
```

Den exporterade filen ska vara exakt 16 sekunder. Är den längre kommer en liten tystnad vid varje upprepning.

Tänk också på tempo och tonart. Snabb, ljus musik säger något annat än långsam, mörk. Fyrvaktaren kan börja med några få, lugna toner och lägga på fler lager när stormen tilltar. Tekniken att bygga musik i lager kallas **adaptiv musik**, eftersom musiken anpassar sig till spelet. Du kan börja enkelt, med att byta låt mellan banor.

## Mixa ljud

Att **mixa** är att bestämma hur starka ljuden ska vara i förhållande till varandra. Ljudstyrka mäts i **decibel**, dB. Skalan är logaritmisk, det vill säga att lika steg i dB motsvarar lika stora förändringar i förhållande, inte i absolut mängd.

### Genomräknat exempel: decibel

En ändring i dB hänger ihop med ljudvågens styrka (amplitud) enligt:

```text
amplitud = 10^(dB ÷ 20)
```

| dB | Amplitud jämfört med full styrka |
|---:|---:|
| 0 | 1,00 |
| −3 | 0,71 |
| −6 | 0,50 |
| −20 | 0,10 |

Att sänka med cirka 6 dB halverar alltså amplituden. Det betyder inte att ljudet upplevs som hälften så starkt, örat fungerar inte så enkelt, men det ger en känsla för vad siffrorna gör.

I Godot används **ljudbussar**, kanaler som kan styras gemensamt. Skapa till exempel `Musik` och `Effekter`, så kan du ändra hela grupper samtidigt och ge spelaren volymreglage. Lägg musiken lägre, ofta flera dB under effekterna, så att viktiga ljud hörs. Testa på både hörlurar och högtalare, för det som är tydligt i hörlurar kan försvinna i bärbara datorers högtalare.

## Begrepp

- **Återkoppling:** spelets svar på det du gör.
- **Diegetiskt ljud:** ljud som finns i spelets värld.
- **Sampling:** att mäta ljud med jämna mellanrum.
- **Bitdjup:** hur noggrant varje mätning lagras.
- **Foley:** ljudeffekter gjorda med vardagliga föremål.
- **Loop:** ljud som upprepas utan avbrott.
- **BPM:** slag per minut.
- **Decibel:** logaritmisk enhet för ljudnivå.
- **Mixning:** att balansera ljudens styrka mot varandra.

## Koppling till projektet

I [2D-spelet](../projekt/2d-spel/README.md) krävs ljudeffekter och bakgrundsmusik. I [3D-spelet](../projekt/3d-spel/README.md) krävs ljud för rörelse, hopp, kollisioner eller insamling och musik eller ljud för atmosfär. Använd positionsberoende ljud i 3D med noden `AudioStreamPlayer3D`.

## Läs mer

- [Godot: importera ljud](https://docs.godotengine.org/en/stable/tutorials/assets_pipeline/importing_audio_samples.html)
- [Godot: ljudbussar](https://docs.godotengine.org/en/stable/tutorials/audio/audio_buses.html)
- [Godot: audio streams](https://docs.godotengine.org/en/stable/tutorials/audio/audio_streams.html)

[← Föregående](06-bild-och-animation.md) | [Innehåll](../README.md) | [Nästa →](08-granssnitt-och-upplevelse.md)
