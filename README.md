# md-like-html-text-editor
This is my text editor made in html, which has text editing similar to those of .md files'. I created it mostly for myself, for a certain project, a short story, actually, but who cares. It's pretty simple, I might update it, I might not. 

## How I made this project
### 1. The idea
  I really like the Discord and md formatting system. It is easy to get into, remember it, and forget that other chatting websites/apps(referring to Discord) don't have that formatting. I was also thinking about making a short story, just to train my english skills and to put the idea of it into creation, because I already an outline in my mind for a few days already. However, I didn't exactly like most of the text editors out there. They either were too complicated, not good enough, silly-looking... I needed something easy to use, easy to get into, easy to share and most importantly, something that doesn't require an active internet connection. Now, this may sound kind of silly, but this was a huge deal-breaker for me, as I really wanted to have such a tool that I can use whenever I want. Anyways, me being a web designer and all, I decided to fuck it, why not make one myself?
### 2. The original design
  The original design was absolute dogshit ngl. I mean, I still kept most of it, but overall it was pretty fucking shit. Seriously. Here is a picture:
  ![Tools Here (1)](https://github.com/user-attachments/assets/cddbe706-069e-4ab4-b39e-dbb2b1ab72ba)
Like, this shit didn't even have a TITLE EDITOR! Then, I decided to add *some* stuff, and came up with this:
![Tools Here (3)](https://github.com/user-attachments/assets/eadcf75c-fe20-4189-af2c-7b6ea6af1452)
Still absolute dawg shi... And that's all thanks to the text tool bar or whatever. Like, what the hell was I thinking??? Why the fuck would I make a text tool bar for a text editor that is designed not to require any buttons for formatting?? Who cares, in the end, I didn't implement it anyway. Overall my design here was pretty shit, but, I rolled with it at start, and just freestyled my way through, which also lead me to adding a help button in case anyone wants to know the way around cuz they didn't use something like this before. This is my first design of the help popup menu:
![Tools Here (4)](https://github.com/user-attachments/assets/dee23999-00ef-4874-abfb-2390507040f1)
Yes I actually typed to myself "notice how bla bla" whatever, I'm like, stupid af anyway(just look at my obsession with 40px in the pictures!! Like, bruh, I dunno what was I thinking. It was like, about 12am, though, that could explain my incompetence...). And this is my final original design:
![Tools Here (7)](https://github.com/user-attachments/assets/ba7912b6-a9d3-4597-bdac-8278d8fc2ab6)
don't mind the file names btw.. Also as you can notice nothing much changed. Seriously. Just added a bit more text to clear shit up.

Now, this does suck, but I made this shit in one night(of course with help of a certain friend haha(I love Windsurf... and I hate JavaScript......)).
In the end, I did 17px of border-radius and def not 40px of spacing between them. On the design it looked better at 40px but it was also pretty massive... and you know what else is massive? LOOOOWWWWW-
Ekhm, anyways...
### 3. The final design
<img width="1640" alt="kocham alternatywki" src="https://github.com/user-attachments/assets/642706c7-ef61-4b34-b112-c7b9d5a967f3" />
Yup... this is the final design. I know it is not the best, but then again, I started coding this shit at like, 1:30, until then I was just designing it and trying to come up with a list of shi that needs to be done. Btw, this is it(yes i put it in an md lol):
# Markdown-Like Text Editor Web App – SPECIFICATION!!!!! [image](https://github.com/user-attachments/assets/a5cedeae-3b18-4dde-bea9-afe1d69705d2)


This document outlines the feature set and tasks required for building a browser-based, markdown-style text editor interface. The editor supports multiple text sections, md-like formatting, a dual text mode (normal/advanced), JSON export, HTML rendering with scoped styling, and a full-page help popup.

---

## General Functionality

### 1. Text Editor Page Structure

- The base page consists of a title editor and one or more text input sections.
- A "+" button adds a new section for text input.
- Each text input section gets turned into a `<p>` element with:
  - Class `.p` and `.p1`, `.p2`, etc. for ordering.
  - Scoped under a parent class based on the title (`.My-Section`).

---

### 2. Section Types

When adding a new writing area, offer two options:

- **Normal Mode**
  - HTML tags like `<div>` are escaped.
  - Supports only markdown-like formatting (see below).

- **Advanced Mode**
  - Allows raw HTML like `<div>`, `<a>`, `<button>`, etc.
  - HTML elements are preserved and exported.
  - HTML elements get a class of `[title]-Item`.

---

### 3. Rendering Mode

- A button toggles "rendered" mode, converting all input areas into formatted `<p>` tags.
- All formatting is applied according to the md-like rules.
- Output is ready for export.

---

### 4. Export Buttons

- **Export as JSON**
  - Contains raw content of each section.
  - Maintains structure and order.

- **Export as HTML**
  - Wrapped in a `<section class="[title-class]">`.
  - Includes a `<style>` tag with scoped CSS (e.g. `.Title .p b`).
  - Pre-built theme matching the editor’s design.

---

### 5. Help Button

- A circular `?` button in the text tools bar.
- On click, opens a full-page popup with formatting instructions.
  - Popup dims the background (120px padding on all sides).
  - Clicking outside the popup closes it with a smooth animation.
  - Style follows layout described in the second picture.

---

## Markdown-Like Formatting Rules

> These formatting rules must be supported and stylable in CSS.

| Syntax            | Output Tag              |
|------------------|--------------------------|
| `*text*`         | `<em>`                   |
| `**text**`       | `<strong>`               |
| `***text***`     | `<em><strong>`           |
| `# Text`         | `<h1>`                   |
| `## Text`        | `<h2>`                   |
| `### Text`       | `<h3>`                   |
| `(text)[link]`   | `<a href="link">text</a>`|
| `~text~`         | `<s>`                    |
| `_text_`         | `<u>`                    |
| `{text}`         | `<code>`                 |
| `||spoiler||`    | Spoiler tag              |
| `\`              | Escape character         |

### Nesting & Matching Rules

- Formatting must use strict open-close matching:
  - `*...*` ends only at the next `*`, unless escaped.
  - Inner tags don’t close outer tags.
  - Escape `\` disables parsing.

---

## Visual & Theme Styling

### Color Palette

| Element                       | Color       |
|------------------------------|-------------|
| Borders                      | `#5b5b5b`   |
| Toolbars & Writing Sections  | `#2d2c39`   |
| Writing Container Div        | `#323140`   |
| Buttons                      | `#3f3d50`   |
| Background                   | `#0c0b17`   |

### Borders

- All elements: `1px solid #5b5b5b`
- Title editor: `3px dashed #5b5b5b`

---


Now, I did ask chatGPT to clear shit up so I can see it better, but whatever.
I did also ask it to already class them cuz I didn't wanna waste time. Then I implemented my original design, tweaked it and that shit came outta it. Here is another picture, with a picture of the help popup as well:
<img width="1660" alt="image" src="https://github.com/user-attachments/assets/de8b1c65-e767-4c85-a520-08ccd20ddd93" />
<img width="1660" alt="image" src="https://github.com/user-attachments/assets/af96f4fb-ea77-45c5-9843-8828834c37a7" />
also if ur wondering what the copy toggle is, it changes modes between copy and file mode. No idea why I added it tbh, but who the hell cares.

### That's it lol
I wanna drive to the nearest bridge and fucking... take a walk or smth.

Enjoy if you want to, or don't, I really don't care. Also, writing this README took me 40 minutes, fuck my life <3

