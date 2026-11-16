# Направи го с AI — практическа работилница / Do it with AI

**Kiki Innovation & Learning Lab · BG / EN · 16.11.2026 · v1.0**

Не започваме с „избери си инструмент от сто възможности“. Тук получаваш: **пряк линк → точни стъпки → промпт за копиране → критерий за готов резултат**. След това проверяваш дали AI е помогнал, или само е написал нещо убедително.

## 1. Създай анкета за училищно събитие с AI

<details open><summary><strong>Български: стъпка по стъпка</strong></summary>

**Инструмент:** [Google Forms](https://forms.google.com/) с функцията **Help me create a form (Gemini)**.

**Официално ръководство:** [Google — Create a form with Gemini](https://support.google.com/docs/answer/16346789?hl=en).

**Важно:** автоматичното генериране е достъпно **само при определени Google Workspace / Google AI планове** и най-общо на компютър. **Българският не е сред изрично поддържаните езици за тази функция** към датата на проверката; английският е. Ако Gemini не създаде формуляра на български, използвай английска чернова и преведи/редактирай въпросите ръчно. Не обещаваме функцията за всеки ученически акаунт.

### Натисни и направи

1. Отвори **[Google Forms](https://forms.google.com/)** в браузъра на компютър.
2. Създай нов формуляр с **Blank form**.
3. Ако виждаш **Help me create a form**, отвори го.
4. Постави **английския промпт** отдолу (той е по-надеждният вариант за поддържаните езици).
5. Избери **Create**, прегледай предложените въпроси и натисни **Create form**.
6. Редактирай всички въпроси на български, ако е необходимо. Провери дали има водещи въпроси и дали отговорите ще ти помогнат да вземеш решение.
7. Използвай **Preview**, попълни един тестов отговор и чак тогава публикувай/сподели формуляра според правилата на училището.

### Копирай в Gemini

```text
Create a short, neutral survey for high-school students about
a possible school entrepreneurship and digital innovation event.

Goal: understand interest in topics, preferred format and convenient times.
Maximum eight questions, under three minutes to complete.
Include:
- preferred topics (multiple choice)
- preferred format (workshop / discussion / challenge)
- suitable day or time window
- likelihood of attending
- one optional open question for ideas

Do not request names, emails, phone numbers, birth dates, or any
identifying information. Avoid leading questions and assumptions.
Use simple language and clear response options.
```

### Ако нямаш Gemini в Google Forms

1. Отвори [ChatGPT](https://chatgpt.com/) (ако е разрешен за твоята възраст и училищни правила).
2. Постави този промпт:

```text
Направи 8 въпроса за кратка анонимна анкета за интерес към
училищно събитие по предприемачество и дигитални иновации.
За всеки въпрос посочи подходящ тип в Google Forms
(един избор, няколко избора, скала или кратък текст).
Не искай лични данни и не използвай водещи въпроси.
Дай готов текст за копиране, без да твърдиш, че си създал формуляра.
```

3. Отвори [Google Forms](https://forms.google.com/) и добави предложените въпроси **ръчно**. Този резервен вариант не е автоматично създаване на форма.
4. Тествай въпросите с примерен отговор.

**Готово е, когато:** имаш реален формуляр, 6–8 ясни въпроса, тестов отговор и знаеш кое решение ще вземеш от резултатите.

**Кратка проверка:** Ако всички отговорят „да“, как ще разбереш коя тема и кой час да избереш? Поправи анкетата, ако не можеш да отговориш.

</details>

<details><summary><strong>English instructions</strong></summary>

**Tool:** [Google Forms](https://forms.google.com/), using **Help me create a form (Gemini)** if available under your Google Workspace/AI plan.

1. Create a blank form on a desktop.
2. Select **Help me create a form**, paste the English prompt above, and press **Create**.
3. Review the generated draft and select **Create form**.
4. Check questions, access settings and privacy, then test a response.
5. If the Gemini option is missing, use an age-appropriate AI tool for a **question draft only**, and enter the questions manually in Google Forms.

**Outcome:** a real survey with clear questions, a tested response and a specific decision the findings will inform.

**Never confuse generating a list of questions with actually creating a working Google Form.** Official information: [Google Help](https://support.google.com/docs/answer/16346789?hl=en).

</details>

---

## 2. Направи кратък тест / Create a quiz

**Инструмент:** [Google Forms](https://forms.google.com/). При поддържан план **Help me create** може да генерира и тест с предложени верни отговори и точки. **Провери всеки отговор лично**.

**Промпт:**

```text
Create a 7-question multiple-choice quiz about
the difference between invention, innovation, digitalisation,
and digital transformation for upper secondary students.
Include one realistic business scenario per question.
Provide correct answers and short explanations.
Avoid trivial or leading questions.
```

**Изпълнение:** отвори нов Google Form → Help me create, ако е налично → постави промпта → Create → прегледай отговорите → Create quiz → тествай. [Официални инструкции](https://support.google.com/docs/answer/16346789?hl=en).

**Резултат:** тест, в който въпросите проверяват разбиране, а не просто запаметяване.

---

## 3. Анализирай отговорите / Analyse survey responses

**Инструменти:** [Google Forms](https://forms.google.com/) → таб **Responses** → свързана таблица в [Google Sheets](https://sheets.google.com/). Ако си начинаещ, първо ползвай автоматичните обобщения в Forms и обикновена таблица. AI анализ е *допълнителна възможност*, ако е налична и разрешена.

**Текст за анализ с AI, само с анонимизирани данни:**

```text
Analyse the following anonymised survey results.
Count responses by option, identify the top three preferences
and explain limitations of the sample.
Do not invent missing answers or infer individual identities.
Separate facts, hypotheses and practical recommendations.
Data: [paste non-identifying aggregate counts only]
```

**Резултат:** кратко обобщение, таблица с брой отговори, ограничения и решение, което може да се защити.

---

## Общ стандарт за всички бъдещи инструкции

**Инструмент → директен адрес → кой бутон да натиснеш → готов промпт → какъв файл/резултат получаваш → как проверяваш → какво правиш, ако функцията липсва.**

Вместо да трупаме десетки случайни приложения, ще подбираме конкретен инструмент за конкретна задача. Всички препоръки са подчинени на правилата на училището и на възрастовите ограничения на съответните услуги.

**Проверено:** 16.11.2026 г. · [Наличност на Gemini в Forms](https://support.google.com/docs/answer/16346789?hl=en) · [Поддържани езици](https://support.google.com/docs/answer/14925782?hl=en)

[Начална страница](README.md) · [Редакционни правила](REDAKTSIONEN-STANDART.md)
