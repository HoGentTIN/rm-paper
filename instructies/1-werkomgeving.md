# Fase 1. Opzetten werkomgeving

In deze cursus maak je gebruik van verschillende softwarepakketten en tools. In deze fase installeren we de nodige applicaties en maken de nodige configuratie-aanpassingen om efficiënt te kunnen werken.

## Installatie software

Dit heb je nodig:

- Een Git client ([Git CLI](https://git-scm.com), [Gitkraken](https://git-scm.com), ...)
- Een LaTeX-distributie:
    - Windows: [MikTeX](https://miktex.org) of [TeX live](https://www.tug.org/texlive/) (aanbevolen in combinatie met VS Code)
    - MacOS X: [MacTeX](https://www.tug.org/mactex/)
    - Linux: [TeX live](https://www.tug.org/texlive/))
- Een LaTeX IDE of editor met ondersteuning voor LaTeX:
    - [Texstudio](https://www.texstudio.org) is een volledige IDE, specifiek voor LaTeX
    - [Visual Studio Code](https://code.visualstudio.com) heeft ook zeer goede ondersteuning, maar vraagt wel wat werk [om goed te configureren](https://dev.to/ucscmozilla/how-to-create-and-compile-latex-documents-on-visual-studio-code-3jbk)
- [JabRef](https://www.jabref.org), een bibliografische databank specifiek voor LaTeX
- Een editor met ondersteuning voor Markdown is ook handig
    - [Visual Studio Code](https://code.visualstudio.com) heeft uitstekende ondersteuning (o.a. HTML preview met `Ctrl+Shift+V`)
    - [Typora](https://typora.io)

### Windows

We raden aan om de [Chocolatey Package Manager](https://chocolatey.org/install) te gebruiken voor het beheren van geïnstalleerde applicaties.

Open een Powershell of CMD terminal als Administrator en selecteer uit onderstaande commando's de specifieke packages die je wil installeren. Merk op dat de tekst volgend op het hekje (`#`) commentaar is en dus niet moet overgetikt worden!

```powershell
choco install -y git        # CLI client
choco install -y gitkraken  # Grafische Git client (optioneel)
choco install -y miktex     # LaTeX distributie
choco install -y texlive    # Alternatieve LaTeX distro (kies 1 van de 2!)
choco install -y texstudio  # Complete LaTeX IDE
choco install -y vscode     # Visual Studio Code (optioneel)
choco install -y JabRef     # Bibliografische databank
choco install -y typora     # Markdown editor (optioneel)
```

### MacOS X

We raden aan om de [Homebrew package manager](https://brew.sh/) te gebruiken voor het beheren van geïnstalleerde applicaties. *Let op: deze werkwijze is niet recentelijk getest, feedback welkom!*

Open een Terminal en selecteer uit ondersttaande commando's de specifieke packages die je wil installeren. Merk op dat de tekst volgend op het hekje (`#`) commentaar is en dus niet moet overgetikt worden!

```bash
brew install git               # CLI client
brew install --cask gitkraken  # Grafische Git client (optioneel)
brew install --cask mactex     # LaTeX distributie
brew install --cask texstudio  # Complete LaTeX IDE
brew install --cask visual-studio-code # VS Code (optioneel)
brew install --cask jabref     # Bibliografische databank
brew install --cask typora     # Markdown editor (optioneel)
```

### Linux (Debian/Ubuntu)

Linux-gebruikers weten dat er verschillen zijn bij het installeren van software, afhankelijk van de distributie. Hier volgen instructies voor distributies uit de Debian-familie (Ubuntu, Mint, enz.). Voor andere distributies kunnen het commando en package-namen verschillen, maar meestal weten jullie wel hoe dat precies moet.

```bash
sudo apt install git        # CLI client
sudo apt install texlive    # LaTeX distributie
sudo apt install texstudio  # Complete LaTeX IDE
sudo apt install jabref     # Bibliografische databank

wget https://release.gitkraken.com/linux/gitkraken-amd64.deb
sudo dpkg -i gitkraken-amd64.deb  # Grafische Git client (optioneel)

# Download eerst de .deb package van https://code.visualstudio.com/Download
sudo dpkg -i ./code_*.deb   # VS Code
```

De **TeX live** distributie is enorm uitgebreid en werd onderverdeeld in verschillende packages. `texlive` is de basisinstallatie, `texlive-full` de complete distributie (incl. onderdelen die jij nooit nodig zult hebben). Je kan dus kiezen: ofwel installer je TeX live volledig, ofwel de basisinstallatie, aangevuld met de extra's die je nodig hebt, bv. `texlive-science`, `texlive-xetex`, enz. Voor een volledig overzicht van wat beschikbaar is kan je `apt search texlive` uitproberen. Je zal verder moeten ondervinden wat je precies nodig hebt en wat je eventueel nog extra moet installeren.

## Configuratie Git, Github

Normaal gezien heb je intussen al een Github-account en een persoonlijke Github-repository aangemaakt via de Github Classroom link die je op Chamilo kon vinden.

### Basisconfiguratie

Voordat je Git gaat gebruiken op je laptop is het belangrijk om enkele **basisinstellingen** goed te configureren. Als je dit niet doet, worden jouw commits niet altijd correct onder jouw naam naar Github opgeladen. Vooral bij groepswerk is dit problematisch, want jouw bijdrage is dan niet zichtbaar!

- Koppel je **HoGent-emailadres** aan je Github account (je kan meerdere adressen registreren). Op die manier kan je aanspraak maken op het [Github student developer pack](https://education.github.com/pack), wat je gratis toegang geeft tot een aantal in principe betalende producten en diensten.
- [Genereer een SSH-sleutelpaar](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) als je dit nog niet gedaan hebt en [registreer het op Github](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).
- Stel je naam en (HOGENT-)emailadres in. Via de CLI kan dit zo:

    ```console
    git config --global user.name "Pieter Stevens"
    git config --global user.email pieter.stevens.u12345@student.hogent.be
    git config --global github.user PieterStevens
    ```

- Pas [enkele basisinstellingen](https://git-scm.com/book/nl/v2/Git-aanpassen-Git-configuratie) aan:

    ```bash
    git config --global push.default simple
    git config --global pull.rebase true
    git config --global rebase.autoStash true
    git config --global init.defaultBranch main
    ```

    Ga eens in de [documentatie](https://git-scm.com/book/nl/v2/Git-aanpassen-Git-configuratie) zoeken wat deze commando's precies doen.

- Maak een kloon van je Github-repo op je laptop.

### Aanbevelingen

We gaan er van uit dat je met Git/Github kan werken! Enkele aanbevelingen.

- **Vermijd** werken via de **Github webinterface** voor het aanpassen/toevoegen van bestanden. Maak een lokale kloon van je repository op je laptop en werk via de command-line of met een goede grafische client.
- **Commit en push** zo vaak mogelijk!
- Creëer [**atomaire commits**](https://dev.to/cbillowes/why-i-create-atomic-commits-in-git-kfi). Je github-repository is een backup waarmee je kan vermijden dat je werk verloren gaat.
- Voorzie je commits van een duidelijke beschrijving in de [**commit messsage**](https://cbea.ms/git-commit/).
- De standaard voor opgemaakte tekst op Github is [Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax). Neem de tijd om correcte **Markdown-documenten** te leren schrijven en hoe de opmaak te bekijken (in een editor of op Github).

## LaTeX

LaTeX bestaat al enkele decennia. Waar het vroeger enkel mogelijk was om in een LaTeX-document ASCII-tekst te gebruiken, is het nu volledig UTF-8 compatibel. De meeste LaTeX-gerelateerde tools hebben in hun basisinstellingen echter nog steeds die oorspronkelijke werkwijze geconfigureerd. Enkele aanpassingen zijn dus nodig!

### TeXStudio configureren

Controleer deze instellingen via menu-item *Options > Configure TeXstudio*

- Build:
    - Default Compiler: **XeLaTeX** (UTF-8 compatibel, mogelijkheid om TTF-lettertypes te gebruiken, enz.) in plaats van PDFLaTeX (enkel ASCII, PostScript lettertypes, enz.)
    - Default Bibliography tool: **`biber`** (UTF-8 compatibel, ondersteuning voor APA-referenties, ...) in plaats van `bibtex` (enkel ASCII, geep APA-referenties, ...)
- Commands:
    - XeLaTeX: `xelatex -synctex=1 -interaction=nonstopmode -shell-escape %.tex` (voeg de optie `-shell-escape` toe)
- Editor:
    - Indentation mode: *Indent and Unindent Automatically*
    - Replace Indentation Tab by Spaces: *Aanvinken*
    - Replace Tab in Text by spaces: *Aanvinken*
    - Replace Double Quotes: *English Quotes: ``''*

Om te testen of TeXStudio goed werkt, kan je het sjabloon voor de paper ( `paper/FamilienaamVoornaamJaarRM.tex`) gebruiken. Verander eerste de bestandsnaam in je eigen naam (familienaam eerst) en het jaartal (bv. `DeSmetJan2022RM.tex`).

Kies *Tools > Build & View* (of functietoets `F5`) om deze te compileren in een PDF-bestand. **Let op!** Als het resulterende PDF-bestand geen bibliografie bevat, moet je die nog apart compileren. Dit kan via het menu *Tools > Bibliography* of functietoets `F8`. Daarna doe je op nieuw *Build & View*.

Veel functionaliteiten van LaTeX zitten in aparte packages die niet noodzakelijk standaard geïnstalleerd zijn. De eerste keer dat je een bestand compileert, is het dan ook mogelijk dat er extra packages moeten gedownload worden. MiKTeX op Windows zal een pop-up tonen om je toestemming te vragen, bevestig dit. De eerste keer compileren kan enkele minuten duren zonder dat je feedback krijgt over wat er gebeurt. Even geduld, dus. Op Linux werkt dit misschien niet en moet je opzoeken welke extra packages `texlive` je nog moet installeren voor de gewenste functionaliteit.

Indien er zich fouten voordoen bij de compilatie, kan je onderaan in het tabblad *Log* een overzicht krijgen van de foutboodschappen. Wanneer je bij je lector hulp vraagt, is het belangrijk om de **exacte foutboodschap** mee te geven. Dat kan het makkelijkst door het tabblad *Logbestand* te selecteren en de gehele inhoud te kopiëren.

### Visual Studio Code

VS Code is een krachtige teksteditor met zeer goede ondersteuning voor tientallen programmeer- en scriptingtalen en gestructureerde tekstformaten als HTML, Markdown, enz. Ook voor LaTeX zijn er goede plugins. Als je al gewend bent om VS Code te gebruiken, dan kan je het even goed ook gebruiken voor LaTeX. Het nadeel is misschien wel dat het wat complexer is om Code goed te configureren, in die mate zelfs dat het ons hier te ver zou leiden om een volledig stappenplan te voorzien.

Installeer in elk geval [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) van James Yu. Pas de configuratie aan zodat de `xelatex` compiler gebruikt wordt in plaats van `pdflatex`. Lees [de documentatie](https://github.com/James-Yu/LaTeX-Workshop/wiki) voor meer info en inspireer je eventueel op [dit VS Code configuratiebestand](https://github.com/bertvv/dotfiles/blob/master/.config/Code/User/settings.json) om LaTeX Workshop in te stellen.

### JabRef

[JabRef](http://www.jabref.org/) is een GUI voor het bewerken van BibTeX-bestanden, een soort database van bronnen uit de wetenschappelijke of vakliteratuur voor een LaTeX-document. De interface en instellingen veranderen nogal eens tussen versies, dus het is mogelijk dat deze instructies niet meer exact werken.

Binnen de LaTeX-wereld is er een apart subsysteem voor het correct opmaken van een referentielijst of bibliografie. Het "oude" systeem heet BibTeX en is vaak de standaard in LaTeX-editors. Het sjabloon voor de paper en ook dat voor de bachelorproef zijn echter gebaseerd op een modernere vervanger, BibLaTeX/biber. Pas Jabref aan om standaard het laatste te gebruiken.

- Kies in het menu voor *Options > Preferences > General* en kies onderaan voor de optie "Default bibliography mode" voor "biblatex".
- Kies in het *Preferences*-venster voor de categorie *File* en geef een directory op voor het bijhouden van PDFs van de gevonden bronnen onder *Main file directory*. Het is heel interessant om de gevonden artikels te downloaden en onder die directory bij te houden. Nog beter is om als naam van het bestand de BibTeX key te nemen (typisch naam van de eerste auteur + jaartal, bv. Knuth1998.pdf). Je kan het bestand dan makkelijk openen vanuit Jabref.

## Checklist

- [ ] De nodige software is geïnstalleerd.
- [ ] De basisinstellingen van Git zijn waar nodig aangepast. Bij een commit naar Github is duidelijk wie de auteur is.
- [ ] TeXstudio of VS Code zijn geconfigureerd voor gebruik.
- [ ] Het sjabloon compileert zonder fouten, in de PDF is ook de (voorbeeld-)bibliografie opgenomen.
