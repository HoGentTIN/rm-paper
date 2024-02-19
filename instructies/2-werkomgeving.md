# Fase 2. Opzetten LaTeX-werkomgeving

In deze cursus maak je gebruik van verschillende softwarepakketten en tools. In deze fase installeren we de nodige applicaties en maken de nodige configuratie-aanpassingen om efficiënt te kunnen werken.

## Installatie software

Om de nodige software te installeren voor LaTeX, volg je de instructies in onze [LateX-gids](https://hogenttin.github.io/latex-hogent-gids/). Zorg er daarnaast ook voor dat je een Git client en een Github account hebt (heb je normaal al voor andere vakken gebruikt).

### Basisconfiguratie Git, Github

Voordat je Git gaat gebruiken op je laptop is het belangrijk om enkele **basisinstellingen** goed te configureren. Als je dit niet doet, worden jouw commits niet altijd correct onder jouw naam naar Github opgeladen. Vooral bij groepswerk is dit problematisch, want jouw bijdrage is dan niet zichtbaar! Je begeleiders kunnen dan ten onrechte besluiten dat je niet bijgedragen hebt tot het groepswerk.

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

- Maak een kloon van je Github-repo op je laptop en vul de tabel bovenaan het README.md-bestand aan met de correcte gegevens. Elk teamlid doet dit best apart om te controleren dat alles goed ingesteld is. Vermijd natuurlijk wel merge-conflicten! Commit, push naar Github en controleer of de wijzigingen correct op Github staan en dat de auteurs van de commits herkenbaar zijn.

### Aanbevelingen

We gaan er van uit dat je met Git/Github kan werken! Enkele aanbevelingen.

- **Vermijd** werken via de **Github webinterface** voor het aanpassen/toevoegen van bestanden. Maak een lokale kloon van je repository op je laptop en werk via de command-line of met een goede grafische client.
- **Commit en push** zo vaak mogelijk!
- Creëer [**atomaire commits**](https://dev.to/cbillowes/why-i-create-atomic-commits-in-git-kfi). Je github-repository is een backup waarmee je kan vermijden dat je werk verloren gaat.
- Voorzie je commits van een duidelijke beschrijving in de [**commit messsage**](https://cbea.ms/git-commit/).
- De standaard voor opgemaakte tekst op Github is [Markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax). Neem de tijd om correcte **Markdown-documenten** te leren schrijven en hoe de opmaak te bekijken (in een editor of op Github).
    - In VS Code kan je de plugins [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one) en [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) installeren om de ervaring van het schrijven van Markdown-documenten te verbeteren. Gebruik de shortcut `Ctrl+Shift+V` om een preview te zien van het document zoals het op Github zou gerenderd worden in HTML.
    - Er bestaan ook andere editors met ondersteuning voor Markdown, zoals [Typora](https://typora.io).

### LaTeX-installatie testen

Om te testen of LaTeX correct geïnstalleerd is, kan je het sjabloon voor de paper ( `voorstel/FamilienaamVoornaamJaarRM.tex`) gebruiken. Kopieer het bestand naar een nieuw bestand met daarin de naam/namen van de auteur(s) en het jaartal verwerkt, bv. `AkinDeSmet2024` of `DeSmet2022RM.tex`.

## Onderwerp uitschrijven

Als je in de vorige fase een definitief onderwerp gekozen hebt, kan je in dat nieuwe bestand de inleiding van de paper schrijven.

## Checklist

- [ ] De nodige software is geïnstalleerd: Git client, LaTeX compiler, LaTeX editor, JabRef.
- [ ] De basisinstellingen van Git zijn waar nodig aangepast. Bij een commit naar Github is duidelijk wie de auteur is.
- [ ] TeXstudio of VS Code zijn geconfigureerd voor gebruik.
- [ ] Het sjabloon compileert zonder fouten, in de PDF is ook de (voorbeeld-)bibliografie opgenomen.
- [ ] De inleiding van jullie onderwerp is uitgeschreven.
