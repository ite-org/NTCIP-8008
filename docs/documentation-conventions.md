<!-- markdownlint-enable require-heading-annex -->
<div markdown="1">
<style>
    :root { --section-number: 2; --section-style: upper-alpha; }
</style>

# Documentation Conventions {.annex}

## Exceptions Allowed {.annex}

Unless otherwise stated in the project-specific CONTRIBUTIONS.md file, each
project based on this specification **shall** develop documentation as defined
by this annex.

## Development Environment {.annex}

### Overview {.annex}

In addition to the development tools needed to manage and submit any
contribution within the Git environment (e.g., Git, GitHub), developing project
documentation requires the following tools:

- **A text editor,** which is used to create and edit markdown and yaml files,
- **Python,** which is required to run MkDocs,
- **MkDocs,** which is an open-source tool for translating a set of markdown
  files into a static website, and
- **Materials for MkDocs,** which is an open-source tool that extends the
  markdown language to support additional features that are useful for
  developing the look and feel of the project's documentation.

This combination of tools has been selected because it:

- is designed to be easy to install and use,
- requires minimal setup,
- works well with Git and GitHub,
- supports search functionality,
- can produce a static website,
- when coupled with add-ons, can produce PDFs
- has an active development community

It is recommended to establish this development environment prior to making any
edits. Generating the documentation website locally from a known baseline allows
the contributor to verify that the development environment is working correctly
prior to introducing edits to the files. Contributors are required to generate
the documentation locally to verify that their proposed changes do not introduce
any errors to the project. The MkDocs development environment allows users to
see their changes in real time so that any errors can be addressed quickly.

### Text Editor {.annex}

Any text editor can be used to produce markdown and yaml files. These files are
to have the extensions of ".md" and ".yml", respectively.

