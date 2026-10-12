---
name: mads-translate
description: Translate or localize text (UI strings, app copy, push notifications, errors, docs, marketing, messages) so it reads as if it was originally written in the target language. Use whenever the user asks to translate, localize, or adapt text or string files into another language.
---

# Natural translation

The goal: a native reader of the target language must not be able to tell the text was translated. Translate the **intent**, not the words or the sentence structure.

## 1. Before translating

1. Pin down:
   - target language and locale (ru-RU, uz-Latn-UZ, en-US...);
   - text type: UI label, button, error, push, onboarding, marketing, legal, docs, chat;
   - audience and register: formal or informal address, tone of the product.
2. Look for project conventions and follow them over this file: `glossary.*`, `styleguide.*`, `l10n/`, `locales/`, translator comments in `.po`, `.xliff`, `.strings`, `.arb` files, existing translations in the repo (match their terminology and tone).
3. If the target language has an appendix at the end of this file (for example "Appendix: Russian"), apply it.
4. Short ambiguous strings ("Open", "Free", "Post", "Clear") cannot be translated without context. Check where the string is used in code. If still unclear, ask, or pick the most likely reading and flag it.

## 2. Process for every text unit

1. **Understand the function.** What does the text do: instruct, confirm, warn, apologize, persuade, label? What should the reader feel or do after reading it?
2. **Drop the source structure.** Ask: "How would a native professional say this if they were writing this product from scratch in their own language?"
3. **Write it** in the target language.
4. **Run the calque check** (section 4).
5. **Read-aloud test.** If a native speaker would never say or write it this way, rewrite.

## 3. Rules

