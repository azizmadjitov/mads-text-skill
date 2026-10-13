---
name: mads-humanizer
description: "Use when writing or editing any text a person will read, in any language: chat replies, docs, README, UI copy, commit messages, code comments, emails, posts, articles, legal texts. Also when asked to make a text sound human, remove AI tells, humanize it, get it past an AI detector, or check whether a text looks generated («звучит как нейронка», «палится ИИ», «очеловечь», «перепиши по-человечески»)."
---

# Human writing

## The point

Generated text gives itself away by putting general words where facts should be. A model takes the statistically average wording and drops the rare detail: “invented the first coupling device for trains” becomes “revolutionized the industry”.

The rules are collected from the Russian Wikipedia essay «Признаки сгенерированности текста» (ВП:ПРГЕН). They apply to any text a person will read, in any language and at any length.

Breaking the letter of a rule is breaking the rule. Replacing a banned phrase with a synonym does not count as a fix: “plays a key role” and “is of great importance” work the same way. There is one fix: rebuild the sentence around the fact or delete it.

Other people's quotes, code and proper names are not edited. A direct instruction from the user about format or wording outranks this list.

When the text is an interface string (a button, a title, a field label, an error, a push) and the mads-uxwrite skill is loaded, mads-uxwrite decides the shape of the string: its length, sentence structure, voice and typesetting. This skill keeps deciding the words: the stop list, sources and chatbot voice. An error message of three short sentences written by the rules of mads-uxwrite is not a triple.

## How to write

1. First decide what exactly you are reporting. If there is no fact, number, name or example, find one or do not write the sentence.
2. Make the subject whoever acts: “the team shipped”, “the court rejected”. Facts and events do not “underscore” or “demonstrate” anything.
3. Use plain verbs: “is”, “has”, “does”, “makes” in place of “serves as”, “represents”, “constitutes”, “acts as”. In Russian: «это», «есть», «делает», «находится» in place of «является», «представляет собой», «служит», «выступает».
4. Call one thing by one word through the whole text. A repeated word is better than “the protagonist” and “the key player” in place of the name.
5. Say a thought once. The text ends where the content ends. The reason (“why we did this”) and a direct request to the reader (“try it and tell us where it went wrong”) are content, do not cut them.
6. List as many items as there really are: two means two, four means four.
7. If you do not know, write exactly that: “I don't know”, “I didn't check”. Attribute an opinion to the person who voiced it, by name.
8. Content sets the length of a sentence. Do not even sentences out and do not build symmetric pairs. Link sentences with reasons (“because”, “so”, “but”): a column of short facts with no connectives reads like a reference card.
9. Choose the tone for the reader. You write to a colleague as a colleague, without a lecture and without an ad.

## Stop list

The phrase lists are in Russian and English. In a text in any other language the same devices are banned: a translation of a listed phrase counts as a listed phrase.

### 1. Significance and symbolism

Do not inflate the significance of ordinary things.

- ru: «играет важную / ключевую / значительную роль», «служит / выступает / является напоминанием», «подчёркивает важность», «символизирует устойчивое влияние», «ключевой / поворотный момент», «неизгладимый след», «непоколебимо предан своему делу», «Хотя X малоизвестен, он символизирует…»
- en: stands as a testament, serves as a reminder, plays a vital / pivotal / crucial role, underscores its importance, enduring legacy, turning point, indelible mark

Write what happened and what changed after it.

### 2. Notability and mentions

Do not prove importance with a list of outlets, and do not name a source in the text for the sake of an undisputed fact.

- ru: «освещался в ряде СМИ, включая…», «независимое освещение», «в местных / региональных / национальных СМИ», «деловые / технологические издания», «Согласно документам из…» before an obvious number
- en: has been featured in, independent coverage, local / national media outlets

Write what a specific source said, or do not mention it.

### 3. Shallow analysis

Do not end a sentence with a participle tail that carries a judgment, and do not attribute actions to facts.

