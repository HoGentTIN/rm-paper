# Fase 4. Bibliografische databank, literatuurstudie

In deze fase verwerk je de gevonden bronnen tot een doorlopende inleidende tekst over het gekozen bachelorproefonderwerp. Dit is wellicht de fase waar het meeste tijd zal in kruipen.

Laat dit niet liggen, anders kom je in de problemen met de deadlines van opdrachten die meer naar het einde van het semester liggen!

- Open het bestand `paper/bibliografie.bib` met JabRef.
- Voeg alle gevonden bronnen toe aan de bibliografische databank. Let daarbij goed op dat:
    - Alle nodige informatie aanwezig is (cfr. tabblad Required Fields), bv.
        - Electronic/Online/WWW-bronnen moeten een "url" en "urldate" hebben!
        - Een Book moet een uitgever hebben;
        - Een Article moet een Journaltitle, jaargang en nummer hebben;
        - ...
    - Auteursnamen in het juiste formaat staan (`Familienaam, Voornaam and Familienaam, Voornaam and ...`)
    - Elke bron een unieke Bibtexkey heeft (typisch AuteursnaamJaartal, bv. Knuth1985)
    - Als je de PDF hebt, die opgeslagen wordt in de daartoe bestemde directory die je ingesteld hebt in JabRef. Verander de naam van de PDF in de Bibtexkey, dan kan je deze openen vanuit JabRef.
    - Hou ook extra informatie over de bron bij: de Abstract (inleidende paragraaf), sleutelwoorden, DOI-code, commentaar, enz.
- Schrijf een inleidende tekst over het door jou gekozen bachelorproefonderwerp, op basis van de door jou gevonden bronnen. Doe dit meteen in het , in de daarvoor bestemde sectie. Verwijs waar het gepast is naar de bronnen met het juiste LaTeX-commando:
    - `\autocite{Bibtexkey}` => (Auteur, jaartal)
    - `\textcite{Bibtexkey}` => Auteur (jaartal)
- Compileer het LaTeX-bestand regelmatig en controleer de uitvoer!
    - Is de tekst vlot leesbaar? Laat eventueel eens nalezen door iemand!
    - Zijn de referenties correct ingevoegd?
    - Is de bibliografie volledig? Let er op dat enkel bronnen waar effectief naar verwezen wordt vanuit de tekst opgenomen worden in de bibliografie. Is er bij elke referentie voldoende info om de bron terug te vinden? Is het duidelijk om welke bron het gaat? Zijn online bronnen voorzien van een datum van raadplegen?