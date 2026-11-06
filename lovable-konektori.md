# Lovable конектори: как да свържете приложението си с инструментите, които вече ползвате

Това е моето обяснение на страницата [Lovable Connectors](https://lovable.dev/connect) на български. Не е превод дума по дума, защото искам да разберете какво означава всичко това за вашите проекти. Официалното ръководство е в [документацията на Lovable](https://docs.lovable.dev/integrations/introduction).

## Съдържание

- [Какво е конектор и защо ви трябва](#какво-е-конектор-и-защо-ви-трябва)
- [Трите вида връзка](#трите-вида-връзка)
- [Как да добавите конектор](#как-да-добавите-конектор)
- [Какво можете да направите](#какво-можете-да-направите)
- [С какво да започнете](#с-какво-да-започнете)
- [За сигурността](#за-сигурността)
- [Всички конектори](#всички-конектори)

## Какво е конектор и защо ви трябва

Конекторът (connector) е готова връзка между Lovable и друг инструмент. Вместо да копирате данни от Google Sheets или да обяснявате всеки път как работи екипът ви, свързвате инструмента веднъж и Lovable започва да работи с него.

Представете си, че правите приложение за записване на часове. Без конектор имате красив екран, зад който не се случва нищо. С Google Calendar записът влиза в календара, с Gmail клиентът получава потвърждение, а със Stripe може и да плати.

Lovable обещава три основни неща:

- **Работи и когато не сте на компютъра.** Автоматизациите и задачите на заден план продължават, без да пишете нов промпт (инструкция към AI). Ако някоя връзка спре, Lovable ви уведомява по имейл.
- **Обяснявате по-малко.** Lovable вижда инструментите ви, докато гради, и така има повече контекст.
- **Потребителите ви могат да свържат своите акаунти.** Данните им за вход не влизат в кода на приложението, защото Lovable се грижи за тях чрез своя gateway (междинен слой за връзките).

Към момента на писане каталогът има 136 конектора, а Lovable казва, че добавя нови всяка седмица.

## Трите вида връзка

Това е най-важното за разбиране, защото от него зависи кой какво вижда.

| Вид | Как работи | Пример |
|---|---|---|
| **App + chat connector** (за приложението и чата) | Един общ акаунт, който ползват и приложението, и чатът в Lovable. Посетителите ви работят през него. | Формуляр на сайта на вашата ученическа фирма, който записва всяка заявка в една обща таблица |
| **Chat connector** (само за чата, чрез MCP) | Личен е за вас. Lovable чете вашите акаунти, докато гради, но връзката не влиза в публикуваното приложение. | Lovable чете бележките ви от Notion, за да разбере брифа на клиента |
| **App user connector** (за всеки потребител) | Всеки потребител влиза със собствения си акаунт и приложението действа с неговите права. | Приложение, което показва на всеки ученик неговия собствен Google Calendar |

MCP (Model Context Protocol, общ стандарт за връзка между AI и външни инструменти) е начинът, по който AI получава достъп до друг инструмент, без да се пише отделна връзка за всеки.

Не всеки конектор поддържа и трите вида. На страницата му пише кои са възможни.

Има и още три варианта, но за тях ще ви трябва повече опит:

- **Custom connector** (собствен конектор): администратор описва свое REST API (начин две програми да си говорят) за целия екип.
- **Custom MCP server** (собствен MCP сървър): за инструмент с MCP сървър, който го няма в каталога.
- **Any API** (всяко API): Lovable сам пише кода за връзката. Документацията препоръчва конектор, когато има такъв, защото тогава gateway пази данните за достъп.

## Как да добавите конектор

1. Отворете [каталога с конектори](https://lovable.dev/dashboard?connectors). Стига се до него и от страничното меню, и от бутона „+“ в полето за промпт.
2. Изберете инструмента и натиснете **Add connection** (добави връзка).
3. Изберете вида връзка.
4. Влезте в акаунта на инструмента и дайте само нужните права.
5. В чата кажете на Lovable какво да прави с връзката.

В отворен проект връзките ви са в **More > Connectors**, където са разделени на Project connections (връзки на проекта) и MCP connectors (MCP конектори). В чата ги намирате през **+ > Add context > Connectors**.

Някои неща идват без отделен акаунт: хостинг (място, където живее сайтът), backend (база данни, вход на потребители и файлове) и Lovable AI. Ако предпочитате, можете да свържете собствен Supabase проект.

## Какво можете да направите

Lovable дава три примера. Ето ги с моите думи:

- **Ако работите сами за клиенти:** агент, който подготвя фактури и напомня на клиентите, използвайки Gmail и таблица.
- **Ако сте в продуктов екип:** инструмент, който събира задачи от Linear, дизайн от Figma и съобщения от Slack, като всеки вижда само това, до което има достъп.
- **Ако поддържате вътрешните процеси на фирма:** нощна проверка на показателите, която пише в Slack, щом забележи нещо необичайно.

А за нашите проекти по маркетинг:

- **Табло за клиент:** Google Analytics + Google Search Console + Lovable, за да вижда клиентът трафика и търсенията на едно място.
- **Събиране на контакти:** формуляр от Tally или страница в Lovable, която записва в Google Sheets и изпраща имейл през Brevo.
- **Магазин:** страница с продукти от Shopify, а за плащане Stripe.

## С какво да започнете

Не свързвайте всичко. Започнете с малък проект и добавяйте по един конектор:

1. **Google Sheets:** виждате данните си в позната таблица.
2. **Gmail или Brevo:** приложението започва да праща съобщения.
3. **Google Analytics:** разбирате дали някой го използва.
4. **GitHub:** кодът ви е на сигурно място и не зависи от една платформа.
5. **Stripe:** чак когато наистина имате какво да продавате.

## За сигурността

- Давайте само нужните права. Ако проектът само чете таблица, не му давайте достъп до цялата ви поща.
- Внимавайте с общия акаунт. При App + chat connector всички посетители минават през един акаунт, така че не свързвайте личния си.
- Не ползвайте чужди данни за тестове. Направете си примерни.
- Плащанията пускайте само с помощта на възрастен и след проверка на условията.
- Проверявайте кой е влязъл в приложението ви и какво вижда, преди да го споделите.

На страницата пише, че свързването е безплатно, но там не се разбира дали ползването харчи кредити в Lovable. Вижте [цените](https://lovable.dev/pricing), преди да автоматизирате нещо голямо. Подробности за защитата има в [документацията за сигурност](https://docs.lovable.dev/integrations/security).

## Всички конектори

### Лична продуктивност и съдържание (33)

Тук са документите, календарите, бележките и дизайнът. Оттук започнете, защото това са инструментите, които вече ползвате.

- [Azure Graph & Entra API](https://docs.lovable.dev/integrations/azure-graph): данни за потребители и достъп в Microsoft среда
- [Calendly](https://docs.lovable.dev/integrations/calendly): записване на срещи
- [Canva](https://docs.lovable.dev/integrations/mcp-servers): дизайн на визии и презентации
- [Contentful](https://lovable.dev/connect/contentful): система за управление на съдържание
- [Excalidraw+](https://docs.lovable.dev/integrations/mcp-servers): бързи скици и диаграми
- [Figma MCP](https://docs.lovable.dev/integrations/mcp-servers): дизайн на интерфейси, от който Lovable може да взима контекст
- [Fireflies](https://docs.lovable.dev/integrations/fireflies): записи и обобщения на срещи
- [Gmail](https://lovable.dev/connect/google_mail): четене и изпращане на имейли
- [Google Calendar](https://lovable.dev/connect/google_calendar): събития и графици
- [Google Docs](https://docs.lovable.dev/integrations/google-workspace): текстови документи
- [Google Drive](https://lovable.dev/connect/google_drive): файлове в облака
- [Google Sheets](https://lovable.dev/connect/google_sheets): таблици, често първата проста база данни на един проект
- [Google Slides](https://lovable.dev/connect/google_slides): презентации
- [Granola](https://lovable.dev/connect/granola): бележки от срещи
- [Loom](https://docs.lovable.dev/integrations/mcp-servers): кратки видео съобщения със запис на екрана
- [Lovable API](https://docs.lovable.dev/integrations/lovable-api): управление на Lovable чрез код
- [Microsoft Excel](https://docs.lovable.dev/integrations/microsoft): таблици
- [Microsoft OneDrive](https://docs.lovable.dev/integrations/microsoft): файлове в облака
- [Microsoft OneNote](https://docs.lovable.dev/integrations/microsoft): бележки
- [Microsoft Outlook](https://docs.lovable.dev/integrations/microsoft): поща и календар
- [Microsoft PowerPoint](https://docs.lovable.dev/integrations/microsoft): презентации
- [Microsoft SharePoint](https://docs.lovable.dev/integrations/microsoft): вътрешни документи на организация
- [Microsoft Teams](https://docs.lovable.dev/integrations/microsoft): екипна комуникация
- [Microsoft Word](https://docs.lovable.dev/integrations/microsoft): текстови документи
- [Miro](https://lovable.dev/connect/miro): онлайн бяла дъска за идеи
- [Notion](https://docs.lovable.dev/integrations/mcp-servers): бележки, задачи и бази знания
- [Paper MCP](https://docs.lovable.dev/integrations/mcp-servers): дизайн инструмент
- [Sanity](https://lovable.dev/connect/sanity): система за управление на съдържание
- [Storyblok](https://docs.lovable.dev/integrations/storyblok): система за управление на съдържание
- [Tally](https://docs.lovable.dev/integrations/tally): онлайн формуляри
- [Wispr Flow](https://docs.lovable.dev/integrations/mcp-servers): диктовка, която превръща говор в текст
- [WordPress (собствен хостинг)](https://docs.lovable.dev/integrations/wordpress): сайт на ваш хостинг
- [WordPress.com](https://lovable.dev/connect/wordpress-com): сайт, хостнат от WordPress

### Бизнес и CRM (16)

CRM (управление на взаимоотношенията с клиенти) пази кой е клиентът и какво сме си говорили с него. Тази група е за продажби, екипи и подбор на хора.

- [Airtable](https://docs.lovable.dev/integrations/airtable): таблици, които работят като база данни
- [Apollo.io](https://docs.lovable.dev/integrations/apollo): търсене на потенциални клиенти и контакти
- [Asana](https://lovable.dev/connect/asana): задачи и проекти
- [Ashby](https://docs.lovable.dev/integrations/ashby): подбор на служители
- [Atlassian](https://docs.lovable.dev/integrations/mcp-servers): Jira и Confluence, задачи и документация
- [Attention](https://docs.lovable.dev/integrations/attention): анализ на търговски разговори
- [BambooHR](https://docs.lovable.dev/integrations/bamboohr): данни за служители
- [Clay](https://docs.lovable.dev/integrations/clay): обогатяване на данни за потенциални клиенти
- [Gong](https://docs.lovable.dev/integrations/gong): анализ на търговски разговори
- [Google Ads](https://docs.lovable.dev/features/ads): рекламни кампании в Google
- [HubSpot](https://docs.lovable.dev/integrations/hubspot): CRM и маркетинг
- [Linear](https://lovable.dev/connect/linear): задачи за продуктови екипи
- [Pipedrive](https://docs.lovable.dev/integrations/pipedrive): CRM за продажби
- [Salesforce](https://docs.lovable.dev/integrations/salesforce): голям CRM за компании
- [Zendesk](https://docs.lovable.dev/integrations/zendesk): клиентска поддръжка
- [Zoho CRM](https://docs.lovable.dev/integrations/zoho-crm): CRM за малък и среден бизнес

### Търговия и плащания (15)

Тези конектори ви трябват, когато проектът трябва да продава, да таксува или да издава фактури.

- [Chargebee](https://docs.lovable.dev/integrations/chargebee): абонаменти и таксуване
- [Lexware](https://docs.lovable.dev/integrations/lexware): счетоводство, разпространено в Германия
- [Lightspeed](https://docs.lovable.dev/integrations/lightspeed): продажби в магазини и заведения
- [Mollie](https://docs.lovable.dev/integrations/mollie): онлайн плащания в Европа
- [Polar.sh](https://lovable.dev/connect/polar): продажба на дигитални продукти и абонаменти
- [PrestaShop](https://docs.lovable.dev/integrations/prestashop): онлайн магазин
- [Ramp](https://docs.lovable.dev/integrations/ramp): фирмени разходи
- [Sevdesk](https://docs.lovable.dev/integrations/sevdesk): счетоводство за малък бизнес
- [Shopify](https://docs.lovable.dev/integrations/shopify): онлайн магазин
- [Stripe](https://lovable.dev/connect/stripe): онлайн плащания
- [Wave](https://docs.lovable.dev/integrations/wave): фактури и счетоводство
- [Wix](https://docs.lovable.dev/integrations/wix): сайтове и онлайн магазини
- [WooCommerce](https://docs.lovable.dev/integrations/woocommerce): магазин върху WordPress
- [Xero](https://docs.lovable.dev/integrations/xero): счетоводство
- [Zoho Books](https://docs.lovable.dev/integrations/zoho-books): счетоводство

### Изкуствен интелект и автоматизация (13)

Тук проектът получава глас, търсене в интернет, четене на документи и задачи, които се изпълняват сами.

- [Apify](https://docs.lovable.dev/integrations/apify): събиране на данни от сайтове
- [Custom (собствен MCP)](https://docs.lovable.dev/integrations/mcp-servers): свързване на ваш собствен MCP сървър
- [ElevenLabs](https://docs.lovable.dev/integrations/eleven-labs): генериране на глас
- [Firecrawl](https://docs.lovable.dev/integrations/firecrawl): превръща уебсайтове в данни за AI
- [Fireworks AI](https://docs.lovable.dev/integrations/fireworks): достъп до AI модели
- [Gemini Enterprise](https://docs.lovable.dev/integrations/gemini-enterprise): Gemini за компании
- [HeyGen MCP](https://docs.lovable.dev/integrations/mcp-servers): видеа с AI аватари
- [Inngest](https://docs.lovable.dev/integrations/inngest): задачи, които вървят на заден план
- [LlamaParse Platform](https://docs.lovable.dev/integrations/llamaparse): четене на сложни документи и PDF файлове
- [n8n](https://docs.lovable.dev/integrations/mcp-servers): автоматизация на работни процеси
- [Parallel](https://docs.lovable.dev/integrations/parallel): търсене в интернет за AI агенти
- [Perplexity](https://docs.lovable.dev/integrations/perplexity): търсене с цитирани източници
- [Replicate](https://docs.lovable.dev/integrations/replicate): пускане на различни AI модели

### Данни и анализи (28)

Тази група отговаря на въпроса „работи ли това, което правим?“. За маркетинг най-важни са Google Analytics, Search Console и Semrush.

- [Algolia](https://docs.lovable.dev/integrations/algolia): бързо търсене в сайт
- [Amazon Redshift](https://docs.lovable.dev/integrations/amazon-redshift): склад за големи обеми данни
- [Amplitude](https://lovable.dev/connect/amplitude): анализ на поведението в продукт
- [AWS Athena](https://docs.lovable.dev/integrations/aws-athena): заявки върху данни в облака
- [BigQuery](https://lovable.dev/connect/bigquery): склад за данни на Google
- [ClickHouse](https://docs.lovable.dev/integrations/clickhouse): бърза база за анализи
- [Confidence](https://docs.lovable.dev/integrations/mcp-servers): експерименти и A/B тестове (сравнение на два варианта)
- [Cube](https://docs.lovable.dev/integrations/cube): единни бизнес показатели
- [Databricks](https://lovable.dev/connect/databricks): платформа за данни и AI
- [dbt Semantic Layer](https://docs.lovable.dev/integrations/dbt-semantic-layer): единни дефиниции на показатели
- [FullStory](https://docs.lovable.dev/integrations/mcp-servers): как хората се държат в сайта
- [GoodData](https://docs.lovable.dev/integrations/gooddata): бизнес анализи и табла
- [Google Analytics](https://docs.lovable.dev/integrations/google-analytics): трафик и поведение в сайта
- [Google Search Console](https://docs.lovable.dev/integrations/google-search-console): как ви намират в Google
- [Hex](https://docs.lovable.dev/integrations/mcp-servers): анализи на данни в екип
- [IBM Db2](https://docs.lovable.dev/integrations/ibm-db2): корпоративна база данни
- [Looker](https://docs.lovable.dev/integrations/looker): бизнес анализи и табла
- [Metabase](https://docs.lovable.dev/integrations/metabase): лесни табла с данни
- [Microsoft Fabric](https://docs.lovable.dev/integrations/microsoft-fabric): платформа за данни
- [MotherDuck](https://docs.lovable.dev/integrations/motherduck): база за анализи в облака
- [Neon](https://docs.lovable.dev/integrations/neon): база данни Postgres
- [Omni](https://docs.lovable.dev/integrations/omni): бизнес анализи
- [Oracle Autonomous AI Database](https://docs.lovable.dev/integrations/oracle-autonomous): корпоративна база данни
- [PostHog](https://docs.lovable.dev/integrations/mcp-servers): анализ на продукт и експерименти
- [Power BI](https://docs.lovable.dev/integrations/power-bi): табла с данни на Microsoft
- [Qlik Cloud](https://docs.lovable.dev/integrations/qlik-cloud): бизнес анализи
- [Semrush](https://docs.lovable.dev/integrations/semrush): SEO (оптимизация за търсачки) и анализ на конкуренти
- [Snowflake](https://lovable.dev/connect/snowflake): склад за данни

### Комуникация (14)

Така приложението ви стига до хората: с имейл, съобщение или публикация.

- [Brevo](https://docs.lovable.dev/integrations/brevo): имейл маркетинг
- [Discord](https://docs.lovable.dev/integrations/discord): общности и чат
- [Firebase Cloud Messaging](https://docs.lovable.dev/integrations/firebase-cloud-messaging): известия към телефони
- [GatewayAPI](https://docs.lovable.dev/integrations/gatewayapi): SMS съобщения
- [LinkedIn](https://docs.lovable.dev/integrations/linkedin): професионална социална мрежа
- [Mailgun](https://docs.lovable.dev/integrations/mailgun): автоматични имейли
- [Resend](https://docs.lovable.dev/integrations/resend): автоматични имейли от приложение
- [Slack](https://lovable.dev/connect/slack): екипен чат
- [Telegram](https://lovable.dev/connect/telegram): съобщения и ботове
- [TikTok](https://docs.lovable.dev/integrations/tiktok): кратки видеа
- [Twilio](https://lovable.dev/connect/twilio): SMS и обаждания
- [Twitch](https://docs.lovable.dev/integrations/twitch): стрийминг на живо
- [WhatsApp Business](https://docs.lovable.dev/integrations/whatsapp): съобщения към клиенти
- [X](https://docs.lovable.dev/integrations/x): социална мрежа

### Карти и медия (5)

Малка група, полезна за местен бизнес и за по-жив интерфейс.

- [Google Business Profile](https://docs.lovable.dev/integrations/google-business-profile): профилът на фирма в Google
- [Google Maps](https://lovable.dev/connect/google_maps): карти и адреси
- [KLIPY](https://docs.lovable.dev/integrations/klipy): GIF файлове и стикери
- [Logo.dev](https://docs.lovable.dev/integrations/logo-dev): лога на компании
- [Mapbox](https://lovable.dev/connect/mapbox): карти с ваш дизайн

### Сигурност и инфраструктура (12)

Това е по-техническата част. В началото ще ви трябват най-вече GitHub и Supabase.

- [Aikido](https://docs.lovable.dev/integrations/aikido): проверка на кода за уязвимости
- [Amazon S3](https://docs.lovable.dev/integrations/aws-s3): съхранение на файлове
- [AWS API](https://docs.lovable.dev/integrations/aws): облачните услуги на Amazon
- [Azure Cloud API](https://docs.lovable.dev/integrations/azure): облачните услуги на Microsoft
- [Cloudflare API](https://docs.lovable.dev/integrations/cloudflare-api): домейни, скорост и защита на сайта
- [GitHub](https://lovable.dev/connect/github): хранилище за код
- [GitLab API](https://docs.lovable.dev/integrations/gitlab): хранилище за код
- [Google Cloud API](https://docs.lovable.dev/integrations/gcp): облачните услуги на Google
- [incident.io](https://docs.lovable.dev/integrations/incidentio): управление на технически инциденти
- [Sentry](https://docs.lovable.dev/integrations/mcp-servers): улавяне на грешки в приложението
- [Supabase](https://docs.lovable.dev/integrations/supabase): база данни, вход на потребители и файлове
- [Wiz](https://docs.lovable.dev/integrations/wiz): сигурност в облака