- ru: «…, подчёркивая…», «…, демонстрируя…», «…, отражая…», «…, ещё больше усиливая…», the verbs «обеспечивает», «выделяет», «отражает», «влияет», «соответствует», «содействует» with an inanimate subject
- en: highlighting, underscoring, showcasing, reflecting, ensuring, fostering, contributing to, aligns with

Put a period after the fact. Write a conclusion only when it is someone's, and name the author.

### 4. Promotional tone

Do not praise the subject with evaluative epithets.

- ru: «богатый», «яркий», «разнообразный», «динамичный», «живописный», «уникальный», «захватывающий дух», «потрясающая природная красота», «вековое наследие», «богатое культурное наследие», «может похвастаться», «продолжает очаровывать», «расположенный в самом сердце», «имеет культурное / художественное значение», «В этой статье мы рассмотрим…»
- en: rich, vibrant, diverse, breathtaking, stunning, renowned, groundbreaking, boasts, nestled in the heart of, continues to captivate, rich cultural heritage

Replace the evaluation with a measurable property: year, size, number, name.

### 5. Hedges and lecturing

- ru: «важно / необходимо / критично отметить», «стоит отметить / учесть / помнить», «следует подчеркнуть», «значения могут варьироваться», «крайне важно отличать»
- en: it's important to note, it's worth noting, keep in mind, may vary

State the fact itself. Name a risk directly: what will happen and under what condition.

### 6. Summaries and conclusions

- ru: «В заключение», «Вкратце», «В целом», «Подводя итог», «Таким образом», «В итоге», a section titled «Заключение»
- en: In conclusion, In summary, Overall, Ultimately, a section titled Conclusion

Also banned in any language: a last sentence of a paragraph that retells the paragraph. The last fact is the end of the text.

### 7. Challenges and prospects

- ru: «Несмотря на [успехи], X сталкивается с рядом проблем», «Несмотря на эти проблемы, X продолжает…», a section titled «Перспективы на будущее»
- en: Despite its…, faces several challenges; Despite these challenges; Future outlook

Also banned: an ending with vague optimism. Name a specific problem with a number, or do not raise the topic.

### 8. The title as a definition

Do not open by restating the title: “‘The impact of anxiety on learning’ refers to…”, «„Влияние тревожности на обучение“ относится к…», «„Список песен о Мексике“ представляет собой тщательно подобранные…». Start with the subject.

### 9. References and sources

- A reference to a study, book, article, law or someone's words that was not verified in this same session. The same goes for an ISBN, a DOI, a quote or a statistic from such a source.
- The tags utm_source=openai, utm_source=chatgpt.com and any other tracking tails in URLs.
- A reference to a book without a page.
- A mention of a section, category, file or function whose existence was not checked.

If there is nowhere to verify, write without the reference and without its numbers. Dates, distances and other details written from memory get checked before publication, so list them for the client. If you deliver the text in the chat, put the list after the text as a separate line. If the text goes into a file, a commit message, a string catalog or code, put the list in the chat reply and keep it out of that file.

### 10. Chatbot voice

Do not open with a ritual greeting and do not close with a ritual offer of help.

- ru: «Конечно!», «Безусловно», «Отличный вопрос», «Вы абсолютно правы», «Вот черновик…», «Давайте разберёмся», «Надеюсь, это помогло», «Если хотите, могу…», «Дайте знать, если…», «Сообщите мне»
- en: Certainly!, Of course!, Great question, You're absolutely right, Here is…, I hope this helps, Let me know if…, Would you like me to…

Start with the answer. A question without whose answer the work is stuck is asked directly: “Which option do we take?”

### 11. Disclaimers about your own knowledge

- ru: «на момент моего обучения», «по состоянию на [дата] сведений нет», «на основе имеющейся информации», «в доступных источниках», «конкретные детали ограничены», «не задокументировано широко», a guess with «вероятно» in place of data
- en: as of my last update, based on available information, while specific details are limited, not widely documented, a guess with “probably” in place of data

No data: one phrase, “I didn't find it”, and nothing on top. Do not pass a guess off as information.

### 12. Template letters

