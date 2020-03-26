# Picme Code Challange
Welcome to the Picme Code Challange. This document explain what is given and
what is expected in this challange.

In this challange you are given a very simple web server that provides a
restaurant menu data and you are expected to write the React application that
displays the restaurant menu for the provided data.

The web server code is implemented in express.js, you need node and npm to start
running the web server code.

Once you have the requirement, clone the repo, and run
```
npm install
```
within the repository.

## Web Server

There is only single endpoint in the web server, which just tries to render
`index.jade`. Express uses jade for templating engine by default so we are keeping
it. It should be [quite straightforward](https://naltatis.github.io/jade-syntax-docs/) to work with jade templates.

The default libraries have already added in the `layout.jade` for convenience. By default we include:
- bootstrap
- react
- jquery

You can also include any 3rd party library you want to use in the `layout.jade`

### Restaurant Data Format
`window.data.restaurant` contains the Restaurant json which you will use to implement restaurant menu.

A Restaurant data looks like:
```
"id": "1",
"name": "Restoran",
"active_menu": {
  ...
}
```
Restaurant contains `active_menu` which is where the menu data contained
```
"id": "1",
"menu_name": "Kahvaltı Menüsü",
"menu": {
  "id": "1",
  "sections": [
    "Kaseler",
    "Pancakes",
    ... // menu section names
  ],
  "item_order": [
    {
      "section": "Kaseler",
      "items": [
        "item-1",
        "item-2"
      ]
    },
    {
      "section": "Pancakes",
      "items": [
        "item-3",
        "item-4"
      ]
    },
    ... // Items are ordered in the sections items array here points to item ids in the menu listed below
  ],
  "items": [
    {
      "id": "item-1",
      "section": "Kaseler",
      "promotion": "33.00", // An item can have a promotion which is it's final price
      "item": {
        "name": "Granola Bowl",
        "price": "39.00", // Item's base price
        "dietary_info": [
          "GLUTEN_FREE"
        ], // Dietary info can be either GLUTEN_FREE or SPICY
        "ingredients": [
          "Çilek",
          "Granola",
          "Yogurt",
          "Yaban mersini"
        ],
        "images": [
          {
            "400": "....jpg",
            "200": "....jpg",
            "100": "....jpg"
          } // images contains the links of the menu item images in different sizes for responsive design
        ]
      }
    },
    ///
  ]
}
```

### Your Task

Your task is complete the frontend app that renders the Restaurant menu, and defines some actions that users
can do. 