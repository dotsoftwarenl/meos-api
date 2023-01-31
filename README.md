
# Installatie dotsoftware boete API script

De boete API is ontwikkeld door dotsoftware. De API laat gebruikers vanuit het dotsoftware MEOS boetes schrijven naar online spelers. Het API script werkt alleen met de maatwerk applicatie gemaakt door dotsoftware. Voor meer informatie zie; https://dotsoftware.nl of join onze discord; https://discord.com/invite/GXJ2XaJuTW.

## Belangrijke informatie
Wij raden af om gelekte versies van het boete API script te installeren op je gameserver. We weten helaas niet wat er met het script is gebeurd als het vanaf een derde partij beschikbaar wordt gesteld. Download dus ook alleen het boete API script via de officiele dotsoftware github.

## Installatie procedure
* Je hebt het bestand, meos_api.rar, ge-download via onze github.
* De map naam van de installatie (meos_api.rar) moet hetzelfde blijven zodat deze blijft werken.

In de installatie heb je de api.json zitten. Dit bestand spreekt voor zich, want deze vul je straks aan met informatie vanuit je MEOS account. Zie de content van het bestand:

```
{
    "api-enabled": true, // Enable or disable the API script
    "api-token": "TOKEN HERE" // Your API token which can be requested via your meos dashboard
}
```

Naast de api.json heb je ook de config.lua zitten. Dit config bestand moet aangepast worden naar jullie eigen framework core name en de notify event. Weet je niet hoe dit moet? Vraag je developer. Die weet het wel.

```
config = {
    ["CoreName"] = "qb-core", -- The name of your core
    ["NotifyName"] = "QBCore:Notify", -- Event name which triggers the notification to a player
}
```

Volg de volgende stappen om de API token te genereren van het boete API script.

* Log in
* Klik rechtboven op je accountnaam
* Klik op API token
* Vul de naam in van je API token (mag alles zijn wat je wilt)
* Klik op aanmaken
* In de pop-up zie je nu je API token. Deze kan je eenmalig zien.
* Kopieer de API token en vul deze in je api.json bestand in.

Extra optie:
* Gebruik een Discord webhook URL om grip te krijgen op de boetes die worden verstuurd vanuit MEOS richting spelers in je stad. Zo kan je gemakkelijk misbruik detecteren.

Om het script te laten werken moet je het rar bestand uploaden op je gameserver. Dit bestand kan je vervolgens runnen als resource. 

## MEOS aanpassing
Gefeliciteerd, je hebt het script geactiveerd op je server. Nu ziet elke agent onder een PV staan "Boete status". Deze status geeft weer als de speler al eens is bekeurd voor zijn procesverbaal. Dus; Boete status geeft een groen vinkje wanneer de actie succesvol is gegaan. Een rood kruis geeft aan dat de boete nog niet is verstuurd of dat er iets mis is gegaan. Is het een rode kruis, dan kan je bij het bewerken alsnog de boete versturen.

Als een agent een procesverbaal aanmaakt heeft deze de optie om op "Send fine" te klikken. Wanneer dit gebeurd verstuurd de agent een boete richting de speler toe. De speler krijgt hier ook een notificatie van (mits je dit goed hebt ingesteld in de config.lua).

## Support
Kom je toch ergens niet uit? Of werkt het script niet omdat je versie v1.2918201 gebruikt van een herkauwd framework? Dan kan je altijd contact opnemen met ons via discord via een ticket.
