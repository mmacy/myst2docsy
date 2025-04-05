# Sphinx-to-Hugo conversion tool

A conceptual Python-based tool designed to convert Sphinx projects written in MyST-markdown into a Hugo/Docsy-compatible format. This project aims to streamline the migration of documentation by transforming directives, asset paths, and site organization while ensuring high fidelity to the original content.

The `myst2docsy` tool is intended to:

- Automate the removal and conversion of Sphinx- and MyST-specific elements.
- Transform admonitions, role references, and cross-references into Hugo-compatible formats.
- Provide configurable options for customizing front matter metadata.
- Incorporate quality assurance features like error handling, logging, and a dry run mode.

## Objectives

- **High fidelity conversion:** Maintain the structural and stylistic integrity of the original documentation.
- **Configurability:** Enable users to adjust conversion parameters, especially for front matter specifications, without altering the code.
- **Robust validation:** Implement error reporting and logging mechanisms to assist in troubleshooting during conversion.
- **Extensibility:** Lay a strong foundation for future enhancements and additional features based on user feedback.
