# Doplň znaménko, Miky! – věty pro TV hru

Veřejné úložiště vět pro aplikaci **Doplň znaménko, Miky!** na Android TV.

Aplikace si tento soubor stahuje automaticky při spuštění:

```
https://raw.githubusercontent.com/K0SiK/dopln-znamenko-vety/main/sentences.json
```

## Jak upravit věty

1. Otevřete `sentences.json` a klikněte na tužku **Edit**.
2. Přidejte / upravte / smažte položky v poli `sentences`.
3. Commitněte změnu do větve `main`.
4. V televizi aplikaci zavřete a znovu otevřete (nebo v menu
   **⚙ Věty** použijte **🔄 Stáhnout**).
5. Nové věty se projeví při dalším kole.

Není potřeba nic instalovat ani nahrávat do televize.

## Formát

```json
{
  "sentences": [
    {
      "text": "Naše kočka spí celé odpoledne na gauči",
      "answer": ".",
      "type": "věta oznamovací",
      "rule": "Jen oznamujeme, co se děje. Stačí si v duchu říct: AHA."
    }
  ]
}
```

- `text` – věta bez koncového znaménka, česky, pro 2. třídu.
- `answer` – `"."`, `"?"` nebo `"!"`.
- `type` – `"věta oznamovací"`, `"věta tázací"`, `"věta rozkazovací"` nebo `"věta přací"`.
- `rule` – krátké vysvětlení pro dítě.

Pole `type` a `rule` jsou nepovinná; když chybí, aplikace je doplní podle znaménka.

## Generování dalších vět

V souboru [`PROMPT-generovani-vet.md`](PROMPT-generovani-vet.md) je připravený
prompt pro jiný model. Výstup z něj sem můžete vložit přímo.

## Bezpečnost

Repozitář je veřejný pouze pro čtení. Upravovat ho může jen vlastník účtu.
Aplikace funguje i offline – používá naposledy staženou verzi vět.