Contributors are encouraged to use [Visual Studio
Code](https://code.visualstudio.com), which is an open-source editor, with the
following extensions enabled as it provides a reasonably close rendering of the
final display format:

- Markdown Preview Enhanced by Yiyi Wang, this extension provides a markdown
  previewer with support for diagrams, math (LaTeX), mermaid, charts, and more;
- markdownlint by David Anson, this extension assists in ensuring markdown files
  follow consistent formatting rules; and
- YAML by Red Hat, this extension provides syntax highlighting, validation, and
  autocomplete for YAML files.

While any text editor can be used, this suite of tools offers a free solution
that is designed to render the markdown in real-time while assisting the user in
producing high quality code. However, users should be aware that the toolset
still does not attempt to render some of the more advanced features of Materials
for MkDocs. The final look and feel can be obtained using the MkDocs server.

### Python {.annex}

MkDocs requires Python 3.8 or higher. You can check to see if Python is already
installed and its version with the following command:

`python --version`

The most recent version of Python can be installed from [official Python
website](https://www.python.org/downloads/).

Once installed, you should verify by running both the `python --version` and
`pip --version` commands. PIP should be installed as a part of the Python
package.

### MkDocs {.annex}

Running the MkDocs server locally allows the contributor to see proposed changes
in real-time and test them thoroughly prior to submitting pull requests. To
install MkDocs, run

`pip install mkdocs`

Once installed, verify its installation with:

`mkdocs --version`

Once you have verified the installation, start the MkDocs server by changing to
the directory containing your cloned copy of the project repository and running

`mkdocs serve`

Once the server is running, you can direct a web browser to [localhost port
8000](http://127.0.0.1:8000) to see the development version of the website. This
site will be updated in realtime as you update files in the repository. If you
want to create a static site, However, to render all elements within the project
correctly, you will need to install Materials for MkDocs.

### Materials for MkDocs {.annex}

To install Materials for MkDocs and the commonly used extensions for ITS
projects, run the following command:

```bash
pip install mkdocs-material pymdown-extensions
```

## Working with the Content {.annex}

The content of ITS open-source documentation is generally written in
[Markdown](https://www.markdownguide.org/), a lightweight and easy-to-use markup
language that allows you to format text in a readable and visually appealing
way.

<!-- markdownlint-disable-next-line MD051 -->
Please read the "[Frequently Used Markdown](#frequently-used-markdown)" section
for details about how to use it in this project.

### Default Document Structure {.annex}

ITS open-source projects can cover a range of projects that have wildly
different documentation needs. Each project is allowed to define its own
structure, but unless otherwise specified **shall** use the structure defined in
this document, which is intended for projects that result in a product that can
be conceptualized as a single traditional document (e.g., a traditional
standard).

Each major portion of the document **shall** be defined in a separate markdown
file. Major portions are defined as:

- the title page, which shall be `index.md`;
- each top-level section of the front matter (e.g., Foreword, Introduction);
- each section in the body of the document; and
- each annex.

The document structure **shall** be reflected in the project's `mkdocs.yml` file
under the `nav` section with all front matter located under a `Front Matter`
heading.

```yml
    - Front Matter:
      - Title Page: index.md
      - Notices: notices.md
      - Acknowledgements: acknowledgements.md
      - Foreword: foreword.md
      - Introduction: introduction.md
    - 1 General: general.md
    - 2 Overview: overview.md
    - 3 Commenter Responsibilities: commenter-responsibilities.md
    - 4 Contributor Responsibilities: contributor-responsibilities.md
    - 5 Maintainer Responsibilities: maintainer-responsibilities.md
    - 6 WG Responsibilities: wg-responsibilities.md
    - A Code of Conduct: code-of-conduct.md
    - B Documentation Conventions: documentation-conventions.md
    - C Coding Conventions: code-quality.md
```

!!! note
    When using the default configuration for ITS projects, this results in
    a left-hand left-hand navigation bar that shows the major portions of the
    document while the right-hand navigation shows the content of the currently
    opened section.

!!! note
    Be sure to follow naming conventions. Notice that file names are not
    capitalized, and there are hyphens in place of spaces between words.

### Structure of the Title Page File {.annex}

The `index.md` file **shall** represent the title page of the document and **shall**:

- Start with a line containing a hashtag and nothing else
- Include code that suppresses unwanted markdownlint warnings
- Identify the status of the document
- Define the Document Identifier (e.g., NTCIP X8008)
- Define the Document Title (e.g., ITS Open-Source Process)
- Any other information required by the Standards Development Organization (SDO)

!!! example "Example of a Title Page File"
    ```markdown
    #
    <!-- markdownlint-disable MD033 -->
    <div style="text-align: center; font-style: italic; font-weight: bold;">
      A proposal to the NTCIP Joint Committee</div>
    <div style="text-align: center; font-size: 1.5em; font-weight: bold;">
      NTCIP X8008
    </div>
    ---
    <div style="text-align: center; font-size: 1.5em; font-weight: bold;">
      National Transportation Communications ITS Protocol
    </div>
    <div style="text-align: center; font-size: 2em; font-weight: bold;">
      ITS Open-Source Process
    </div>
    <!-- markdownlint-enable MD033 -->
    ```

### Structure of All Other Front Matter Files {.annex}

Each file representing a major portion of the front matter, other than the title
page, **shall** include a single level 1 heading that has the same title as
defined in the `nav` section of the `mkdocs.yml` file and is the first line of
the document

!!! example "Example of Start of a Front Matter File"
    ```markdown
    # Foreword
    ```

### Structure of a Section File {.annex}

Each file representing a section of the main body of the document **shall**:

- Start with code that sets the section counter for the body to the section
  number while suppressing unwanted markdownlint warnings
- Include a single level 1 heading that has the same title as defined in the
  `nav` section of the `mkdocs.yml` file and occurs immediately after the code
  defining the section number
- End each heading with `{.body}`

!!! example "Example of Start of a Section File"
    ``` html
    <!-- markdownlint-enable require-heading-annex -->
    <div markdown="1">
    <style>
        :root { --section-number: 2; --section-style: decimal; }
    </style>
    ```

!!! note
    Rule MD033 of markdownlint does issues a warning about the use of HTML
    within markdown, but it is is necessary in this case to allow automated
    numbering to work properly.

    Rule MD041 of markdownlint indicates that the first line in a file should be
    a top-level heading, but our convention requires defining the section number
    first.

### Structure of an Annex File {.annex}

Each file representing an annex of the document **shall**:

- Start with code that sets the section counter for the annex to the numerical
  order of the annex (the script will transform this into an alphabetic letter)
- Include a single level 1 heading that has the same title as defined in the
  `nav` section of the `mkdocs.yml` file and occurs immediately after the code
  defining the section number
- End each heading with `{.annex}`

!!! example "Example of Start of an Annex File"
    ```markdown
    <!-- markdownlint-enable require-heading-annex -->
    <div markdown="1">
    <style>
        :root { --section-number: 2; --section-style: upper-alpha; }
    </style>

    # Example Annex {.annex}
    ```

### Adding Definitions to the Glossary {.annex}

If you add definitions to the project's
[glossary](https://github.com/ite-org/NTCIP-8008/resources/glossary.md),
ensure the definitions are added **alphabetically**.

### Frequently Used Markdown {.annex}

#### Headings {.annex}

The hash (`#`) symbol at the start of a line denotes a heading (e.g., section,
clause, subclause). There are six levels of headings, and the number of hash
symbols indicates the heading level. The title of the heading should appear
after the hash symbols and a space.

!!! example
    ```markdown
    ### Heading 3

    #### Heading 4
    ```

#### Text Formatting {.annex}

- Make text bold by enclosing it with double asterisks (`**`).
- Make text italic by enclosing it with single underscores (`_`).
- Create inline code by wrapping text with backticks (`` ` ``).

!!! example
    ```markdown
    **This is a bold text.**

    _This is an italic text._

    This is an`inline code`.
    ```
    **This is a bold text.**

    _This is an italic text._

    This is an`inline code`.

#### Lists {.annex}

- Create ordered lists using numbers followed by a period (`1.`, `2.`, etc.).
- Create unordered lists using hyphens (`-`).
- The line before a list must be blank and a list cannot be immediately preceded by a different list
- The style for the list is defined by the first list item

!!! example
    ```markdown
    1.  Item 1
    2.  Item 2

    New List

    - Unordered Item 1
    - Unordered Item 2
    ```

    1.  Item 1
    2.  Item 2

    New List

    - Unordered Item 1
    - Unordered Item 2

!!! note
    The numbering of numbered lists is automatic within markdown (i.e.,
    when rendered, the list items are numbered sequentially from 1 regardless of
    what numbers are contained within the markdown file); however, it is good
    coding practice to maintain the correct numbering within the markdown file
    to prevent any confusion among contributors.

#### Links {.annex}

Create links using square brackets (`[]`) for the link text and parentheses
(`()`) for the URL.

!!! example
    ```markdown
    [NTCIP](https://ntcip.org)
    ```
    [NTCIP](https://ntcip.org)

#### Images {.annex}

Embed images using an exclamation mark (`!`), followed by square brackets (`[]`)
for the alt text, and parentheses (`()`) for the image URL. AN optional
attribute field can be added to the end to specify the size.

!!! example
    ```markdown
    ![NTCIP](_assets/images/NTCIP.jpg){ width=200px }
    ```
    ![NTCIP](_assets/images/NTCIP.jpg){ width=200px }

#### Block quotations {.annex}

Create a blockquote using the greater-than symbol (`>`) or through Materials for
MkDocs' admonition quote (`!!! quote`).

!!! example
    ```markdown
    > This is a blockquote.

    !!! quote
        This is a Materials for MkDocs admonition quote.
    ```
    > This is a blockquote.

    !!! quote
        This is a Materials for MkDocs admonition quote.

#### Code Blocks {.annex}

Create code blocks using triple backticks (` ``` `) for fenced code blocks and
specify a language next to the backticks before the fenced code block to
highlight the syntax.

=== "Example"
    ``` bash
    bash git pull
    ```

=== "Example code"
    ``` markdown
    ``` bash
    bash git pull
    ```
    ```

#### Admonitions {.annex}

Create callout out blocks for different purposes using the Materials for MkDocs
[admonitions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/?h=adm#supported-types)
feature by including three explanation points and the admonition type with the
contained text indented by four spaces (`!!! note`)

!!! example
    ```markdown
    !!! note
        This is a note.

    !!! tip
        This is a tip.
    ```
    !!! note
        This is a note.

    !!! tip
        This is a tip.

Materials for MkDocs supports the following standard admonitions:

- abstract
- bug
- danger
- example
- failure
- info
- note
- question
- quote
- success
- tip
- warning

### Markdown Tips {.annex}

- Preview your Markdown locally to ensure proper formatting before submitting
  your contribution.
- Keep your Markdown content organized, and use headings to structure your sections.
- There should be exactly one `heading 1` within each file.
- Use code blocks to highlight code snippets or configuration examples.
- See the official [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
  for more information about Markdown.
- See the
  [Materials for MkDocs Guide](https://squidfunk.github.io/mkdocs-material/) for
  more information about Materials for MkDocs.

</div>
