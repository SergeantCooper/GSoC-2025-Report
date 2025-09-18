# Import Markdown files into LibreOffice Writer - GSoC 2025
- **Contributor**: Ujjawal Kumar Chouhan
- **Organization**: LibreOffice
- **Mentors**: Thorsten Behrens, Ilmari Lauhakangas

## Project Overview
This project implements Markdown import support in LibreOffice Writer, with a focus on compliance with the CommonMark specification. The imported Markdown content is accurately structured within Writer, preserving headings, lists, code blocks, and other formatting elements.

## Core Goals Completed
* Integrated the MD4C Markdown parser into LibreOffice’s build system.
* Created a filter for importing Markdown files.
* Implemented document conversion from Markdown to Writer’s Document Model.
* Added unit tests to validate correct document conversion.

## Stretch Goals Completed
* Added clipboard support for Markdown into Writer, allowing pasting of Markdown content directly from the clipboard into Writer.
* Enabled parsing of Markdown tables into Calc, allowing pasting of Markdown tables directly from the clipboard into Calc.

## Implementation Details
The core implementation involved integrating the MD4C library and mapping its parsed elements into LibreOffice Writer’s document model.

This consists of these core patches:
* [Patch 185170](https://gerrit.libreoffice.org/c/extern/+/185170) - Adds md4c library to the LibreOffice extern repository.
* [Patch 183850](https://gerrit.libreoffice.org/c/core/+/183850) - Integrates MD4C library into LibreOffice build system.
* [Patch 186484](https://gerrit.libreoffice.org/c/core/+/186484) - Adds reading of Markdown files into Writer using the new filter.
* [Patch 186485](https://gerrit.libreoffice.org/c/core/+/186485) - Implements the core document conversion.

## Demonstration

| Before                                                 | After                                                         |
| ------------------------------------------------------ | ------------------------------------------------------------- |
| ![](./before.png)                                      |  ![](./after.png)                                             |
| No Formatting Present in the document.                 | Document is correctly formatted.                              |
| Plain text without structure.                          | Well-structured document with proper formatting applied.      |
| Limited usability of Markdown content in LibreOffice.  | Seamless integration of Markdown into LibreOffice workflow.   |

## Contributions Overview
### Core Patches
* [Patch 185170](https://gerrit.libreoffice.org/c/extern/+/185170)
* [Patch 183850](https://gerrit.libreoffice.org/c/core/+/183850)
* [Patch 186484](https://gerrit.libreoffice.org/c/core/+/186484)
* [Patch 186485](https://gerrit.libreoffice.org/c/core/+/186485)

### Unit tests
* [Patch 187449](https://gerrit.libreoffice.org/c/core/+/187449) - Introduces unit tests verifying Markdown lists and headings.
* [Patch 188082](https://gerrit.libreoffice.org/c/core/+/188082) - Adds unit test for tables.

### Bug fixes and Others
* [Patch 187622](https://gerrit.libreoffice.org/c/core/+/187622) - Fixes uninitialized member variable in SwMarkdownParser.
* [Patch 187659](https://gerrit.libreoffice.org/c/core/+/187659) - Registers Markdown filter in registry
* [Patch 187658](https://gerrit.libreoffice.org/c/core/+/187658) - Fixes formatting inconsistency.
* [Patch 187792](https://gerrit.libreoffice.org/c/core/+/187792) - Introduces clipboard support for Markdown format.
* [Patch 188067](https://gerrit.libreoffice.org/c/core/+/188067) - Introduces a new dialog for pasting plain text as Markdown.
* [Patch 188528](https://gerrit.libreoffice.org/c/core/+/188528) - Enables pasting of Markdown tables directly from the clipboard into Calc.
* [Patch 190084](https://gerrit.libreoffice.org/c/core/+/190084) - Adds missing inline code span.
* [Patch 190286](https://gerrit.libreoffice.org/c/core/+/190286) - Fixes progress bar.
* [Patch 190976](https://gerrit.libreoffice.org/c/core/+/190976) - Adds missing task lists symbols.
* [Patch 190953](https://gerrit.libreoffice.org/c/core/+/190953) - Refactor: Improve Image Handling.
* [Patch 191102](https://gerrit.libreoffice.org/c/core/+/191102) - Unique name for images and better image representation.

## Future Work
* **Optimize Performance**: Enhance the importer to improve efficiency and reduce loading times for large Markdown files.
* **Error Reduction & Completeness**: Resolve any remaining conversion errors, while ensuring that all Markdown elements are fully and accurately mapped into Writer.
* **Extend Support to Impress**: Continue work on importing Markdown files into LibreOffice Impress ([Work In Progress Patch](https://gerrit.libreoffice.org/c/core/+/189448)).

## Learning & Experience

This project was a valuable learning experience, giving me deeper insight into LibreOffice’s architecture and the challenges of integrating new features into a large codebase. I learned how the filter system interacts with different LibreOffice modules such as sw, sd, and sc, and how to map Markdown elements into Writer effectively.

I also improved my skills in C++, build systems, and unit testing, while gaining experience with code reviews and collaborative development. Working with my mentors and the community taught me the importance of clear communication, iterative development, and maintaining quality through testing.

Overall, this project strengthened my technical abilities and gave me confidence in contributing to large open-source projects like LibreOffice.

