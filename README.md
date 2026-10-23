# Mini-level — Inleveren

**Naam: Hugo Jager** <!-- jouw naam -->  
**Klas: SD1A** <!-- jouw klas -->
**Datum: 23-10-2026** <!-- datum van inleveren -->  
**Les: GDV Les 6** GDV Les 6

---

## Wat heb ik gemaakt?

<!-- Beschrijf kort je mini-level. Wat moet de speler doen? Wat is het doel? -->
Ik heb een mini-level gemaakt waar je een deur hebt die je moet openen terwijl je achtervolgt wordt door een vijand
...
---

## Screenshot / GIF van je level

<!-- Voeg hieronder een screenshot of een GIF toe van je werkende level.
     Sleep het bestand naar deze map en gebruik dan de syntax hieronder. -->

![Mini-level preview](images/level.gif)

<!-- Tip: gebruik ShareX, LICEcap of de ingebouwde Xbox Game Bar (Win+G) om een GIF op te nemen. -->

---

## Bewegend object

<!-- Welk object beweegt en hoe heb je dat gedaan? -->

...
De vijand beweegt met een navmeshagent
```csharp
// Plak hier het script of het stuk code dat het object laat bewegen.
void Update()
{
        if (hasKilledPlayer) return;
        else agent.SetDestination(player.position);
}
```

---

## Collider of trigger

<!-- Welk object heeft een collider of trigger, en wat gebeurt er? -->

De deur, speler, vijand en key hebben allemaal een Trigger.
...
```csharp
// Plak hier de OnCollisionEnter/OnTriggerEnter code die je hebt gebruikt.
    private void OnTriggerEnter(Collider other)
    {   
        if (other.CompareTag("Player") && GameScript.instance.canDie)
        {
            hasKilledPlayer = true;
            agent.SetDestination(transform.position);
            GameScript.instance.KillPlayer();
        }
    }
```

---

## Logica met `if` of `switch`

<!-- Beschrijf kort welke keuze je hebt gemaakt (bijv. sleutel → deur open). -->

...

```csharp
// Plak hier het stuk code met jouw if- of switch-logica.
            if (canOpen)
            {
                FinishLevel();
            }
            else
            {
                hintText.text = "you need a key!";
                Instantiate(keyObj, keySpawnPos.position, Quaternion.identity);
            }
```
als je de sleutel hebt en de deur aanraakt finish je het level, anders spawn je de sleutel in.
---

## Eigen extra idee

<!-- Wat is jouw eigen extra feature? Beschrijf wat het doet en hoe je het hebt gebouwd. -->

...
De vijand die je achtervolgt.
```csharp
// Optioneel: plak hier de bijbehorende code.

```

---

## Evaluatie

### Wat ging goed? en waarom?

<!-- Wat lukte je makkelijk of waar ben je trots op? -->
Ja het was erg makkelijk, ik hoefde maar een paar extra regels code te schrijven omdat ik al een andere opdracht had, die er 10 keer mooier uitziet maar die ik niet mocht inleveren voor het miniproject.
...

### Wat vond je lastig? en waarom?

<!-- Waar liep je tegenaan? Hoe heb je het opgelost (of niet)? -->
Ik vond het vervelend dat ik een nieuw level moest maken.
...

### Wat zou je een volgende keer anders doen?
Niet meer zo mijn best doen op kleine opdrachten.
<!-- Wat heb je geleerd? -->

...
