# Rituale Romanum: how to edit the texts

The page **rituale-romanum.html** shows the Rituale in Latin and English. The prayers are not inside that page; they are in the plain text files in this folder. To change a word, edit the text file and save it. The website updates by itself a minute or two later, so there's no other step.

```
rituale/
  contents.txt     list of the text files, in the order the page loads them
  texts/           one file per section of the book (baptism, marriage, blessings…)
  shared/          psalms, hymns and litanies used in many rites (edit once, changes everywhere)
  README.md        this guide
```

## Making a change on GitHub

1. Go to the repository on github.com and open the folder **rituale**, then **texts**.
2. Open the file for the section you want. The names say what is inside (for example `medals.txt`, `funerals.txt`, `baptism-of-children.txt`). If you don't know which file holds a prayer, use the search box at the top of GitHub, or the search on the website itself, which shows the rite's name.
3. Click the **pencil icon** (Edit this file).
4. Make the change. Each rite begins after a divider line with its English name, so you can scroll to it, or press Ctrl+F / Cmd+F to find a word.
5. Click **Commit changes…**, add a short note about what you changed if you like, and confirm.
6. Wait a minute or two and reload the website.

If something in an edit can't be understood, the page shows a **red box at the top** naming the file and line number to fix. The rest of the page keeps working.

GitHub keeps every earlier version, so a mistake can always be undone: open the file and click **History** to see or restore an older version.

## How the lines work

Each line holds one piece of a rite: **Latin on the left of `||`, English on the right.**

```
# st-benedict-medal | Benedictio Numismatum S. Benedicti | Blessing of St. Benedict Medals | Objects of Devotion | Appendix
r: Sacerdos benedicturus numismata sancti Benedicti, dicit: || The priest who is to bless medals of St. Benedict says:
v: Adjutórium nostrum in nómine Dómini. || Our help is in the name of the Lord.
x: Qui fecit cælum et terram. || Who made heaven and earth.
t: Orémus. || Let us pray.
n: A note shown in English only.
```

| Start of line | What it is | How it appears |
|---|---|---|
| `# ` | Start of a new rite: `id \| Latin title \| English title \| Category \| Reference` | Title of the rite, and its entry in the contents menu |
| `r:` | Rubric (instructions) | Red italic |
| `t:` | Text said or sung: prayers, psalm verses, antiphons | Normal text |
| `h:` | Small heading inside a rite (e.g. *Psalmus 66*) | Dark red small capitals |
| `v:` | Versicle | Begins with ℣. |
| `x:` | Response | Begins with ℟. |
| `n:` | Note in English only (no `\|\|` needed) | Grey box across both columns |
| `@name` | Inserts a shared text from `shared/name.txt` (e.g. `@psalm-50`, `@gloria-patri`) | The whole psalm, hymn or litany |
| `//` | A note for editors; never shown on the page | Hidden |

Empty lines are ignored, so you can space things out however you like.

### Marks inside a line

| Write | Shows as |
|---|---|
| `✠` | A red cross (the sign of the cross). Use the same number of ✠ in the Latin and the English; the page warns you if they differ. |
| `*words*` | Red italic, for a small rubric inside a prayer, e.g. `*(Hic aspergatur aqua benedicta.)*` |
| `_words_` | Plain italic (used for responses in litanies) |
| ` * ` | The pause in the middle of a psalm verse (an asterisk with a space on each side) |
| `℟. Amen.` | The response at the end of a prayer, inside the same line |

To type ✠ ℣ ℟ æ œ ǽ, the easiest way is to copy one from somewhere else in the same file.

## Common tasks

**Correct a word or a translation:** change it in the line and save. Keep the ` || ` (space, two bars, space) between the Latin and the English.

**Add a line:** copy a similar line, paste it where it belongs and change the words.

**Change a psalm or hymn used in many places:** edit it once in `shared/`. Every rite that uses it with `@name` changes too.

**Add a new rite:** add a `# ` heading line in a suitable text file, with an id (short, lowercase, words joined by hyphens) that isn't used anywhere else, then add its lines below. It appears in the menu under the category you gave it. The categories are listed at the start of the program in `rituale-romanum.html` (part 4a).

**Add a new text file:** create it in `texts/` and add its file name as a new line in `contents.txt`.

**Hide a rite or a file for a while:** put `//` in front of its lines, or in front of its name in `contents.txt`.

## Changing how the page looks

The page `rituale-romanum.html` is divided into labeled parts (colors, layout, phone, printing, and the program). The colors are listed at the top of Part 2, and the "About this edition" text is in Part 4d. Each part has notes explaining what it does.

## Note on viewing the page on your own computer

The page reads the text files from the website, so opening `rituale-romanum.html` directly from a downloaded copy on your computer will just say it can't load the texts. Use the live website, or ask Claude to run a local preview.
