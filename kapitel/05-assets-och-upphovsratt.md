# Kapitel 5: Assets, upphovsrätt och etik

> **I det här kapitlet lär du dig**
> - vad upphovsrätten skyddar och vilka rättigheter en skapare har
> - hur Creative Commons-licenser fungerar
> - hur du hittar assets och redovisar dem på rätt sätt
> - att tänka över etiska val när du skapar digitalt

Innan du lägger in den första bilden i spelet behöver du veta om du får. Det går att hitta nästan vad som helst på nätet, men att du hittat något betyder inte att du får använda det. Samtidigt finns det enorma samlingar av material som skaparna frivilligt har delat med sig av. Kan du läsa en licens har du tillgång till dem.

I kursen betyder **assets** allt material som ett spel består av utöver koden: bilder, ljud, musik, typsnitt och 3D-modeller.

## Upphovsrätt i korthet

**Upphovsrätt** är den rätt som en skapare automatiskt får till sitt verk. Du behöver inte ansöka om den, och verket behöver inte märkas med något tecken. Den gäller bland annat musik, texter, bilder, film, datorprogram och konstverk. Skyddet gäller om verket är tillräckligt originellt, ett krav som brukar kallas verkshöjd. Fotografier skyddas även om de är enkla.

Enligt svensk lag har skaparen, **upphovspersonen**, två sorters rättigheter:

| Rättighet | Innebär | Exempel |
|---|---|---|
| Ekonomisk rätt | Bestämmer vem som får göra kopior och visa verket för allmänheten | Du får inte lägga en känd låt i ditt spel utan tillstånd |
| Ideell rätt | Ska namnges på det sätt som god sed kräver, och verket får inte ändras eller användas på ett kränkande sätt | Du får inte låtsas att någon annans bild är din |

Skyddet gäller som huvudregel till och med det sjuttionde året efter upphovspersonens död. Den ekonomiska rätten kan säljas eller licensieras till andra, men den ideella rätten är personlig.