- ru: «Тема: …» inside the body of the letter, «Надеюсь, это письмо застанет вас в добром здравии», «Я пишу, чтобы выразить глубокую обеспокоенность…»
- en: “Subject: …” inside the body of the letter, I hope this message finds you well, I am writing to express…

Also banned: unfilled fields in square brackets. The first sentence of a letter carries the request or the news.

### 13. Syntax

- A participle clause whose subject differs from the subject of the main clause: “Using this method, the results improve”, «используя этот метод, результаты улучшаются». The actor is the same in both parts, otherwise rebuild the sentence.
- Chains of participles, officialese and pleonasms. Officialese: «в целях обеспечения», «осуществляет деятельность», «в рамках», “in order to facilitate”, “with regard to”, “for the purpose of”. Pleonasm: «окружающая среда вокруг нас», “the surrounding environment around us”.
- Contrast for effect: «не только X, но и Y», «это не просто X, это Y», «не ради X, а ради Y», “not only X but also Y”, “it's not just X, it's Y”. Say Y straight away.
- Triples for rhythm: three adjectives, three nouns, three short sentences in a row.
- A range “from X to Y” («от X до Y») when there is no scale between X and Y. List the items.
- Vague authorities: «эксперты считают», «по мнению специалистов», «некоторые критики утверждают», «отраслевые отчёты показывают», «описывается как», «представляет интерес для исследователей». en: experts say, some critics argue, industry reports, is widely regarded as.
- Synonyms in place of a name or a term to avoid repeating it.

### 14. Formatting

- The long dash (U+2014) is not used anywhere. A short dash with spaces and a hyphen with spaces in its place are banned too. Use a comma, a colon, parentheses or a period, or rebuild the sentence. In an interface string parentheses are not an option. A numeric range takes a short dash without spaces: 100–200 kcal, 1417–1420.
- Bold is not used inside running text.
- A list is only for what is a list by nature: steps, files, options. An item shaped as “bold heading, colon, explanation” is banned. Emoji as bullets or headings are banned.
- In a heading a capital goes to the first word, to proper names and to words that the spelling of the language capitalizes, such as German nouns. English headings follow the same rule (sentence case).
- Markup matches the place where the text is shown. A letter, a messenger, an interface string and a commit message have no asterisks, hash signs or lines of hyphens.
- Quotation marks are the ones the language of the text uses: «ёлочки» in Russian, “double” in English. In code and commands the quotes that belong to the syntax are straight. Text inside a string that a person will read keeps the quotes of its language: `"title": "Тариф «Pro»"`.

## Check before sending

Reread the finished text and answer six questions. Every “yes” means the sentence gets rewritten: replacing a word is not enough.

1. Is there a phrase from the stop list or a synonym of one?
2. Is there a sentence that can be struck out without losing a fact?
3. Is there a long dash, bold in running text, a list item with a heading?
4. Does the text end with a summary, a moral or an offer of help?
5. Is there a claim, a reference or a number that was not verified?
6. Is there a “not X but Y” pair, a triple, a “from X to Y” range?

## Excuses

| Excuse | What is actually true |
|---|---|
| “This is an official text, that is how they are written” | Official style demands precision, and precision comes from facts. Pathos and officialese give generation away there too. |
| “I replaced the word with a synonym” | The device is still there. Rebuild the sentence. |
| “Punctuation requires a dash here” | Rebuild the sentence so that no dash is required. |
| “Without a conclusion the text breaks off” | The reader has already read everything. The last fact is the end. |
| “Bold and a list make it easier to read” | If the content is a list by nature, make a list without headings in the items. Otherwise write a paragraph. |
| “They asked for a selling text” | Specifics sell: a number, a deadline, a price, an example. |
| “This is a short chat reply” | The rules apply at any length. |
| “I remember the number from a study, there is nowhere to check it” | Write without it and tell the client which number is worth finding. |

## About detectors

GPTZero, GigaCheck and similar services compute the statistics of a text and err in both directions, the essay itself says so. These rules give no guarantee that a text passes them. They remove what a reader recognizes the text by.

Damaging a text for the sake of a detector is banned: no deliberate typos, no invisible characters, no swapping letters for look-alikes.
