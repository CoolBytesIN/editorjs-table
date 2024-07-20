# Table block tool for Editor.js

This is a clone of this [Editor.js block tool](https://editorjs.io). It fixes the default `withHeadings` issue.

## Preview

![table](assets/68747470733a2f2f636170656c6c612e706963732f34313239346365632d613262332d343135372d383339392d6666656665643364386666642e6a7067.jpeg)

## Installation

**Using `npm`**

```sh
npm install @coolbytes/editorjs-table
```

**Using `yarn`**

```sh
yarn add @coolbytes/editorjs-table
```

## Usage

Include it in the `tools` property of Editor.js config:

```js
const editor = new EditorJS({
  tools: {
    table: Table
  }
});
```

Or init the Table tool with additional settings

```javascript
const editor = new EditorJS({
  tools: {
    table: {
      class: Table,
      inlineToolbar: true,
      config: {
        rows: 2,
        cols: 3,
      },
    },
  },
});
```

## Config Params

| Field              | Type     | Description          |
| ------------------ | -------- | ---------------------------------------- |
| `rows`             | `number` | initial number of rows. `2`  by default |
| `cols`             | `number` | initial number of columns. `2` by default |
| `withHeadings`             | `boolean` | toggle table headings. `false` by default |

## Output data

This Tool returns `data` in the following format

| Field          | Type         | Description           |
| -------------- | ------------ | ----------------------------------------- |
| `withHeadings` | `boolean`    | Uses the first line as headings |
| `content`      | `string[][]` | two-dimensional array with table contents |

&nbsp;

Example:

```json
{
  "time": 1721500689337,
  "blocks": [
    {
      "id": "XXVTfnMlcE",
      "type": "table",
      "data": {
        "withHeadings": true,
        "content": [
          [ "Kine", "Pigs", "Chicken" ],
          [ "1 pcs", "3 pcs", "12 pcs" ],
          [ "100$", "200$", "150$" ]
        ]
      }
    }
  ],
  "version": "2.30.2"
}
```