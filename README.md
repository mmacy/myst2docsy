# myst2docsy

This project is a Python-based tool designed to convert Sphinx projects written in MyST-markdown to a Hugo/Docsy-compatible format. The conversion process includes reformatting content, updating directives, handling assets, and ensuring proper site structure through Hugo front matter and directory organization. The tool incorporates error handling, configurable options, and a robust testing strategy.

## Phases and task grouping

### 1. Pre-conversion setup

- **Directory structure and input files:**
  - Documentation is organized in a standardized directory structure (e.g., a `docs/` folder with subdirectories such as `concept`, `howto`, and `reference`).
  - Identify and load all input MyST-markdown files.
- **Configuration options:**
  - Load settings from a YAML or JSON configuration file to customize front matter fields (e.g., `title`, `description`) and other conversion parameters.

### 2. Content and structural conversion

- **Remove all toctree directives:**
  - Strip any `toctree` blocks since Hugo/Docsy derives navigation from the file structure and front matter.
- **Convert admonitions:**
  - Parse and convert colon- or backtick-fenced admonitions into Hugo-compatible formats (e.g., using Docsy shortcodes).
- **Update python role references and cross-references:**
  - Replace MyST inline role syntax (e.g., `{py:class}\`mypackage.MyClass\``) with Hugo internal linking or shortcode conventions for python objects.
  - Update all other cross-references (internal links, footnotes, reference-style links) to reflect changes due to file reorganization.
- **Adjust asset paths:**
  - Modify image and static asset paths to align with Hugo’s folder structure (typically relocating them to the `/static` directory).
- **Standardize code blocks:**
  - Convert any MyST-specific code directives into standard Markdown fenced code blocks with appropriate language annotations.

### 3. Post-conversion enhancements

- **Insert Hugo front matter:**
  - Prepend each Markdown file with YAML or TOML front matter required by Hugo (including metadata such as title, description, and slug).
- **Create _index.md files for sections:**
  - Generate an `_index.md` file for each section directory (e.g., `concept`, `howto`, `reference`) to serve as the landing page.
- **Add metadata to _index.md files:**
  - Embed YAML/TOML front matter in each `_index.md` file, specifying metadata such as `title`, `description`, `weight`, and `menu` configuration for navigation control.
- **Provide section overviews:**
  - Include introductory content in each `_index.md` file to outline the purpose and context of the section.
- **Maintain directory structure:**
  - Preserve the standardized directory layout to ensure Hugo correctly recognizes each section based on the presence of `_index.md` files.

### 4. Validation and quality assurance

- **Error handling and logging:**
  - Define a clear error reporting mechanism to handle cases where conversion rules might fail or be ambiguous; log warnings or errors to assist with troubleshooting.
- **Dry run mode:**
  - Implement an option to perform a dry run that reports intended changes without writing files, enabling verification of conversion logic before applying changes.
- **Integration with markdown linters:**
  - Optionally integrate a markdown linter post-conversion to catch any formatting issues introduced during the conversion process.

### 5. Testing and configuration

- **Testing strategy:**
  - Develop and implement a testing strategy using a variety of sample files covering edge cases; automated tests (using pytest) will verify that every conversion rule functions as expected.
- **Configuration options for front matter specification:**
  - Provide configuration options (via a YAML or JSON configuration file) to customize front matter fields such as `title`, `description`, and other metadata without requiring code modifications.
