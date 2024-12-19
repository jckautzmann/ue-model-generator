# Models Generator for the AEM Universal Editor

Generates AEM Universal Editor models from a markdown file containing Edge Delivery Service blocks.

## Usage

Run the following command to generate the `model.json` file below the project root directory from a markdown file containing Edge Delivery Service blocks:
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
- Supports the following block types: container, key-value, and simple blocks
- Supports multiple blocks in the markdown file
- Container block: generates parent and item models
- Supports group fields
- Supports block classes
- Supports empty cells by generating a rich text field

## Example

Input: markdown file:
```markdown
+-------------------------------------------------------+
| Actors                                                |
+===============+=============+=========================+
| Harrison      | Ford        | USA                     |
+---------------+-------------+-------------------------+
| Rachel        | MacAdams    | Canada                  |
+---------------+-------------+-------------------------+
| Alain         | Delon       | France                  |
+---------------+-------------+-------------------------+
```

Output: generated `model.json` file:
```json
{
  "filters": [
    {
      "id": "actors",
      "components": [
        "actors-item"
      ]
    }
  ],
  "definition": {
    "groups": [
      {
        "title": "Blocks",
        "id": "blocks",
        "components": [
          {
            "title": "actors",
            "id": "actors",
            "plugins": {
              "xwalk": {
                "page": {
                  "resourceType": "core/franklin/components/block/v1/block",
                  "template": {
                    "name": "actors",
                    "model": "actors"
                  }
                }
              }
            }
          },
          {
            "title": "actors-item",
            "id": "actors-item",
            "plugins": {
              "xwalk": {
                "page": {
                  "resourceType": "core/franklin/components/block/v1/block/item",
                  "template": {
                    "name": "actors-item",
                    "model": "actors-item"
                  }
                }
              }
            }
          }
        ]
      }
    ]
  },
  "models": [
    {
      "id": "actors-item",
      "fields": [
        {
          "component": "richtext",
          "name": "text0",
          "value": "",
          "label": "Text",
          "valueType": "string"
        },
        {
          "component": "richtext",
          "name": "text1",
          "value": "",
          "label": "Text",
          "valueType": "string"
        },
        {
          "component": "richtext",
          "name": "text2",
          "value": "",
          "label": "Text",
          "valueType": "string"
        }
      ]
    }
  ]
}
```