Du kan läsa mer i [upphovsrättslagen](https://www.riksdagen.se/sv/dokument-och-lagar/dokument/svensk-forfattningssamling/lag-1960729-om-upphovsratt-till-litterara-och_sfs-1960-729/) och i Patent- och registreringsverkets (PRV) [förklaring av upphovsrätt](https://www.prv.se/sv/upphovsratt/om-upphovsratt/). Boken ger en översikt och är inte juridisk rådgivning.

### Vad är inte skyddat?

Enligt PRV har en upphovsperson inte ensamrätt till tankar, principer, fakta och idéer. Att inspireras är alltså tillåtet, men att plagiera är det inte. Den stora frågan är om det nya är för likt originalet, och vid en tvist är det en domstol som avgör.

I spel kan det översättas ungefär så här:

| Går bra | Risk |
|---|---|
| Idén att bära saker mellan punkter | Kopiera bilderna från ett befintligt spel |
| Genren plattformsspel | Använda spelets musik eller ljudeffekter |
| Att låna en stämning och skriva egna figurer | Använda kända figurer, namn eller logotyper |

Namn och logotyper kan dessutom vara skyddade som **varumärken**. I kursen får du återskapa ett känt spel, och det är ett bra sätt att lära sig. Men bilder, musik, figurer och namn ska du byta ut, eller ha rätt att använda. Vill du publicera spelet offentligt blir det ännu viktigare.

## Creative Commons och fria licenser

En **licens** är ett tillstånd från skaparen som säger vad andra får göra. **Creative Commons**, förkortat CC, är en familj av färdiga licenser som många använder. De byggs upp av fyra villkor:

| Villkor | Betyder |
|---|---|
| BY | Du måste ange vem som gjort verket |
| SA | Bearbetningar måste delas under samma villkor |
| NC | Bara icke-kommersiellt bruk |
| ND | Du får inte dela bearbetade versioner |

Av dem byggs sex licenser, till exempel CC BY och CC BY-NC-SA. Dessutom finns **CC0**, där skaparen avstår så mycket av sina rättigheter som lagen tillåter. CC0-material kan du i praktiken använda fritt.

### Var hittar man material?

| Källa | Innehåll | Licens |
|---|---|---|
| [Kenney](https://kenney.nl/assets) | Grafik, ljud, 3D | Enligt webbplatsen CC0 |
| [OpenGameArt](https://opengameart.org/) | Grafik, ljud, musik | Varierar per verk, läs alltid |
| [Freesound](https://freesound.org/) | Ljud | CC0, CC BY eller CC BY-NC och några äldre licenser |
| [Godot Asset Library](https://godotengine.org/asset-library/asset) | Tillägg och resurser till Godot | Varierar per resurs |

Licenser kan ändras, och uppgifter kan vara felaktiga. Läs alltid licenstexten vid den fil du faktiskt laddar ner. "Gratis" betyder inte alltid "fri att använda", och "gratis att ladda ner" betyder inte alls att licensen tillåter det du vill göra.

### AI-genererat material

Enligt PRV krävs en människa som gjort fria kreativa val för att upphovsrätt ska uppstå. En bild som helt framställts med ett AI-verktyg utifrån en textinstruktion har därför enligt PRV ingen upphovsrätt, även om tjänstens användarvillkor kan begränsa hur du får använda den. Bearbetar du bilden kraftigt kan det se annorlunda ut, och den bedömningen görs av domstol. PRV påpekar också att du själv ansvarar om en AI-bild gör intrång i någon annans verk.

Det här området förändras snabbt. Fråga läraren vad som gäller i projektet, och skriv alltid i loggen och krediterna om du använt AI, och hur.

## Kreditera rätt

Att **kreditera** är att ange vem som gjort något. I det här spelet samlar du det i en fil, `KREDITER.md`, och visar krediterna i spelet, till exempel på en särskild skärm. Creative Commons föreslår att du anger titel, upphovsperson, källa och licens.

### Genomgånget exempel: en krediteringslista

Fyrvaktaren använder fyra assets. Så här kan filen se ut:

```markdown
# Krediter

## Eget material
All grafik för figurer och miljö samt spelets musik är gjort av skaparen av spelet.

## Lånat material
| Asset | Titel | Upphovsperson | Källa | Licens | Ändringar |
|---|---|---|---|---|---|
| Vind | "Exempelvind" | Exempelanvändare | länk till filens sida | CC BY 4.0 | Klippt och tonad ner |
| Båt | "Båt, lågpoly" | Exempelskapare | länk till filens sida | CC0 | Inga |
```

Titlarna ovan är påhittade. Gör en sådan rad **samma stund** som du hämtar en fil, för efteråt är det nästan omöjligt att hitta tillbaka. Skriv också ut om du har ändrat något.

### Genomgånget exempel: får jag använda den?

Du vill lägga ditt spel gratis på en publik sida. Hur är det med de här filerna?

| Fil | Licens | Får du? | Varför |
|---|---|---|---|
| Ljud från Freesound | CC0 | Ja | Inga villkor |
| Musik från OpenGameArt | CC BY | Ja, om du krediterar | BY kräver namn |
| Grafik | CC BY-NC | Ja, om du krediterar och spelet inte säljs | BY kräver namn och NC förbjuder kommersiellt bruk |
| Grafik från ett känt spel | Ingen angiven | Nej | Upphovsrätten gäller automatiskt |
| Låt från en streamingtjänst | Ingen angiven | Nej | Låten är skyddad och att strömma den ger ingen rätt att återanvända den |

Tar du ut en avgift eller tänker sälja spelet ändras svaret på NC-raden. Kom också ihåg att en fil med villkoret ND inte får spridas i ändrad version.

## Etik och hållbarhet

Att kunna något tekniskt betyder inte att man bör göra det. Som skapare har du ansvar för hur verket påverkar människor. Det handlar om att handla klokt, inte bara lagligt.

- **Representation.** Vem syns i spelet, och hur? Lätt tillgängliga mallar och AI-verktyg kan upprepa stereotyper. Fundera på vilken bild av människor du sprider.
- **Innehåll.** Våld, skräck och språk ska passa den målgrupp du valt.
- **Manipulativ design.** Spel kan pressa spelare med nedräkningar, falska erbjudanden och belöningar som liknar spel om pengar. Fråga dig om din design hjälper spelaren eller utnyttjar spelaren.
- **Andras arbete.** Bakom varje asset finns en människa. Att kreditera är ett sätt att visa respekt, och det gäller även material där det inte är lagkrav.
- **Personuppgifter.** Om du filmar eller spelar in någon under ett test ska den personen veta om det och ha sagt ja. Visa inte upp inspelningar av andra utan tillstånd. Integritetsskyddsmyndigheten [IMY](https://www.imy.se/verksamhet/dataskydd/) beskriver reglerna för personuppgifter.
- **Hållbarhet.** Digitala verk använder energi och hårdvara. Onödigt stora texturer och filer kräver mer av datorerna. Ett spel som går bra på en äldre dator håller längre och når fler.

Skolverket lyfter fram just den här sortens frågor i ämnets syfte. Ta upp dem i din dokumentation när du gör val som påverkar andra.

## Begrepp

- **Assets:** bilder, ljud, musik, typsnitt och modeller som ingår i ett spel.
- **Upphovsrätt:** den automatiska rätten till ett verk du skapat.
- **Ekonomisk rätt:** rätten att bestämma om kopiering och spridning.
- **Ideell rätt:** rätten att namnges och att inte få sitt verk kränkt.
- **Licens:** tillstånd som anger vad andra får göra.
- **CC0:** skaparen avstår från sina rättigheter så långt det går.
- **Kreditera:** att ange vem som gjort något.
- **Varumärke:** kännetecken som skiljer ett företags varor från andras, till exempel ett namn eller en logotyp.

## Koppling till projektet

I både [2D-spelet](../projekt/2d-spel/README.md) och [3D-spelet](../projekt/3d-spel/README.md) gäller att koden inte får hämtas färdig från nätet. Assets är en annan fråga: 3D-projektet nämner färdiga assets som ett alternativ, och 2D-guiden tar inte upp det, så fråga läraren om du vill använda lånat material där. Starta `KREDITER.md` första dagen och lägg till en rad varje gång du hämtar något.

## Läs mer

- [Creative Commons: licenserna förklarade](https://creativecommons.org/share-your-work/cclicenses/)
- [Creative Commons: rekommendationer för kreditering](https://wiki.creativecommons.org/wiki/Recommended_practices_for_attribution)
- [PRV: upphovsrätt på AI-bilder](https://www.prv.se/sv/upphovsratt/for-anvandare/upphovsratt-pa-ai-bilder/)
- [PRV: frågor och svar om upphovsrätt](https://www.prv.se/sv/upphovsratt/om-upphovsratt/fragor-och-svar-om-upphovsratt/)

[← Föregående](04-verktyg-och-samarbete.md) | [Innehåll](../README.md) | [Nästa →](06-bild-och-animation.md)
