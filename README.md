# Universal Editor Models Generator

Generates AEM Universal Editor models from a markdown file containing Edge Delivery Service blocks.

## Usage

To generate the `model.json` file below the project root from a markdown file containing the blocks, run the following command:
```
npm run md2model --file path/to/file.md
```
Example:
```
npm run md2model --file test/md2model/fixtures/container.md
```
For a list of existing markdown files and their generated models, see the [fixtures](https://github.com/jckautzmann/ue-model-generator/tree/gw-2024/test/md2model/fixtures) directory.

## Features

- Generates the `model.json` file with definition, filters, and models
- Supports the following blocks: container, key-value, and all blocks
- Supports multiple blocks in the markdown file
- Container block: generates parent and item models
- Supports group fields
- Supports block classes
- Supports empty cells by generating a rich text field