- **Idioms and set phrases:** replace with a target-language expression that has the same function, or with plain wording. Never translate literally.
- **Restructure freely:** split or merge sentences, change word order, switch passive to active, use verbs instead of nouns, drop filler ("please note that", "simply", "just").
- **Never change:** meaning, facts, numbers, legal or safety meaning, placeholders (`{name}`, `%d`, `%@`, `{{count}}`, `$1`), HTML or markup tags, string keys, URLs, brand and product names (unless an established localized name exists).
- **Don't add** information that isn't in the source, **don't drop** information the reader needs.
- **Consistency:** one source term = one translation across the whole job.
- **Locale formats:** dates, times, numbers, decimal and thousands separators, currency, quotation marks, units.
- **Dashes:** no long dash (U+2014) in the translation, in any language, even when the source has one. A short dash or a hyphen with spaces in its place is not allowed either. Use a comma, colon, parentheses or a period, or rephrase. A numeric range takes a short dash (U+2013) without spaces: 100–200.
- **Plurals:** use the plural categories of the target language (ICU MessageFormat or the platform's plural mechanism). If the source builds sentences by concatenating fragments, flag it: it usually can't be localized correctly.
- **Gender:** if the gender of a person is unknown, use constructions that avoid gendered forms.
- **Length:** for UI strings keep the length close to the source. If the natural version is much longer, give a shorter alternative.
- **Humor and wordplay:** recreate the effect, not the words. If that's impossible, flag it and offer options.
- **Legal, medical, financial, safety text:** accuracy beats style. Keep the meaning exact and flag anything uncertain.

## 4. Calque check (universal red flags)

- Source word order kept where the target language orders differently.
- Passive voice where the target language prefers active.
- Chains of nouns and nominalizations ("execution of the process of verification").
- Possessive pronouns everywhere ("your account", "your settings") where the target language omits them.
- False friends.
- Title Case copied into a language that doesn't use it.
- Source punctuation copied: quote style, exclamation marks, ellipses, colons.
- Politeness markers copied mechanically ("please" in every string).
- Exclamation-heavy enthusiasm that sounds unnatural in the target culture.
- Words that are technically correct but nobody uses in this context.

## 5. Output

- By default output **only the translation**, in the same format as the input.
- For string files (`.json`, `.strings`, `.xml`, `.po`, `.arb`, `.xliff`, `.yaml`): translate values only, never keys; preserve escaping, placeholders, order and comments.
- After the translation, add a short **Notes** block only if something matters:
  - an idiom, joke or wordplay was adapted;
  - meaning-bearing structure was changed significantly;
  - an ambiguity was resolved by guessing;
  - a length risk or a concatenation / plural problem was found.
  Write notes in the language the user is talking to you in. If there's nothing to note, skip the block.
- If the user asks for options, give 2–3 variants that differ in tone or length, not cosmetic rewordings.

## 6. Examples (en → ru)

| Source | Literal (bad) | Natural |
|---|---|---|
| You're all set! | Вы все установлены! | Готово! |
| Something went wrong. Please try again. | Что-то пошло не так. Пожалуйста, попробуйте снова. | Не получилось. Попробуйте ещё раз |
| Your request has been successfully processed. | Ваш запрос был успешно обработан. | Заявка принята |
| Piece of cake | Кусок торта | Проще простого |
| Don't miss out! | Не пропустите! | Успейте, пока действует |
| Create New Project | Создать Новый Проект | Создать проект |
| You have {n} new messages | У вас есть {n} новых сообщений | {n} новое сообщение / новых сообщения / новых сообщений (ICU plural) |

---

# Appendix: Russian (ru) specifics

## Register
- Default for products: «вы» with lowercase «в». Capital «Вы» only in personal letters and official correspondence, never in UI.
- «ты» only if the product's style guide says so (youth, gaming, playful brands). Never mix «ты» and «вы».

## Grammar and structure
- **Plurals: 3 forms** (one / few / many): 1 файл, 2 файла, 5 файлов; 21 файл, 22 файла, 25 файлов, 11–14 → «файлов». Always use ICU plural with `one`, `few`, `many`, `other`.
- **Gender:** past tense verbs and adjectives agree with gender («удалил / удалила»). If unknown, use impersonal or passive-participle forms: «Удалено пользователем {name}», «{name}: сообщение удалено».
- **Avoid канцелярит:** «осуществить», «произвести оплату», «в целях», «данный», «является», «в случае если», «на сегодняшний день». Write «оплатить», «чтобы», «этот», «если».
- **Verbs instead of nouns:** «Восстановление пароля осуществляется по ссылке» → «Восстановить пароль можно по ссылке».
- **Active instead of passive:** «Ваш платёж был отклонён банком» → «Банк отклонил платёж».
- **Drop extra «ваш»:** «Введите ваш пароль» → «Введите пароль».
- **«Пожалуйста»** sparingly. Russian imperative with «вы» is already polite.
- **Buttons:** infinitive or imperative, keep the style consistent across the product. Common pattern: buttons in infinitive («Сохранить», «Отменить»), instructions in imperative («Введите код»).

## Punctuation and typography
- Quotes: «ёлочки», nested „лапки“.
- No long dash, as in section 3. Hyphen inside words.
- No Title Case: only the first word and proper nouns are capitalized.
- No period at the end of buttons, labels, headings, single-sentence toasts.
- «ё»: follow the project convention; if none, use «ё» where it prevents misreading (всё / все).

## Formats
- Date: 12.10.2026 or «12 октября 2026 г.»; time 24-hour: 14:30.
- Numbers: decimal comma (3,5), thousands separated by a non-breaking space (1 000 000).
- Currency after the number with a space: 1 500 ₽, 120 000 сум.
- Units with a space: 5 МБ, 10 км.

## Length
- Russian is usually 15–30% longer than English. For buttons and tabs, look for shorter synonyms («Настройки» not «Параметры конфигурации»).

## Common calques from English
| English | Calque | Natural |
|---|---|---|
| Are you sure? | Вы уверены? | Удалить чат? (name the action) |
| Learn more | Узнать больше | Подробнее |
| Sign in / Log in | Войти в систему | Войти |
| Got it | Понял | Понятно / Хорошо |
| Stay tuned | Оставайтесь на связи | Скоро расскажем больше |
| Unlock | Разблокировать (for features) | Открыть доступ |
| Feel free to... | Чувствуйте себя свободно... | Можете... / drop it |
| We're sorry | Мы сожалеем | Извините |
| Oops! | Упс! | drop it, state the problem |
