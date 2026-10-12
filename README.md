# mads text skills

![Before and after examples for mads-humanizer, mads-uxwrite and mads-translate](docs/cover.png)

Three skills for Claude Code. Each one is a set of rules that Claude loads before it writes a certain kind of text.

| Skill | Command | Claude uses it for |
|---|---|---|
| [mads-humanizer](mads-humanizer/SKILL.md) | `/mads-humanizer` | Any text a person will read, and requests to check a text for AI tells or rewrite it |
| [mads-uxwrite](mads-uxwrite/SKILL.md) | `/mads-uxwrite` | Interface strings: buttons, titles, field labels, errors, empty states, push notifications, string catalogs |
| [mads-translate](mads-translate/SKILL.md) | `/mads-translate` | Translating and localizing text or string files |

All three skills work on text in any language. mads-humanizer and mads-translate are written in English, mads-uxwrite is written in Russian.

## What each skill does

### mads-humanizer

The skill lists the patterns that mark generated text and bans them: inflated significance, promotional adjectives, chatbot openers and closers, closing summaries, vague authorities, the long dash. Most bans come with phrase lists in Russian and English, and each one says what to write in its place. Before sending a text Claude answers six check questions about it.

The rules come from the Russian Wikipedia essay [Признаки сгенерированности текста](https://ru.wikipedia.org/wiki/Википедия:Признаки_сгенерированности_текста) (“Signs of generated text”). The phrase lists are Russian and English, and the same patterns are banned in any other language. The skill gives no guarantee that a text passes AI detectors such as GPTZero. It removes the patterns a reader notices.

### mads-uxwrite

Every interface string goes through two passes. The first pass decides what the string says: the title states what happened, the button names the action it triggers, the message tells the user what to do now. The second pass decides how the string is typeset: non-breaking spaces, real symbols such as −, × and ², quotation marks, and the formats of numbers, dates and currency. [TYPOGRAPHY.md](mads-uxwrite/TYPOGRAPHY.md) covers rarer cases: phone and card numbers, ranges, abbreviations, lists.

The first pass does not depend on the language. The second pass has rules common to all languages and a table of norms for Russian and English: «128 000 $» in a Russian string is “$128,000” in an English one. For any other language Claude takes the norms from the product style guide, the locale formatter and the typographic conventions of that language, and says so when it does not know a norm.

The common rules and the Russian norms follow the Kontur guides on [screen typography](https://guides.kontur.ru/principles/text/typography/) and [interface text](https://guides.kontur.ru/principles/text/styleguide/).

### mads-translate

Claude translates the intent of a string. It works out what the string does, writes it the way a native author would, then checks the result for calques: source word order, passive voice, copied punctuation, false friends. Placeholders, markup tags, string keys, numbers and URLs stay as they are. In string files Claude translates values only.

The skill has an appendix for Russian: register, plural forms, typography, number and date formats, common calques from English.

## Install

With the [skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add azizmadjitov/mads-text-skill
```

By default the CLI installs into the current project. Add `-g` to install for your user, `-s mads-translate` to install one skill, `-l` to list the skills without installing.

Without the CLI, clone the repository and copy the three folders:

```bash
git clone https://github.com/azizmadjitov/mads-text-skill.git
mkdir -p ~/.claude/skills
cp -R mads-text-skill/mads-* ~/.claude/skills/
```

To install for one project, copy the folders into `.claude/skills/` inside that project.

## Use

Type a command in Claude Code and add the task:

```
/mads-translate translate locales/en.json into Russian
```

Claude also loads a skill without the command when the task matches the skill description, for example when you ask it to translate a file.

## License

[MIT](LICENSE)
