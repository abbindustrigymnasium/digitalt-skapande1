# Kapitel 8: Gränssnitt och spelarens upplevelse

> **I det här kapitlet lär du dig**
> - hur du gör menyer och visning under spelets gång tydliga
> - hur du lär spelaren spela utan att skriva en lång text
> - hur återkoppling får ett spel att kännas bra
> - hur du gör spelet tillgängligt för fler, inklusive att räkna ut kontrast

Någon startar ditt spel. Hittar personen knappen? Förstår den vad som ska göras? Märker den att den just fått poäng? Allt det här räknas till **användarupplevelsen**, den samlade känslan av att använda något. Bra användarupplevelse märks sällan. Dålig upplevelse märks direkt.

## Spelets gränssnitt

Ett **gränssnitt** är den del av ett program som låter människor förstå det och styra det. I spel brukar man prata om:

- **Menyer:** startskärm, pausmeny, game over-skärm.
- **HUD** (heads-up display): information som visas under spelets gång, till exempel poäng och liv.
- **Diegetiska element:** information inuti spelets värld, till exempel att lampans låga blir mindre.

Det sista är särskilt spännande i ett skapande perspektiv. I stället för en mätare i hörnet kan själva världen berätta. I Fyrvaktaren behöver spelaren se hur mycket olja varje lampa har. En lösning är en stapel över varje lampa. En annan är att lågan krymper och flimrar. Den senare är vackrare men svårare att läsa. Du väljer, och kanske behövs båda.

Frågan du ska ställa är: **vilken information behöver spelaren, när, och var ska den komma ifrån?** Ta bort allt annat.

### Principer för tydliga gränssnitt

Forskaren Jakob Nielsen har formulerat tio tumregler för användbarhet, ofta kallade heuristiker. Några är särskilt användbara för spel:

| Princip | I spelet |
|---|---|
| Visa vad som händer | Knappen ändras när du håller musen över den |
| Använd spelarens språk | "Spela" i stället för "Initiera session" |
| Var konsekvent | Samma knapp betyder samma sak i alla menyer |
| Förebygg fel | "Vill du verkligen avsluta?" vid viktiga val |
| Låt spelaren backa | Det ska alltid gå att gå tillbaka från en meny |

Godot har noder för gränssnitt under `Control`, till exempel `Label` för text, `Button` för knappar och `TextureProgressBar` för mätare. Lägg gärna HUD:en i ett `CanvasLayer` så att den stannar på plats när kameran rör sig. Med **ankare** (anchors) håller du elementen på rätt plats även när fönstret ändrar storlek. Ett `Theme` samlar typsnitt och färger på ett ställe så att hela spelet ser enhetligt ut.

## Lär spelaren spela

En genomgång med en stor textruta innan spelet börjat läser nästan ingen. Tre bättre sätt:

1. **Lär genom banan.** Första rummet kan bara lösas genom att hoppa, så spelaren lär sig det.
2. **Visa inte alla regler samtidigt.** Lägg till ett nytt moment i taget.
3. **Visa kontrollen när den behövs.** Texten "E: Häll i olja" när spelaren står vid lampan.

Spelet introducerar saker i en trygg situation, där spelaren kan misslyckas utan att det kostar något. Sedan prövas det i en svårare situation.

## Återkoppling och känsla

**Återkoppling** är allt spelet gör för att svara på det du gör. I spelvärlden pratar man om "game feel" eller "juice": små effekter som gör att en handling känns tillfredsställande. Det är ofta skillnaden mellan ett spel som fungerar och ett som känns bra.

| Handling | Enkel version | Med återkoppling |
|---|---|---|
| Plocka upp olja | Siffra ändras | Kannan blinkar, ljud, siffran hoppar till |
| Tända lampa | Lampan tänds | Ljuset ökar mjukt, vågor av ljus, en ton |
| Bli träffad | Liv minskar | Skärmen skakar kort, röd blink, ljud |

En tumregel är att kombinera två eller tre kanaler: bild, ljud och rörelse. Var dock försiktig med starka blinkningar och skärmskakningar, av anledningar som kommer härnäst.

## Tillgänglighet

