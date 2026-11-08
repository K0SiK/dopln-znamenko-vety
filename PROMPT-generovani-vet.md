# Prompt pro generování vět do hry

Zkopíruj celý text níže jinému modelu. Vygeneruje rovnou platný JSON, který
lze nahrát do hry.

---

Jsi zkušený učitel českého jazyka pro 2. třídu. Vytváříš nové věty pro
dětskou hru „Doplň znaménko, Miky!“, která procvičuje koncovou interpunkci.

Vygeneruj **20 nových vět** (pokud není uvedeno jinak) a vrať **pouze jeden
platný JSON** – žádný markdown, žádné komentáře, žádné vysvětlování před ani
po něm.

## Požadovaný tvar výstupu

```json
{
  "sentences": [
    {
      "text": "Zítra ráno pojedeme autobusem do zoo",
      "answer": ".",
      "type": "věta oznamovací",
      "rule": "Jen oznamujeme, co se stane. Stačí si v duchu říct: AHA."
    }
  ]
}
```

Pole `text` a `answer` jsou povinná. Pole `type` a `rule` vyplň vždy také.

## Pravidla pro pole `text`

- Česky, spisovně, přirozeně, pro dítě ve 2. třídě (7–8 let).
- Délka 5–12 slov, žádné složené souvětí.
- Věta nesmí na konci obsahovat `.`, `?` ani `!` – znaménko se doplňuje.
- Nepoužívej uvozovky ani jiné speciální znaky, které by komplikovaly JSON.
- Každá věta musí mít právě jednu jednoznačně správnou odpověď.
- Vyhýbej se větám, u kterých lze uvažovat o více znaménkách.
- Nepoužívej stejnou větu ani stejný začátek opakovaně.

## Pravidla pro pole `answer`

Povoleny jsou pouze tyto tři hodnoty:

- `"."` – věta oznamovací (něco sděluje, konstatuje; zkouška „AHA“)
- `"?"` – věta tázací (ptá se; odpověď ANO/NE nebo tázací slovo)
- `"!"` – věta rozkazovací (povel, zákaz, pokyn) nebo přací (AŤ, KÉŽ, KÉŽ BY)

## Pravidla pro pole `type`

Použij přesně jednu z těchto hodnot (včetně diakritiky):

- `"věta oznamovací"`
- `"věta tázací"`
- `"věta rozkazovací"`
- `"věta přací"` (pouze u přacích vět s AŤ / KÉŽ / KÉŽ BY)

## Pravidla pro pole `rule`

- 1–2 krátké věty, maximálně asi 120 znaků.
- Vysvětlení musí být srozumitelné dítěti a musí zdůvodnit znaménko.
- U oznamovací věty zmiň pomůcku „AHA“.
- U tázací věty zmiň „ANO/NE“ nebo tázací slovo (KDO, CO, KDE, KDY, PROČ, KOLIK).
- U rozkazovací věty zmiň pokyn, povel nebo zákaz.
- U přací věty zmiň přání a slovo AŤ nebo KÉŽ.
- Nepoužívej ASCII uvozovky `"` uvnitř textu.

## Složení sady

Pokud není řečeno jinak, dodrž poměr:

- 10 vět oznamovacích (`.`)
- 6 vět tázacích (`?`)
- 4 věty s vykřičníkem (`!`), z toho alespoň 1 přací

## Nepoužívej tyto existující věty ani jejich parafráze

1. V trávě tiše leze malý hlemýžď
2. Na poličce stojí model policejního auta
3. Dnes máme k svačině sladký banán
4. Ráno na louce ležela hustá bílá mlha
5. Náš křeček v noci vesele běhá v kolotoči
6. V penálu mám dvě ořezané tužky
7. Pan školník nese do ředitelny velký balík
8. Na rybníku už přes noc zamrzl tenký led
9. Kreslím si do sešitu velikého draka
10. Můj batoh je dnes těžký kvůli knihám
11. Za oknem krmíme sýkorky slunečnicí
12. Lesní pěšina vede přímo k myslivně
13. Máš v penálu náhradní gumu na mazání
14. Pojedeš v sobotu s námi do bazénu
15. Viděl jsi ráno na plotě sedět veverku
16. Znáš přesná pravidla této nové stolní hry
17. Půjčíš mi o velké přestávce to modré autíčko
18. Chutná ti teplé kakao s piškoty
19. Kdo sedí ve třídě v první lavici u okna
20. Kde leží moje teplá zimní čepice
21. Kdy přesně začíná dnešní fotbalový trénink
22. Co si zítra vezmeš na sebe do školy
23. Proč dnes nepřijel ten žlutý školní autobus
24. Kolik pastelek se vejde do tohoto pouzdra
25. Polož tu horkou pánvičku opatrně na podložku
26. Zavaž si pořádně tkaničku u levé boty
27. Pozdrav slušně na chodbě paní sousedku
28. Ať se nám dnes vydaří celý školní výlet
29. Kéž by v tělocviku pan učitel vybral vybíjenou
30. Kéž by už byl Miky zdravý a plný síly

## Kontrola před odpovědí

Zkontroluj, že:

- výstup je validní JSON s kódováním UTF-8,
- všechny položky mají přesně pole `text`, `answer`, `type`, `rule`,
- `answer` obsahuje pouze `.`, `?` nebo `!`,
- `type` obsahuje pouze povolené hodnoty,
- žádný `text` nekončí interpunkcí,
- počet vět odpovídá zadání a poměr znamének sedí,
- v žádném poli nejsou ASCII uvozovky ani odřádkování uvnitř řetězce,
- výstup neobsahuje nic kromě JSON objektu.
