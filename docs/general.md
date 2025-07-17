<!-- markdownlint-enable require-heading-body -->
<div markdown="1">
<style>
    :root { --section-number: 1; --section-style: decimal; }
</style>

# General {.body}

## Scope {.body}

This document specifies the process used to produce open-source documents within
the field of Intelligent Transportation Systems (ITS).

The process follows general practices within the larger open-source community;
however, this document:

a. provides a step-by-step overview of the process, so that those unfamiliar with
open-source processes can better understand the process and become contributors,

a. formalizes the process (e.g., by clearly defining what are requirements), and

c. tailors the process (e.g., by defining the preferred tools to be used).

The process to approve the resultant product is defined elsewhere (e.g., NTCIP 8001).

The ITS Open-Source Process is based on the practices defined by
[open-sauced](https://github.com/open-sauced/intro/tree/main). However, whereas
open-sauced is written as an informative guide and describes how systems can
work; this document is written as a specification to define how the ITS
Open-Source Process will work. While still providing a discussion of the
issues; it highlights the requirements and notable options along the way by
stating each in its own paragraph and boldfacing the keywords "shall" and "may"
to clearly designate requirements and options. The
remaining text provides further guidance and can include additional options
that do not necessitate specific numbering.

We recognize that onboarding to a new project can be challenging, especially if
you're new to open source development. Be patient, and don't be discouraged by
setbacks or mistakes. You'll become more comfortable and confident in your
contributions with persistence and practice.

## References {.body}

The following documents are referenced by this document. At the time of
publication, the editions indicated were valid.

### Normative References {.body}

Normative references contain provisions that, through reference in this text,
constitute provisions of this document. All standards are subject to revision,
and parties to agreements based on this standard are encouraged to investigate
the possibility of applying the most recent editions of the standard listed.

- [ISO/IEC/IEEE 24765:2017](https://standards.iso.org/ittf/PubliclyAvailableStandards/c071952_ISO_IEC_IEEE_24765_2017.zip):
_Systems and software engineering — Vocabulary, 2017_
- [GitHub](https://github.com/dashboard)
- [MkDocs](https://www.mkdocs.org)
- [Materials for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- [Python](https://www.python.org/downloads/) (for test procedure projects)

### Other References {.body}

Other references are included to provide a more complete understanding of this
document and its relationship to other documents.

#### Other Resources for Contributors {.body}

This document standardizes and tailors certain aspects of the information
contained in open-sauced; however, it is not a complete replacement of that
material. If you wish to learn more about open-source development, the following
materials may be of interest:

- [What is open-source?](https://opensauced.pizza/learn/intro-to-oss/what-is-open-source)
- [Why open-source?](https://opensauced.pizza/learn/intro-to-oss/why-open-source)
- [The Secret Sauce](https://opensauced.pizza/learn/intro-to-oss/the-secret-sauce)
- [Types of Open-Source Contributions](https://opensauced.pizza/learn/intro-to-oss/types-of-contributions)
- [Open Source Guides](https://opensource.guide)
- [Introduction to GitHub and Open Source Projects](https://www.digitalocean.com/community/tutorial_series/an-introduction-to-open-source)

#### Other Resources for Maintainers {.body}

If you wish to learn more about open-source maintenance, the following materials
may be of interest:

- [Understanding the Role of an Open Source Maintainer](https://opensauced.pizza/learn/becoming-a-maintainer/intro)
- [How to Communicate and Collaborate Effectively](https://opensauced.pizza/learn/becoming-a-maintainer/communication-and-collaboration)
- [Building Community](https://opensauced.pizza/learn/becoming-a-maintainer/building-community)
- [Maintainer Power Ups](https://opensauced.pizza/learn/becoming-a-maintainer/maintainer-powerups)
- [Building Your Team](https://opensauced.pizza/learn/becoming-a-maintainer/your-team)
- [The Power of Open Source Metrics](https://opensauced.pizza/learn/becoming-a-maintainer/metrics-and-analytics)
- [Contributor Ladder Template](https://github.com/cncf/project-template/blob/main/CONTRIBUTOR_LADDER.md)
- [Maintainer Community](https://maintainers.github.com/auth/signin)

## General Statements {.body}

The remainder of this document is broken into the following chapters:

- **Overview:** Provides an overview of the entire process
- **Commenter Responsibilities:** Details the responsibilities of those reviewing open-source materials and provides step-by-step processes for using the preferred tools.
- **Contribution Responsibilities:** Details the responsibilities of those contributing to open-source materials and provides step-by-step processes for using the preferred tools.
- **Maintainer Responsibilities:** Details the responsibilities of those assigned to maintain an ITS open-source project. This includes processes for setting up new projects, managing issues and pull requests, maintaining quality, and coordinating with standard development organizations.
- **WG Responsibilities:** Defines the responsibilities of the working group assigned to manage an ITS open-source project.
- **Code of Conduct:** Defines the default code of conduct for ITS open-source processes. These can be refined for any particular project, if needed, but most projects should be able to use this text without modification.
- **Documentation Conventions:** Defines the preferred styles, processes, and tools for developing documentation for ITS open-source projects, including projects that are 100% documentation (e.g., the ITS Open-Source Process project).
- **Code Conventions:** Defines the styles, processes, and tools for developing computer code for ITS open-source projects, including Python and ASN.1.

!!! note
    It is expected that a future edition will define the responsibilities of the committee that establishes ITS open-source projects.

!!! note
    It is expected that a future edition will define preferred ways to use requirement management tools to produce content that can be easily integrated into the ITS open-source pojects while providing clear traceability.

!!! note
    It is expected that a future edition will move information about the approval of releases to NTCIP 8001.

## Glossary {.body}

For terms not defined here, English words are used in accordance with their
definitions by the [merriam-webster online dictionary](https://www.merriam-webster.com).
Electrical and electronic terms not defined in this section or in Webster's New
Collegiate Dictionary are used in accordance with their definitions in
ISO/IEC/IEEE 24765:2017.

backlog

:   A backlog is a list of tasks that need to be completed within a project. Typically, these are tasks that are not yet assigned to a developer and are waiting to be worked on. Sometimes, these could be tasks that were open weeks or months ago and are still waiting to be worked on.

branch
:   A branch is a separate version of the code that's created for development purposes. Branches allow contributors to experiment with changes without affecting the main codebase. When changes are ready to be merged into the main codebase, they're typically submitted as a pull request.

bug
:   A bug refers to an error, flaw, or defect in code that adversely affects the
    proper functioning of the software. Open source projects often depend on
    contributions from the community to identify and rectify these bugs.

**clone**: Cloning is the process used to copy an existing Git repository into
a new local directory. The `git clone` command will create a new local directory
for the repository, copy all the contents of the specified repository, create
the remote tracked branches, and checkout an initial branch locally. By default,
Git clone will create a reference to the remote repository called origin.

**code freeze**: A code freeze is a period of time where no new code is added
to a project. It is often used to prepare for a release and ensure that the
code is stable and ready for production.

**code review**: A code review is when a maintainer or contributor will review
the work of another contributor. This is a great way to ensure that the code is
high quality and meets the standards of the project.

**containerization**: Containerization is a way of packaging and running
applications. Instead of installing an app directly on your computer, you put
it in a container that includes everything it needs to work. This container can
then run on your computer alongside other containers. It's a way to organize
and run multiple applications on the same machine, making it easier for
developers to manage and scale their applications.

**continuous integration (CI)**: Continuous integration (CI) is a development
approach in which developers regularly merge code into a shared repository. For
each change, an automated build and test process is run to detect errors as
quickly as possible.

**continuous deployment (CD)**: Continuous deployment (CD) is often associated
with continuous integration (CI) and refers to keeping your application
deployable at any point or even automatically releasing to production. CD means
that every change which passes the automated tests is deployed to production
automatically.

**contributor**: A contributor is anyone who makes changes, additions, or
suggestions to an open source project. Contributors can be developers,
designers, writers, testers, or anyone else who helps to make the project better.

**core member**: A core member is a contributor who has been granted additional
privileges or responsibilities within an open source project. Core members are
typically trusted contributors who have demonstrated a deep understanding of
the project and have made significant contributions to its development.

**docs**: Docs is an abbreviation for "documentation". It primarily explains
how to implement and use a product or an open source project. It also provides
information on how to contribute to the project and expectations for
contributors. Documentation is often written using [Markdown](https://www.markdownguide.org/),
a lightweight markup language.

**fork**: A fork is a copy of a repository. When you fork a repository, you
create a new copy of the codebase that you can modify and experiment with
without affecting the original codebase.

**GitHub actions**: GitHub Actions are a way to automate tasks within your
software development life cycle. GitHub Actions are event-driven, meaning that
you can run a series of commands after a specified event has occurred. Examples
of GitHub Actions include running tests, deploying to production, and sending
notifications.

**GitHub discussions**: GitHub Discussions are a way to have conversations
about your project directly in GitHub. They are a great way to discuss ideas,
ask questions, and share knowledge with your community.

**issue**: An issue is a problem or bug that needs to be addressed in the code.
Issues can be created by anyone, and they're often used to keep track of bugs,
feature requests, and other tasks that need to be done.

**linting**: Linting is the process of running a program that will analyze code
for potential errors. A popular linting tool used frequently is ESLint. You can
setup an action to run ESlint against each pull request that comes in to check
for potential errors before it makes it into production.

**maintainer**: A maintainer is a person or a group of people responsible for
maintaining a specific open source project. Maintainers are typically
responsible for reviewing and accepting or rejecting contributions from other
contributors. They also have the authority to make final decisions about the
direction and scope of the project.

**markdown**: Markdown is a lightweight markup language commonly used for
creating formatted text documents. It is widely used for creating documentation
and README files in software development due to its simplicity and readability.

**merge**: Merging is the process of combining changes from one branch into
another. When a pull request is accepted and merged, the changes made in the
pull request become part of the main codebase.

**onboarding**: Onboarding documentation helps new team members or collaborators
quickly become familiar with a project's structure, goals, and processes.

**OSS Projects**: OSS stands for "Open Source Software" projects. These are
software projects where the source code is made available to the public,
allowing anyone to view, use and modify the software.

**pull request**: A pull request is a request from a contributor to a maintainer
for changes made to the code to be pulled into a codebase.

**quality assurance**: Quality assurance in open source projects involves
testing, reviewing, and ensuring the software meets the desired standards.
Community members often contribute to testing and reporting issues to improve
the software's quality.

**release candidate**: A release candidate is a beta version of software with
the potential to be a final product. It is typically the last version before
the final release.

**release notes**: Release notes are documents that detail changes, enhancements,
bug fixes, and new features in each software release. They inform users and
stakeholders about what to expect in a new version of the software.

**repository**: A repository is a central location where code is stored and
managed. In open source, repositories are often hosted on platforms like GitHub,
GitLab, or Bitbucket. Each repository can contain one or more projects, and
contributors can submit changes to the code by making pull requests.

**style guide**: A style guide is a set of rules and conventions that define the
preferred formatting, writing style, and visual elements used in documentation
and other content. This helps maintain consistency and clarity across documents,
making them easier to read and understand.

**versioning**: Versioning is the process of assigning either unique version
names or numbers to new releases of your project. Some versions are released as
"major" versions, while others are released as "minor" versions.

</div>
