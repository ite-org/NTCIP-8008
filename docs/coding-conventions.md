<!-- markdownlint-enable require-heading-annex -->
<div markdown="1">
<style>
    :root { --section-number: 3; --section-style: upper-alpha; }
</style>

# Coding Conventions {.annex}

## Python Coding Conventions {.annex}

Each contributor **shall** adhere to style guidelines defined in
[Python Enhancement Proposals (PEP) 8 – Style Guide for Python Code](https://peps.python.org/pep-0008/).

!!! note "Highlights of PEP 8"
    - Imports should be at the top of the file
    - Imports should be grouped into three sections with a blank line between
    each: (1) standard library imports, (2) thirdd party library imports, and
    (3) local imports
    - Function and variable names should be in lowercase_with_underscores
    - Class names should be in UpperCamelCase
    - Constants should be in ALL_CAPS_WITH_UNDERSCORES
    - Do not use tabs; use four spaces for each indentation level
    - Limit lines to 79 characters; or 72 characters for long comments
    - Separate top-level functions and class definitions with two blank lines
    - Inside functions, use one blank line to separate significant logical
    sections

Each contributor **should** use a linter to automatically enforce the PEP 8
rules.

!!! example
    Pylince

</div>