**Tillgänglighet** handlar om att så många som möjligt ska kunna använda det du gjort, oavsett funktionsvariation. Det som hjälper vissa spelare hjälper ofta alla. Webbplatsen [Game Accessibility Guidelines](https://gameaccessibilityguidelines.com/) samlar konkreta råd. Några enkla att börja med:

- **Text:** tillräckligt stor, tydligt typsnitt, kontrast mot bakgrunden.
- **Färg:** använd aldrig färg som enda signal. En farlig lampa kan både vara röd och blinka.
- **Kontroller:** låt spelaren styra med både piltangenter och WASD, helst också ändra knapparna. Fler kontrollalternativ hjälper fler.
- **Svårighet:** erbjud en lättare nivå, längre tid eller paus.
- **Ljud:** viktig information ska inte bara finnas som ljud. Volymreglage för musik och effekter separat.
- **Blinkande bilder:** starka blinkningar kan vara besvärande eller farliga för vissa. Undvik dem eller ha ett val att stänga av dem.

Knapparna ska också gå att nå med tangentbord eller handkontroll. Ge en knapp fokus när menyn öppnas, så kan spelaren använda pilar och Enter direkt:

```gdscript
func _ready():
    $StartKnapp.grab_focus()
```

### Genomräknat exempel: kontrast

Hur vet du om texten går att läsa? Webbens tillgänglighetsriktlinjer WCAG har ett mätbart mått, **kontrastförhållande**. Det är byggt för webben, men räknesättet går bra även i spel. Riktlinjen är minst 4,5:1 för vanlig text och 3:1 för stor text.

Först beräknas varje färgs **relativa luminans** *L*, ett mått på hur ljus färgen uppfattas. Varje färgkanal (röd, grön, blå) omvandlas till värdet *c* mellan 0 och 1, och sedan:

```text
Om c ≤ 0,03928:  lin = c ÷ 12,92
Annars:          lin = ((c + 0,055) ÷ 1,055) ^ 2,4
L = 0,2126 × R_lin + 0,7152 × G_lin + 0,0722 × B_lin
Kontrast = (L_ljusast + 0,05) ÷ (L_mörkast + 0,05)
```

Vi provar med gul text `#FFD166` på mörkblå bakgrund `#1B263B`. Med formeln ovan blir luminansen:

```text
L_gul ≈ 0,678
L_blå ≈ 0,019
Kontrast = (0,678 + 0,05) ÷ (0,019 + 0,05) ≈ 10,5
```

Kontrasten 10,5:1 klarar kravet med god marginal. Grå text `#777777` på mörkgrå bakgrund `#333333` ger däremot:

```text
L_grå ≈ 0,185
L_mörk ≈ 0,033
Kontrast = (0,185 + 0,05) ÷ (0,033 + 0,05) ≈ 2,8
```

Det klarar inte ens gränsen för stor text. Texten skulle gå att läsa på din bra skärm hemma, men inte alls lika bra på en dålig projektor. Du behöver inte räkna för hand, [WebAIM:s kontrastverktyg](https://webaim.org/resources/contrastchecker/) räknar åt dig, men det är bra att veta vad siffran betyder.

## Begrepp

- **Användarupplevelse:** den samlade upplevelsen av att använda något.
- **Gränssnitt:** det som låter människor förstå och styra ett program.
- **HUD:** information som syns på skärmen under spelets gång.
- **Diegetiskt gränssnitt:** information som finns inuti spelets värld.
- **Heuristik:** tumregel, här om vad som gör något lätt att använda.
- **Återkoppling:** spelets svar på en handling.
- **Tillgänglighet:** att fler kan använda något, oavsett funktionsvariation.
- **Kontrastförhållande:** mått på skillnaden i ljushet mellan text och bakgrund.

## Koppling till projektet

I båda projekten krävs startskärm och game over-skärm, och HUD är ett bra tillägg. I [3D-spelet](../projekt/3d-spel/README.md) ska du dessutom arbeta med tillgänglighet, till exempel kontrast, textstorlek och kontroller, och värdera det i din plan. I [2D-spelet](../projekt/2d-spel/README.md) räcker tydliga menyer och kontroller som en början.

## Läs mer

- [Game Accessibility Guidelines](https://gameaccessibilityguidelines.com/)
- [WCAG 2.1: kontrast](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html)
- [Nielsens tio heuristiker](https://www.nngroup.com/articles/ten-usability-heuristics/)
- [Godot: UI](https://docs.godotengine.org/en/stable/tutorials/ui/index.html)

[← Föregående](07-ljud-och-musik.md) | [Innehåll](../README.md) | [Nästa →](09-gestalta-i-3d.md)
