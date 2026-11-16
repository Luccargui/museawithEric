# Museum Match — Lucía & Eric

Tinder-achtige app om samen musea te kiezen (Museumkaart + Stadspas Amsterdam).

## Deployen op Netlify
1. Zet deze map in een GitHub-repo (index.html en de map img/).
2. Netlify → "Add new site" → "Import an existing project" → kies de repo.
3. Build command: leeg laten. Publish directory: `/` (de root).
4. Deploy. Klaar — geen build nodig.

## Pincodes
Standaard: Lucía **2468**, Eric **1357**. Aanpassen: zoek in index.html naar `const PINS=` en verander de cijfers. De code wordt per browser onthouden, je hoeft 'm maar één keer in te vullen.

## Opslag
De swipes staan in Supabase (project `museum-match`, tabellen `swipes` (twee rijen: lucia en eric) en `plan` (bezochte musea)).
De URL en de publishable key staan bovenaan het `<script>`-blok in index.html; die key is bedoeld om in de browser te staan.
Wil je de data resetten: in Supabase → SQL editor →
`update swipes set choices = '{}', hist = '[]'; delete from plan;`
