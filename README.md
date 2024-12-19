# Universal Editor models generator

Generates AEM Universal Editor models from a markdown file containing Edge Delivery Service blocks.

## Usage

To generate the `model.json` file from a markdown file containing the blocks, run the following command:
```
npm run md2model --file test/md2model/fixtures/container.md
```

## Features

- Supports multiple blocks in the markdown file
- Generates the `model.json` file with definition, filters, and models
- Supports the following blocks: container, key-value, and all blocks
- Container block: generates parent and item models
- Supports group fields
- Supports block classes
- Supports empty cells by generating a rich text field
