# Import Markdown files into LibreOffice Writer - GSoC 2025
- **Contributor**: Ujjawal Kumar Chouhan
- **Organization**: LibreOffice
- **Mentors**: Thorsten Behrens, Ilmari Lauhakangas

## Project Overview
This project implements Markdown import support in LibreOffice Writer, with a focus on compliance with the CommonMark specification. The imported Markdown content is accurately structured within Writer, preserving headings, lists, code blocks, and other formatting elements.

## Core Goals Completed
* Integrated the MD4C Markdown parser into LibreOffice’s build system
* Created a filter for importing Markdown files
* Implemented document conversion from Markdown to Writer’s Document Model
* Added unit tests to validate correct document conversion

## Stretch Goals Completed
* Added clipboard support for Markdown into Writer, enabling users to paste Markdown content directly from the clipboard into Writer
* Enabled parsing of Markdown tables into Calc, allowing pasting of Markdown tables directly from the clipboard into Calc

## Implementation Details
The core implementation involved integrating the MD4C library and mapping its parsed elements into LibreOffice Writer’s document model.

This consists of these core patches:
* [Patch 185170](https://gerrit.libreoffice.org/c/extern/+/185170) - Adds md4c library to the LibreOffice extern repository.
* [Patch 183850](https://gerrit.libreoffice.org/c/core/+/183850) - Integrates MD4C library into LibreOffice Build System.
* [Patch 186484](https://gerrit.libreoffice.org/c/core/+/186484) - Adds reading of Markdown files into Writer using the new filter.
* [Pacth 186485](https://gerrit.libreoffice.org/c/core/+/186485) - Implements the core document conversion.

## Demonstration
| Before        | After           |
| ------------- |:-------------:|
|       |  |
| col 2 is      | centered      |
