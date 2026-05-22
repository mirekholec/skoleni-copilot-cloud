# CAL-013: Implementační poznámky

## Datum implementace
2026-05-22

## Provedené změny

### src/index.html
- Přidán `<span class="event-count" id="eventCount"></span>` do `.header-left` za `#weekRange`

### src/styles.css
- Přidán styl `.event-count` (malý kulatý badge s primární barvou)
- Badge je ve výchozím stavu skrytý (`display: none`), zobrazí se třídou `.is-visible`

### src/app.js
- `cacheDomReferences()`: přidáno `dom.eventCount = document.getElementById('eventCount')`
- Přidána funkce `renderEventCount()` – iteruje přes 7 dní aktuálního týdne, počítá události viditelných kategorií a aktualizuje badge
- `renderCalendar()`: voláno `renderEventCount()` na konci

## Poznámky
- Aplikace nemá měsíční pohled, implementace pokrývá pouze týdenní pohled
- Badge se automaticky aktualizuje při navigaci (přes `renderCalendar()`) a při přepínání kategorií (přes `handleCategoryToggle()` → `renderCalendar()`)
