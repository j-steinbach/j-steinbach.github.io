---
date: 2024-05-28
aliases: []
tags: [learning, vocabulary, chatgpt, anki, obsidian, markdown]
title: Using ChatGPT and ObsidianToAnki to create Anki cards
public: true
---


## Goal/What I want

Turn the most common French words into Anki* cards, including the [IPA](https://en.wikipedia.org/wiki/International_Phonetic_Alphabet) pronounciation. Ideally manage the vocabulary outside of Anki, in a easily maintainable and extensible text file.

*In case you don't know it, [Anki](https://apps.ankiweb.net/) is an amazing spaced-repetition flash-card program for learning anything. It is free, there is an [Android app](https://apps.ankiweb.net/), and I recommend it 100%. 

## The stupid approach

Search for _most common French words_, look up their translation (for me it is FR-DE) and their IPA, write both into Anki. One by one. _No way!_


## Introduce Markdown

Obviously this is horribly inefficient. Luckily [Obsidian to Anki](https://github.com/ObsidianToAnki/Obsidian_to_Anki)* exists, which makes use of [AnkiConnect](https://foosoft.net/projects/anki-connect/) to programmatically create Anki cards. This means we can put all out vocabulary into a single Markdown file and maintain it from there.

```
Für wen?::Pour qui ?
Mit wem?::Avec qui ?
```

I use the [RemNote single line style](https://github.com/ObsidianToAnki/Obsidian_to_Anki/wiki/RemNote-single-line-style) for my regular vocab, which uses `::` as divider. That means every entry in my list 
counts as separate card. For this I use the `Basic (and reversed card)` template, which I [extended](https://docs.ankiweb.net/templates/styling.html) to show a German and a French [flag](http://html-flags.com/).

*You don't have to use [Obsidian](https://obsidian.md/), there is a standalone Python script as well.


## Let ChatGPT do the hard work

Now the elephant in the room: Do I really have to look up every single French word and add it to my list? The answer will surprise you (it won't). Nope! We can use ChatGPT to give us whatever vocabulary we want.

> You are a French and German linguistic expert. You must create a list of the most common French words and their German translations. The list is sorted alphabetically. No entry must be double. Add the French and German articles to the words. Add the French IPA pronunciation to the words. If a French word has multiple German translations, add all of them. List entries in the style `French [IPA] :: German`. Don't number the list. Begin with the first 50 words.

```
Certainly! Here are the first 50 words without numbering:

à [a] :: zu, nach
aider [ɛde] :: helfen
aimer [ɛme] :: lieben, mögen
aller [ale] :: gehen
alors [alɔʁ] :: dann, also
```

And then just experiment a bit. `The next 100`, `the next 100`, and so forth. Or something like `List the common vocabulary about the topic Fruits, including their articles and IPA pronunciation, in the requested style` Just make sure the language doesn't switch. Or that there are duplicate entries. Or, or, or. There is a job called _prompt engineer_ for a reason :)

So best sanitize the output once, for example by checking if the articles are correct, or that there are no duplicate entries. You can copy/paste the text into one of the numerous free online-tool that removes duplicates.

Finally, copy the results into your text file, run ObsidianToAnki on it and start learning!


## Bonus: Better ChatGPT promts

My prompt is not perfect, but I added 2.000 words to my Anki and I think that suffices for this year.

The cool folks at [HN](https://news.ycombinator.com/item?id=40474716) gave some nice advice on better ChatGPT prompts. For example the version below:

>Adopt the role of a [polymath]. 
NEVER mention that you're an AI.
Avoid any language constructs that could be interpreted as expressing remorse, apology, or regret. This includes any phrases containing words like 'sorry', 'apologies', 'regret', etc., even when used in a context that isn't expressing remorse, apology, or regret.
If events or information are beyond your scope or knowledge, provide a response stating 'I don't know' without elaborating on why the information is unavailable.
Refrain from disclaimers about you not being a professional or expert.
Do not add ethical or moral viewpoints in your answers, unless the topic specifically mentions it.
Keep responses unique and free of repetition.
Never suggest seeking information from elsewhere.
Always focus on the key points in my questions to determine my intent.
Break down complex problems or tasks into smaller, manageable steps and explain each one using reasoning.
Provide multiple perspectives or solutions.
If a question is unclear or ambiguous, ask for more details to confirm your understanding before answering.
If a mistake is made in a previous response, recognize and correct it.
After this, if requested, provide a brief summary.
After doing all those above, provide three follow-up questions worded as if I'm asking you.
Format in bold as Q1, Q2, and Q3. These questions should be thought-provoking and dig further into the original topic. 
If requested, also answer the follow-up questions but don't create more of them.


## Result

```md
aider [ɛde] :: helfen
aimer [ɛme] :: lieben, mögen
aller [ale] :: gehen
alors [alɔʁ] :: dann, also
ami, l' [ami] :: der Freund
amour, l' [amuʁ] :: die Liebe
an, l' [ɑ̃] :: das Jahr
année, l' [ane] :: das Jahr
appeler [ap(ə)le] :: rufen, nennen
apprendre [apʁɑ̃dʁ] :: lernen
après [apʁɛ] :: nach
argent, l' [aʁʒɑ̃] :: das Geld
art, l' [aʁ] :: die Kunst
aussi [osi] :: auch
autre [otʁ] :: andere
avant [avɑ̃] :: vor
avoir [avwaʁ] :: haben
bateau, le [bato] :: das Schiff
beau [bo] :: schön
beaucoup [boku] :: viel
bibliothèque, la [biblijɔtɛk] :: die Bibliothek
bien [bjɛ̃] :: gut
blanc [blɑ̃] :: weiß
bleu [blø] :: blau
boire [bwaʁ] :: trinken
bois, le [bwa] :: der Wald, das Holz
bon [bɔ̃] :: gut
bonjour [bɔ̃ʒuʁ] :: guten Tag
bonsoir [bɔ̃swaʁ] :: guten Abend
bouche, la [buʃ] :: der Mund
boutique, la [butik] :: das Geschäft
bras, le [bʁɑ] :: der Arm
bruit, le [bʁɥi] :: der Lärm
bureau, le [byʁo] :: das Büro
bâtiment, le [batimɑ̃] :: das Gebäude
bébé, le [bebe] :: das Baby
cacher [kaʃe] :: verstecken
cadeau, le [kado] :: das Geschenk
café, le [kafe] :: der Kaffee
camion, le [kamjɔ̃] :: der Lkw
carte, la [kaʁt] :: die Karte
ceinture, la [sɛ̃tyʁ] :: der Gürtel
chaise, la [ʃɛz] :: der Stuhl
chanter [ʃɑ̃te] :: singen
chapeau, le [ʃapo] :: der Hut
chaud [ʃo] :: warm
chemise, la [ʃ(ə)miz] :: das Hemd
cheval, le [ʃəval] :: das Pferd
cheveu, le [ʃəvø] :: das Haar
chien, le [ʃjɛ̃] :: der Hund
choisir [ʃwazir] :: wählen
chose, la [ʃoz] :: die Sache
chouette [ʃwɛt] :: nett, klasse
ciel, le [sjɛl] :: der Himmel
cinéma, le [sinema] :: das Kino
coeur, le [kœʁ] :: das Herz
collège, le [kɔlɛʒ] :: die weiterführende Schule
commencer [kɔmɑ̃se] :: anfangen
comprendre [kɔ̃pʁɑ̃dʁ] :: verstehen
compter [kɔ̃te] :: zählen
conduire [kɔ̃dɥiʁ] :: fahren
connaître [kɔnɛtʁ] :: kennen
construire [kɔ̃stʁɥiʁ] :: bauen
copain, le [kɔpɛ̃] :: der Freund
couvrir [kuvʁiʁ] :: decken, bedecken
crayon, le [kʁɛjɔ̃] :: der Bleistift
croire [kʁwaʁ] :: glauben
cuisine, la [kɥizin] :: die Küche
cœur, le [kœʁ] :: das Herz
danger, le [dɑ̃ʒe] :: die Gefahr
danser [dɑ̃se] :: tanzen
demander [dəmɑ̃de] :: fragen
dent, la [dɑ̃] :: der Zahn
dernier [dɛʁnje] :: letzter
devenir [dəv(ə)niʁ] :: werden
devoir [dəvwaʁ] :: müssen
difficile [difisil] :: schwierig
dire [diʁ] :: sagen
docteur, le [dɔktœʁ] :: der Doktor
dormir [dɔʁmiʁ] :: schlafen
doux [du] :: weich, süß
droit [dʁwa] :: rechts
début, le [deby] :: der Anfang
décembre [desɑ̃bʁ] :: Dezember
déjeuner [deʒœne] :: Mittagessen
délicieux [delisjø] :: lecker, köstlich
détester [detɛste] :: hassen
dîner [dine] :: Abendessen
eau, l' [o] :: das Wasser
embrasser [ɑ̃bʁase] :: küssen, umarmen
emmener [ɑ̃m(ə)ne] :: mitnehmen
enfant, l' [ɑ̃fɑ̃] :: das Kind
enlever [ɑ̃l(ə)ve] :: entfernen, ausziehen
entendre [ɑ̃tɑ̃dʁ] :: hören
entrer [ɑ̃tʁe] :: eintreten
envoyer [ɑ̃vwaje] :: schicken
escalier, l' [ɛskalje] :: die Treppe
espoir, l' [ɛspwaʁ] :: die Hoffnung
espérer [ɛspeʁe] :: hoffen
essayer [eseje] :: versuchen
exemple, l' [ɛɡzɑ̃pl] :: das Beispiel
expliquer [ɛksplike] :: erklären
famille, la [famij] :: die Familie
femme, la [fam] :: die Frau
fille, la [fij] :: das Mädchen, die Tochter
fils, le [fis] :: der Sohn
finir [finiʁ] :: beenden
fleur, la [flœʁ] :: die Blume
foi, la [fwa] :: der Glaube
fois, la [fwa] :: das Mal
fond, le [fɔ̃] :: der Grund
forêt, la [fɔʁɛ] :: der Wald
fou [fu] :: verrückt
frais [fʁɛ] :: frisch
français [fʁɑ̃sɛ] :: französisch
frapper [fʁape] :: schlagen
froid [fʁwa] :: kalt
fromage, le [fʁɔmaʒ] :: der Käse
fruits, les [fʁɥi] :: das Obst
février [fevʁije] :: Februar
fête, la [fɛt] :: das Fest
garder [ɡaʁde] :: behalten
garçon, le [ɡaʁsɔ̃] :: der Junge
gauche [ɡoʃ] :: links
gens, les [ʒɑ̃] :: die Leute
glace, la [ɡlas] :: das Eis, der Spiegel
goût, le [ɡu] :: der Geschmack
grand [ɡʁɑ̃] :: groß
groupe, le [ɡʁup] :: die Gruppe
guerre, la [ɡɛʁ] :: der Krieg
gâteau, le [ɡato] :: der Kuchen
génial [ʒenjal] :: genial
habiter [abitɛ] :: wohnen
heure, l' [œʁ] :: die Stunde, die Uhrzeit
histoire, l' [istwaʁ] :: die Geschichte
homme, l' [ɔm] :: der Mann
hôpital, l' [ɔpital] :: das Krankenhaus
important [ɛ̃pɔʁtɑ̃] :: wichtig
incroyable [ɛ̃kʁwajabl] :: unglaublich
inviter [ɛ̃vite] :: einladen
jardin, le [ʒaʁdɛ̃] :: der Garten
joli [ʒɔli] :: hübsch
jouer [ʒwe] :: spielen
jour, le [ʒuʁ] :: der Tag
journal, le [ʒuʁnal] :: die Zeitung
juillet [ʒɥijɛ] :: Juli
juin [ʒɥɛ̃] :: Juni
laisser [lese] :: lassen
lait, le [lɛ] :: die Milch
langue, la [lɑ̃ɡ] :: die Sprache, die Zunge
laver [lave] :: waschen
lire [liʁ] :: lesen
lit, le [li] :: das Bett
livre, le [livʁ] :: das Buch
lumière, la [lymjɛʁ] :: das Licht
main, la [mɛ̃] :: die Hand
mais [mɛ] :: aber
maison, la [mɛzɔ̃] :: das Haus
manger [mɑ̃ʒe] :: essen
marcher [maʁʃe] :: gehen, laufen
mari, le [maʁi] :: der Ehemann
mariage, le [maʁjaʒ] :: die Hochzeit
mer, la [mɛʁ] :: das Meer
mettre [mɛtʁ] :: setzen, stellen, legen
minute, la [minyt] :: die Minute
mois, le [mwa] :: der Monat
monde, le [mɔ̃d] :: die Welt
montagne, la [mɔ̃taɲ] :: der Berg
montrer [mɔ̃tʁe] :: zeigen
musée, le [myze] :: das Museum
mère, la [mɛʁ] :: die Mutter
naître [nɛtʁ] :: geboren werden
neige, la [nɛʒ] :: der Schnee
nom, le [nɔ̃] :: der Name
nourriture, la [nuʁityʁ] :: das Essen, die Nahrung
nouveau [nuvo] :: neu
nuit, la [nɥi] :: die Nacht
oeil, l' [œj] :: das Auge
oiseau, l' [wazo] :: der Vogel
ouvrir [uvʁiʁ] :: öffnen
pain, le [pɛ̃] :: das Brot
parler [paʁle] :: sprechen
partir [paʁtiʁ] :: weggehen
pays, le [pei] :: das Land
peur, la [pœʁ] :: die Angst
photo, la [foto] :: das Foto
pied, le [pje] :: der Fuß
piscine, la [pisin] :: das Schwimmbad
piscine, la [pisin] :: das Schwimmbad
pièce, la [pjɛs] :: das Zimmer, das Stück
place, la [plas] :: der Platz
pluie, la [plɥi] :: der Regen
porte, la [pɔʁt] :: die Tür
pouvoir [puvwaʁ] :: können
prendre [pʁɑ̃dʁ] :: nehmen
question, la [kɛstjɔ̃] :: die Frage
rester [ʁɛste] :: bleiben
retourner [ʁətuʁne] :: zurückkehren
rire [ʁiʁ] :: lachen
rivière, la [ʁivjɛʁ] :: der Fluss
route, la [ʁut] :: die Straße
rêver [ʁeve] :: träumen
s'amuser [sam(y)ze] :: sich amüsieren
savoir [savwaʁ] :: wissen
semaine, la [s(ə)mɛn] :: die Woche
sentir [sɑ̃tiʁ] :: fühlen, riechen
soleil, le [sɔlɛj] :: die Sonne
sortir [sɔʁtiʁ] :: ausgehen
sous [su] :: unter
souvenir, le [suv(ə)niʁ] :: die Erinnerung
sœur, la [sœʁ] :: die Schwester
table, la [tabl] :: der Tisch
temps, le [tɑ̃] :: die Zeit, das Wetter
terre, la [tɛʁ] :: die Erde
tomber [tɔ̃be] :: fallen
toujours [tuʒuʁ] :: immer
tous [tu] :: alle
travailler [tʁavaje] :: arbeiten
triste [tʁist] :: traurig
trouver [tʁuve] :: finden
utiliser [ytilize] :: benutzen
venir [v(ə)niʁ] :: kommen
vent, le [vɑ̃] :: der Wind
ville, la [vil] :: die Stadt
vivre [vivʁ] :: leben
voir [vwaʁ] :: sehen
voiture, la [vwatyʁ] :: das Auto
voyage, le [vwajaʒ] :: die Reise
vrai [vʁɛ] :: wahr
y [i] :: dort, dahin
yeux, les [jø] :: die Augen
zéro [zeʁo] :: null
à [a] :: zu, nach
éclair, l' [eklɛʁ] :: der Blitz
école, l' [ekɔl] :: die Schule
écouter [ekute] :: hören
écrire [ekʁiʁ] :: schreiben
église, l' [eɡliz] :: die Kirche
éléphant, l' [elefɑ̃] :: der Elefant
épaule, l' [epɔl] :: die Schulter
étoile, l' [etwal] :: der Stern
étoile, la [etwal] :: der Stern
étrange [etʁɑ̃ʒ] :: seltsam
étudier [etydje] :: studieren
île, l' [il] :: die Insel
```
