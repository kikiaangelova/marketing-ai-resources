# 12. Извличане на данни от документи / Extract structured document data

**Kiki Innovation & Learning Lab · Версия 1.0 · 16.11.2026 · BG / EN**

## Избери инструмента / Choose the tool

**Препоръчан инструмент / Recommended:** [ChatGPT Data Analysis + Google Sheets](https://chatgpt.com/).  
**Допълнителен инструмент:** [Google Sheets](https://sheets.google.com/) за преглед и проверка на табличните данни.

**За кого:** Търговия, логистика или услуги.  
**Вход:** Разрешени текстови PDF/документи и списък с полета.  
**Изход:** Таблица: документ, поле, стойност и източник.

> Това е учебен прототип. Използвайте само измислени, публични или изрично разрешени и анонимизирани материали. Не предоставяйте фирмени тайни, лични данни или реални клиентски съобщения без разрешение. Проверете възрастовите ограничения и училищните правила.

## Български: натисни и изпълни

1. Натисни **[Отвори инструмента](https://chatgpt.com/)** и започни нов чат. За повтаряща се работа може да създадеш **Project**, ако функцията е налична в твоя профил.
2. Подготви входните данни: **Разрешени текстови PDF/документи и списък с полета**. За първия опит използвай учебния пример по-долу. Ако имаш файл, прикачи го чрез бутона за добавяне на файлове, когато е наличен.
3. Копирай промпта от полето по-долу. Постави след него своя учебен материал.
4. Прегледай резултата. **Очакван изход:** Таблица: документ, поле, стойност и източник.
5. Сравни го с първоизточника. Поправи неточностите и запиши какво не може да се установи.
6. Предай: входните данни, промпта, получената версия, направените корекции и кратък извод *„Какво решавам аз, а не AI?“*.

### Копирай промпта

```text
Извлечи от приложените учебни документи САМО тези полета: номер, дата, артикул, количество, единична цена. Върни таблица: файл, поле, стойност, точен ред/страница или раздел. Ако не се вижда, пиши „липсва“. Не гадай от нечетлив скан. Добави списък с неуверени извличания за ръчна проверка.

ВХОДНИ ДАННИ:
[ПОСТАВИ ТУК ПРИМЕРНИТЕ ИЛИ РАЗРЕШЕНИТЕ МАТЕРИАЛИ]
```

### Учебен пример (измислен, не е реална бизнес информация)

> Учебен документ: Заявка Z-014; дата 16.11.2026; продукт тефтер; количество 12; единична цена 8 лв. Вторият учебен документ няма дата.

### Проверка за готов резултат

**За първия има 12 × 8 = 96 лв.; във втория не е измислена дата.**  
Измери и времето за подготовка, проверка и поправки. Не сравнявай само скоростта на генериране. Ако системата измисля факти, **не я приемай за готова**.

## English: quick instructions

**Tool:** [ChatGPT Data Analysis + Google Sheets](https://chatgpt.com/). **Business use case:** Търговия, логистика или услуги.  
**Input:** Permitted text-based PDFs or documents and required field list. **Deliverable:** Table with document, field, value and source.

1. Open the tool, start a new chat or project if available, and provide fictional or authorised materials only.
2. Paste the Bulgarian prompt above. You can add: **“Respond in English, preserving all evidence requirements and restrictions.”**
3. Inspect the output, check every claim against the supplied documents and mark missing information rather than guessing.
4. Save the example input, instructions, result, corrections and a short human decision.

**Validation:** За първия има 12 × 8 = 96 лв.; във втория не е измислена дата. Do not treat draft answers, categories, offers or extracted data as approved business actions.

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
