# Development TODO

## Phase 1: Pre-conversion setup

- [ ] Implement file loader to:
  - [ ] Identify and load all input MyST-markdown files.
  - [ ] Load Sphinx's `conf.py` file for the project to obtain project/product name.
- [ ] Design configuration parser to load settings from a YAML file, including customizable front matter fields (e.g., `title`, `description`).

## Phase 2: Content and structural conversion

- [ ] Remove all `toctree` directives from source files.
- [ ] Parse and convert admonitions:
  - [ ] Detect colon- or backtick-fenced admonitions.
  - [ ] Convert them to Hugo/Docsy-compatible shortcodes.
- [ ] Update Python role references and cross-references:
  - [ ] Replace MyST inline role syntax (e.g., `{py:class}\`mypackage.MyClass\``) with Hugo internal linking or shortcodes.
  - [ ] Update all other cross-references (internal links, footnotes, reference-style links) to reflect file reorganization.
- [ ] Adjust asset paths:
  - [ ] Option 1: Modify image and static asset paths to align with Hugo’s `/static` directory
  - [ ] Option 2: Convert non-index pages to Hugo leaf bundles (directory containing an `index.md` file along with its related resources like images).

## Phase 3: Post-conversion enhancements

- [ ] Insert Hugo front matter:
  - [ ] Prepend each Markdown file with YAML front matter (include metadata fields `title`, `description`, `category`, and `tags`).
- [ ] Generate `_index.md` files for each section:
  - [ ] Create an `_index.md` file in each section directory (e.g., `concept/`, `howto/`, `reference/`).
  - [ ] Embed YAML front matter in each `_index.md` (include fields `title`, `description`, and `weight`).
- [ ] Ensure the standardized directory layout is maintained for proper Hugo site recognition.

## Phase 4: Validation and quality assurance

- [ ] Implement error handling and logging:
  - [ ] Define clear error reporting for failed or ambiguous conversion rules.
  - [ ] Log warnings/errors to assist in troubleshooting.
- [ ] Add a dry run mode:
  - [ ] Report intended changes without writing files, for conversion verification.

## Phase 5: Testing and configuration

- [ ] Develop a testing strategy using diverse sample files:
  - [ ] Cover edge cases and verify each conversion rule.
  - [ ] Implement automated tests using pytest.
- [ ] Enhance configuration options:
  - [ ] Allow customization of front matter (e.g., `title`, `description`) via YAML configuration without code modifications.
