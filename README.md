# Výplata

Statická aplikace nasazovaná z `main` na GitHub Pages. Data zůstávají lokálně nebo se po přihlášení synchronizují se stávajícím Supabase projektem.

## Cíle a pracovní fond

- Měsíční základ = pracovní dny bez svátků a dovolené × nastavený základ fondu.
- Dovolená snižuje měsíční základ i počet dostupných pracovních dní.
- Volno snižuje pouze počet dostupných pracovních dní. Již uložené záznamy `volno` mají tento význam.
- Klikání v kalendáři: pracovní den → dovolená → volno → pracovní den.
- Dnešní rozpočet pásma = zbývající obrat před dnešními objednávkami / zbývající pracovní dny včetně dneška. Dnešní objednávky rozpočet nemění, pouze ho plní.
- Ve dnech volna se nezobrazuje umělý denní cíl, ale obrat navíc a tempo pro další pracovní dny.
- Hlavní pásmo je 100 %, po dosažení měsíčních 100 % se zvýrazní 136 %. Pásmo 90 % je doplňkové.

## Ověření

`node tests/calculations.cjs` ověřuje fond, stabilitu denního rozpočtu, cyklus kalendáře a pořadí synchronizace s izolovanou náhradou cloudové služby. Nemění produkční data.
