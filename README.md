# Import Markdown files into LibreOffice Writer - GSoC 2025
- **Contributor**: Ujjawal Kumar Chouhan
- **Organization**: LibreOffice
- **Mentors**: Thorsten Behrens, Ilmari Lauhakangas

## Project Overview
This project implements Markdown support in LibreOffice Writer, ensuring compliance with the CommonMark specification. Imported Markdown content is structured appropriately within Writer, preserving headings, lists, code blocks, and other formatting elements.

## Core Goals Completed
* Integrated MD4C markdown parser into LibreOffice's Build System.
* Created an import filter for markdown files.
* Implemented the core document conversion from markdown to Writer's Document Model.
* Added Unit Tests for correct document conversion.

## Stretch Goals Completed
* Introduced clipboard support for Markdown files in Writer.
* Parsed Markdown tables into Calc to allow pasting of markdown tables directly into Calc.

## Implementation Details
The core implementation consists of integration of the MD4C library and using it, to convert markdown elements into Writer elements.

This consists of these core patches:
* [Patch 185170](https://gerrit.libreoffice.org/c/extern/+/185170) - Adds md4c library to the LibreOffice extern repository.
* [Patch 183850](https://gerrit.libreoffice.org/c/core/+/183850) - Integrates MD4C library into LibreOffice Build System.
* [Patch 186484](https://gerrit.libreoffice.org/c/core/+/186484) - Adds reading of Markdown files into Writer using the new filter.
* [Pacth 186485](https://gerrit.libreoffice.org/c/core/+/186485) - Implements the core document conversion.

