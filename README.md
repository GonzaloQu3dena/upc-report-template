# UPC Report Template

<p align="center">
  <img src="https://static.wikia.nocookie.net/logopedia/images/2/2d/UPC-Logo-Actual.png/revision/latest/scale-to-width-down/384?cb=20230305155749&path-prefix=es" alt="UPC Logo" width="300"/>
</p>

## Overview

<p align="justify">
UPC Report Template is a comprehensive framework designed to streamline the documentation process for software projects using a Gitflow-based approach. It enables teams to work collaboratively on different sections of a report by isolating each chapter into its own dedicated branch. This structure ensures that work on specific chapters does not conflict with others and facilitates incremental deliveries.
</p>

## Features

- **Gitflow Strategy**: Each chapter is developed in a specific branch (e.g., `docs/chapter-i`), using `develop` for intermediate integrations and keeping `main` clean until final consolidation.
- **Incremental Deliveries**: Facilitates the export of individual chapters for partial submissions.
- **PDF Ready**: Content is structured to be easily exported to PDF.
- **Scalable**: Easily extensible for additional chapters or sections.

## Workflow & Usage

### 1. Working on Chapters

<p align="justify">
The documentation is divided into branches corresponding to each chapter. To work on a specific section, switch to the relevant branch:
</p>

```bash
git checkout docs/chapter-i
```

### 2. Formatting for Export

<p align="justify">
To ensure proper formatting when exporting to PDF (especially for merging later), every markdown file representing a chapter must end with the following HTML snippet to enforce a page break:
</p>

```html
<div style="page-break-after: always;"></div>
```

### 3. Intermediate Deliveries (Develop Branch)

<p align="justify">
For partial deliveries, it is recommended to merge the branches of the required chapters into a `develop` branch. This allows for an integrated version of the current progress without modifying the `main` branch.
</p>

```bash
git checkout develop
git merge docs/chapter-i
git merge docs/chapter-ii
```

### 4. Exporting and Merging

<p align="justify">
For each delivery, export the respective markdown files to PDF. To combine the cover, individual chapters, and appendices into a single document, use the following tool:
</p>

- **[Merge PDF Files (iLovePDF)](https://www.ilovepdf.com/es/unir_pdf)**

**Order of operations:**
1.  Export the Front Matter (Cover).
2.  Export the specific Chapter(s).
3.  Export the Back Matter (References, Appendices).
4.  Upload them in order to the merging tool and generate the final PDF.

### 5. Extending the Documentation

<p align="justify">
This repository serves as a base template. If your project requires additional chapters:
</p>

1.  Ensure you are on the `main` branch.
2.  Create a new branch for the new chapter:

```bash
git checkout main
git checkout -b docs/chapter-name
```

3.  Repeat the writing and formatting steps described above.

### 6. Final Consolidation

<p align="justify">
Upon completion of all deliveries and final review, all chapter branches should be merged into `main`. This action signifies that the report is consolidated and represents the final version of the project documentation.
</p>

```bash
git checkout main
git merge docs/chapter-i
git merge docs/chapter-ii
# ... repeat for all chapters
```

## Tools

- **Git**: For version control and branch management.
- **Markdown**: For content creation.
- **PDF Converter**: Any Markdown-to-PDF converter (e.g., VS Code extensions, Pandoc).
- **iLovePDF**: For merging final documents.

## Contributing

<p align="justify">
Contributions to improve this template are welcome. Please ensure that the branch structure is respected when submitting pull requests.
</p>
