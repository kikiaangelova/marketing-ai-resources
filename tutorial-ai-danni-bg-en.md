# Анализирай таблица с AI / Analyse a Spreadsheet with AI

**Kiki Innovation & Learning Lab · BG / EN · 16.11.2026 · v1.0**

## Български

**Задача:** изчисли приходите на учебен бизнес по продукти и канали.

**Инструмент:** [ChatGPT](https://chatgpt.com/) с възможност за качване на CSV/XLSX. Наличността зависи от плана и ограниченията на профила. [Официално ръководство](https://help.openai.com/en/articles/8437071-advanced-data-).

### Данни за упражнение (измислени)

Можеш да копираш следната таблица в Google Sheets и да я запазиш като CSV. **Това не са реални продажби.**

```csv
product,channel,quantity,unit_price_bgn
Notebook,School fair,8,12
Notebook,Online,5,12
Sticker,School fair,16,3
Sticker,Online,9,3
Badge,School fair,10,5
Badge,Online,6,5
```

### Стъпки

1. Отвори [Google Sheets](https://sheets.google.com/), въведи примерните данни и ги експортирай като CSV.
2. Отвори [ChatGPT](https://chatgpt.com/) и прикачи **само примерния CSV**. Не качвай имена, контакти, оценки и реални ученически данни.
3. Постави промпта по-долу.
4. Провери ръчно поне три умножения и общата сума.
5. Покажи един стълбовиден график по продукти и напиши две препоръки, които **не надхвърлят данните**.

### Копирай промпта

```text
Анализирай прикачения CSV с примерни продажби.
Изчисли приход = количество × единична цена за всеки ред.
Покажи общ приход, приход по продукт и по канал.
Направи стълбовидна диаграма по продукт.
Покажи формулите и провери дали общите суми съвпадат.
Отдели доказани наблюдения от предположения.
Не измисляй липсващи разходи или печалба.
```

**Контролни суми:** общ приход **311 лв.**; Notebook **156 лв.**, Sticker **75 лв.**, Badge **80 лв.** По канал: School fair **194 лв.**, Online **117 лв.** Провери ги и сам!

**Готов резултат:** обобщена таблица, графика, три ръчно проверени изчисления и две ограничени до данните препоръки.

## English

Create a CSV from the fictional dataset above in [Google Sheets](https://sheets.google.com/). Upload it to [ChatGPT](https://chatgpt.com/) if file analysis is available. Ask for total revenue, revenue by product/channel and a bar chart. Check at least three calculations independently. Do not infer profit without costs.

**Deliverable:** evidence-backed summary, chart and validation notes. [Official OpenAI guidance](https://help.openai.com/en/articles/8437071-advanced-data-).

[Library](README.md)
