# 02. Анализ на клиентски отзиви / Customer review analysis

**Kiki Innovation & Learning Lab · Версия 1.0 · 16.11.2026 · BG / EN**

## Избери инструмента / Choose the tool

**Препоръчан инструмент / Recommended:** [ChatGPT Data Analysis + Google Sheets](https://chatgpt.com/).  
**Допълнителен инструмент:** [Google Sheets](https://sheets.google.com/) за преглед и проверка на табличните данни.

**За кого:** Хотел, ресторант, салон или магазин.  
**Вход:** Анонимизирани номерирани отзиви и категории.  
**Изход:** Теми, доказателства и управленски предложения.

> Това е учебен прототип. Използвайте само измислени, публични или изрично разрешени и анонимизирани материали. Не предоставяйте фирмени тайни, лични данни или реални клиентски съобщения без разрешение. Проверете възрастовите ограничения и училищните правила.

## Български: натисни и изпълни

1. Натисни **[Отвори инструмента](https://chatgpt.com/)** и започни нов чат. За повтаряща се работа може да създадеш **Project**, ако функцията е налична в твоя профил.
2. Подготви входните данни: **Анонимизирани номерирани отзиви и категории**. За първия опит използвай учебния пример по-долу. Ако имаш файл, прикачи го чрез бутона за добавяне на файлове, когато е наличен.
3. Копирай промпта от полето по-долу. Постави след него своя учебен материал.
4. Прегледай резултата. **Очакван изход:** Теми, доказателства и управленски предложения.
5. Сравни го с първоизточника. Поправи неточностите и запиши какво не може да се установи.
6. Предай: входните данни, промпта, получената версия, направените корекции и кратък извод *„Какво решавам аз, а не AI?“*.

### Копирай промпта

```text
Класифицирай предоставените номерирани отзиви по чистота, обслужване, цена, храна и друго. Един отзив може да има две теми. Върни таблица: ID, теми, отношение, точен цитат, възможно действие. Никакви измислени цитати или изводи за целия пазар. Покажи ограниченията на извадката.

ВХОДНИ ДАННИ:
[ПОСТАВИ ТУК ПРИМЕРНИТЕ ИЛИ РАЗРЕШЕНИТЕ МАТЕРИАЛИ]
```

### Учебен пример (измислен, не е реална бизнес информация)

> R01: „Стаята беше чиста, но чаках 20 минути на рецепция.“ R02: „Добра закуска, но скъпо.“ R03: „Удобно място и любезни хора.“

### Проверка за готов резултат

**Ръчно сравнение на категориите за 3 отзива и липса на несъществуващи цитати.**  
Измери и времето за подготовка, проверка и поправки. Не сравнявай само скоростта на генериране. Ако системата измисля факти, **не я приемай за готова**.

## English: quick instructions

**Tool:** [ChatGPT Data Analysis + Google Sheets](https://chatgpt.com/). **Business use case:** Хотел, ресторант, салон или магазин.  
**Input:** Anonymised numbered reviews and categories. **Deliverable:** Themes, evidence and proposed actions.

1. Open the tool, start a new chat or project if available, and provide fictional or authorised materials only.
2. Paste the Bulgarian prompt above. You can add: **“Respond in English, preserving all evidence requirements and restrictions.”**
3. Inspect the output, check every claim against the supplied documents and mark missing information rather than guessing.
4. Save the example input, instructions, result, corrections and a short human decision.

### Copyable English prompt

```text
Categorise the numbered anonymised reviews by cleanliness, service, food, location and price. Allow multiple categories. Return ID, theme, sentiment, supporting verbatim quotation and suggested action. Do not invent reviews or generalise from this small sample.

INPUT MATERIAL:
[PASTE FICTIONAL OR AUTHORISED DATA HERE]
```

**Validation:** Ръчно сравнение на категориите за 3 отзива и липса на несъществуващи цитати. Do not treat draft answers, categories, offers or extracted data as approved business actions.

## Кратка матрица / Assessment (12 точки / points)

| Критерий / Criterion | Точки |
| --- | ---: |
| Подходящ и разрешен вход / Suitable authorised inputs | 3 |
| Работещ промпт и определен изход / Reproducible workflow | 3 |
| Проверка спрямо фактите / Validation against evidence | 4 |
| Собствено решение и ограничения / Human decision and limits | 2 |

**За преподавателя:** използвайте поне четири тестови случая: два обичайни, един с липсващ факт и един с противоречие. Това е минимално учебно упражнение, не доказателство за надеждност в реален бизнес.

**Официални инструкции:** [ChatGPT Projects](https://help.openai.com/en/articles/10169521-projects-in-chatgpt) · [Data analysis](https://help.openai.com/en/articles/8437071-advanced-data-) · [Upload files](https://help.openai.com/en/articles/8555545-uploading-files-and-audio-to-chatgpt).

[Всички 12 проекта](tutorial-12-ai-biznes-proekti.md) · [Начална страница](README.md) · [Редакционен стандарт](REDAKTSIONEN-STANDART.md)
