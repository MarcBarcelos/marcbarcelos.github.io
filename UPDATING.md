# Updating your site

Every change you push to the `main` branch goes live automatically within about 2 minutes. You can do everything below directly on github.com: open the file, click the pencil icon ("Edit this file"), make the change, and click **Commit changes**. To upload a file (a PDF or photo), open the folder on GitHub and use **Add file → Upload files**.

YAML files (the ones ending in `.yaml`) are sensitive to indentation: copy an existing entry, paste it, and change the text, keeping the spaces at the start of each line exactly the same. Put text in "double quotes".

## 1. Add a new paper

Edit `data/papers.yaml` and add an entry (newest first within each group):

```yaml
- title: "My New Paper"
  authors: ["Marc Alexander Barcelos", "Coauthor Name"]
  year: 2027
  status: "working paper"   # published | accepted | revise and resubmit | under review | working paper | work in progress
  venue: ""                 # journal name, once published
  pdf: "files/my-new-paper.pdf"   # optional: upload the PDF to static/files/
  link: ""                  # optional: DOI or external link
  abstract: ""
  job_market_paper: false
```

`work in progress` is shown on the site as **In preparation**. If there's a PDF, upload it to `static/files/` with the same name you used in `pdf:`.

## 2. Update your bio

The bio paragraphs, supervisors, affiliations and research interests are in `content/_index.md`. Your title, tagline, email and social links are in `hugo.yaml` under `params`.

## 3. Add a teaching entry

Edit `data/teaching.yaml`:

```yaml
- course: "Course name"
  role: "Lecturer"          # or Teaching Assistant, Instructor…
  institution: "Aarhus University"
  term: "Spring 2027"
```

## 4. Add a talk

Edit `data/talks.yaml` and add an entry at the top (`with:` and `role:` are optional).

## 5. Add a blog post

Create a new file `content/blog/your-post-slug/index.md`:

```yaml
---
title: "Post Title"
date: 2027-03-15
description: "One-sentence summary."
---

Your text here, in Markdown.
```

Then add a "Blog" item to the `menu` in `hugo.yaml` (`url: "/blog/"`) so visitors can find it.

## 6. Update your CV

Replace `static/files/cv.pdf` with the new version, **keeping the filename `cv.pdf`**, so every link to it keeps working.

## 7. Change your photo

Replace `static/images/photo.jpg` with a new file of the same name. A portrait about 400 × 600 pixels (2:3) works best.

## 8. Add a news item

Edit `data/news.yaml` and add an entry at the top. The homepage shows the six most recent.

## 9. Mark a paper as published

In `data/papers.yaml`, change its `status` to `"published"`, fill in `venue` (for example `"Journal of Cultural Analytics 9(2)"`), and add the DOI to `link`.

## 10. Add your job market paper

Set `job_market_paper: true` on that entry in `data/papers.yaml` and fill in its `abstract`. It will appear as a highlighted card at the top of the Papers section.

## 11. Change the look of the site

The colours and fonts are set at the top of `assets/css/style.css`. For a completely fresh look, ask your assistant to run the design quest at https://gking.harvard.edu/mysite/files/QUEST_DESIGN.md and show you three previews. The current look is recorded in `hugo.yaml` under `params.mysite.design`.
