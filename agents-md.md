# AGENTS.md: файл с инструкции за агенти за писане на код

> Превод на български на [agents.md](https://agents.md/). Оригиналът е под MIT лиценз (свободен лиценз с посочване на източника), чийто пълен текст е в края на файла. Кодът и командите са запазени без промяна.

**Защо ви го давам.** Когато правите сайт или приложение с AI, например с Claude Code или Cursor, AI всеки път започва „на чисто“ и не помни как сте се разбрали. AGENTS.md е обикновен текстов файл, който слагате в папката на проекта. В него пишете с обикновени думи правилата: на какъв език е сайтът, какви цветове ползва брандът, какво да не пипа. AI го прочита сам при всяка задача и не се налага да обяснявате всичко отначало.

Нужен ви е, когато вече правите проект с AI агент за код. Ако още не сте стигнали дотам, започнете с [AI инструменти: какво да ползваш и защо](ai-instrumenti-s-obyasnenie.md).

Няколко думи, които ще срещнете по-долу:

- **Агент за писане на код:** AI, който сам създава и променя файловете на проекта, вместо само да ви отговаря в чат.
- **README:** файлът с описание на проекта, който хората четат първо.
- **Repository (хранилище за код):** папката на проекта в GitHub заедно с цялата история на промените.
- **Билд и тестове:** командите, които сглобяват проекта и проверяват дали работи.
- **Commit:** запазена промяна в хранилището, с кратко описание какво е променено.

AGENTS.md е прост и отворен формат за насочване на coding agents (агенти за писане на код), който се използва от над 60 хиляди проекта с отворен код. Мислете за него като за README за агенти: определено и предвидимо място, където агентът намира контекста и инструкциите за работа по проекта.

Кратък пример:

```markdown
# AGENTS.md

## Команди за настройка
- Инсталиране на зависимости: `pnpm install`
- Стартиране на сървъра за разработка: `pnpm dev`
- Пускане на тестове: `pnpm test`

## Стил на кода
- TypeScript в strict режим
- Единични кавички, без точка и запетая
- Функционални подходи, където е възможно
```

## Съдържание

- [Защо AGENTS.md?](#защо-agentsmd)
- [Един файл за много агенти](#един-файл-за-много-агенти)
- [Примери](#примери)
- [Как се използва](#как-се-използва)
- [За проекта](#за-проекта)
- [Често задавани въпроси](#често-задавани-въпроси)
- [Лиценз на оригинала](#лиценз-на-оригинала)

## Защо AGENTS.md?

README.md е за хора: бърз старт, описание на проекта, насоки за участие. AGENTS.md допълва този файл с подробностите, които трябват на агентите: стъпки за билд, тестове, конвенции. Тези неща биха претрупали README или не са нужни на хората, които участват в проекта.

Форматът е отделен файл с три цели:

- агентите получават ясно и предвидимо място за инструкции;
- README файловете остават кратки и насочени към хора;
- насоките за агенти допълват съществуващата документация, без да я заместват.

Името и форматът умишлено са общи, а не обвързани с конкретен продукт, за да може всеки да ги приеме.

## Един файл за много агенти

Форматът се поддържа от растяща екосистема от инструменти:

- [Codex от OpenAI](https://openai.com/codex/)
- [Jules от Google](https://jules.google)
- [Factory](https://factory.ai)
- [Aider](https://aider.chat/docs/usage/conventions.html#always-load-conventions)
- [goose](https://github.com/block/goose)
- [opencode](https://opencode.ai/docs/rules/)
- [Zed](https://zed.dev/docs/ai/rules)
- [Warp](https://docs.warp.dev/knowledge-and-collaboration/rules#project-scoped-rules-1)
- [VS Code](https://code.visualstudio.com/docs/editor/artificial-intelligence)
- [Devin от Cognition](https://devin.ai)
- [Autopilot и Coded Agents от UiPath](https://uipath.github.io/uipath-python)
- [Junie от JetBrains](https://jetbrains.com/junie)
- [Amp](https://ampcode.com)
- [Cursor](https://cursor.com)
- [RooCode](https://roocode.com)
- [Gemini CLI от Google](https://github.com/google-gemini/gemini-cli/blob/main/docs/get-started/configuration.md#available-settings-in-settingsjson)
- [Kilo Code](https://kilocode.ai/)
- [Phoenix](https://phoenix.new/)
- [Semgrep](https://semgrep.dev)
- [Coding agent от GitHub Copilot](https://gh.io/coding-agent-docs)
- [Ona](https://ona.com)
- [Windsurf от Cognition](https://windsurf.com)
- [Augment Code](https://docs.augmentcode.com/cli/overview)

## Примери

```markdown
# Примерен файл AGENTS.md

## Съвети за средата за разработка
- Използвайте `pnpm dlx turbo run where <project_name>`, за да отидете директно до даден пакет, вместо да търсите с `ls`.
- Пуснете `pnpm install --filter <project_name>`, за да добавите пакета към работното пространство, така че Vite, ESLint и TypeScript да го виждат.
- Използвайте `pnpm create vite@latest <project_name> -- --template react-ts`, за да създадете нов пакет с React и Vite с готови проверки на TypeScript.
- Проверете полето name в package.json на всеки пакет, за да потвърдите правилното име. Пропуснете файла на най-горното ниво.

## Инструкции за тестване
- Намерете плана за CI в папката .github/workflows.
- Пуснете `pnpm turbo run test --filter <project_name>`, за да изпълните всички проверки за този пакет.
- От главната папка на пакета е достатъчно да извикате `pnpm test`. Преди сливане commit трябва да минава всички тестове.
- За да се съсредоточите върху една стъпка, добавете шаблона на Vitest: `pnpm vitest run -t "<test name>"`.
- Поправяйте грешките в тестовете и типовете, докато целият набор мине успешно.
- След преместване на файлове или промяна на импорти пуснете `pnpm lint --filter <project_name>`, за да сте сигурни, че правилата на ESLint и TypeScript все още се спазват.
- Добавяйте или обновявайте тестове за кода, който променяте, дори никой да не го е поискал.

## Инструкции за PR
- Формат на заглавието: [<project_name>] <Заглавие>
- Винаги пускайте `pnpm lint` и `pnpm test` преди commit.
```

Реални файлове AGENTS.md в публични проекти:

- [openai/codex](https://github.com/openai/codex/blob/-/AGENTS.md): инструменти за команден ред за агенти за писане на код (Rust)
- [apache/airflow](https://github.com/apache/airflow/blob/-/AGENTS.md): платформа за създаване, планиране и наблюдение на работни процеси чрез код (Python)
- [temporalio/sdk-java](https://github.com/temporalio/sdk-java/blob/-/AGENTS.md): Java SDK за Temporal, оркестрация на работни процеси, описани в код (Java)
- [PlutoLang/Pluto](https://github.com/PlutoLang/Pluto/blob/-/AGENTS.md): надмножество на Lua 5.4 за програмиране с общо предназначение (C++)

[Вижте над 60 хиляди примера в GitHub](https://github.com/search?q=path%3AAGENTS.md%20NOT%20is%3Afork%20NOT%20is%3Aarchived&type=code)

## Как се използва

### 1. Добавете AGENTS.md

Създайте файла в главната папка на repository (хранилището за код). Повечето агенти могат да го подготвят сами, ако ги помолите.

### 2. Покрийте важното

Подходящи раздели са:

- общ преглед на проекта;
- команди за билд и тестове;
- стил на кода;
- инструкции за тестване;
- съображения за сигурност.

### 3. Добавете допълнителни инструкции

Commit съобщения и насоки за pull request (заявка за сливане на промени), капани в сигурността, големи набори от данни, стъпки за внедряване. С други думи, всичко, което бихте казали на нов колега.

### 4. Голям monorepo (едно хранилище с много проекти)? Използвайте вложени файлове

Поставете отделен AGENTS.md във всеки пакет. Агентите четат най-близкия файл в дървото на папките, така че той има предимство. Към момента на писане на оригинала основното хранилище на OpenAI съдържа 88 такива файла.

## За проекта

AGENTS.md е резултат от съвместна работа в екосистемата, включително [OpenAI Codex](https://openai.com/codex/), [Amp](https://ampcode.com), [Jules от Google](https://jules.google), [Cursor](https://cursor.com) и [Factory](https://factory.ai). Проектът е ангажиран с формат, който остава отворен независимо от агента. Днес за него се грижи [Agentic AI Foundation](https://aaif.io) към Linux Foundation. [Научете повече](https://openai.com/index/agentic-ai-foundation/).

## Често задавани въпроси

### Има ли задължителни полета?

Не. Това е обикновен Markdown. Може да използвате каквито заглавия искате, а агентът просто чете текста.

### Какво става, ако инструкциите си противоречат?

Предимство има файлът AGENTS.md, който е най-близо до редактирания файл. Изричните указания на потребителя в чата стоят над всичко.

### Агентът пуска ли автоматично тестовите команди от AGENTS.md?

Да, ако са описани. Агентът се опитва да изпълни съответните програмни проверки и да поправи грешките, преди да приключи задачата.

### Мога ли да го обновявам по-късно?

Да. Отнасяйте се към него като към жива документация.

### Как да прехвърля съществуваща документация към AGENTS.md?

Преименувайте файла и създайте symbolic link (символна връзка) за обратна съвместимост:

```bash
mv AGENT.md AGENTS.md && ln -s AGENTS.md AGENT.md
```

### Как да настроя Aider?

Добавете в `.aider.conf.yml`:

```yaml
read: AGENTS.md
```

### Как да настроя Gemini CLI?

Добавете в `.gemini/settings.json`:

```json
{ "context": { "fileName": "AGENTS.md" } }
```

## Лиценз на оригинала

Източник: [agents.md](https://agents.md/) и [agentsmd/agents.md](https://github.com/agentsmd/agents.md).

```
MIT License

Copyright (c) 2025 OpenAI

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
