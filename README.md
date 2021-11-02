# coding-task

DynAmaze has developed a simplified design for their activities detail page and would like this page to be rebuilt.

Please implement the design from the mockup and the functional requirements.

Design can be found here:
https://www.figma.com/file/LX3Qw79il4ATD6NxVwJuCS/Design-System?node-id=3057%3A6327

Image Url:
https://firebasestorage.googleapis.com/v0/b/dynamaze---pwa-1550221436823.appspot.com/o/public%2Fimg%2Fdeals%2Ffunfussball1.png?alt=media&token=448599c6-ffb7-43f4-afc9-dfb82ce426f0

## Requirements
* Design implemented for IPhone 6/7/8
  * Header
  * Image
  * TimeSlot-Buttons
  * Available tickets text
  * amount increase/decrease buttons
  * price sum
  * "Jetzt Buchen" Button
* When clicking on a TimeSlot
    * Clicked TimeSlot gets selected (highlighted in green) and price, ticket count gets updated to match this TimeSlot.
    * The selected number of tickets remains the same, unless there are fewer tickets in the newly selected slot than in the previous one => in this case 1 ticket will be selected.
* When changing the number of tickets
    * the price changes according to the number of selected tickets
* When clicking on book now
    * Show JavaScript alert with message “Booking TimeSlot at HH:MM, x tickets at YY,YY € succeeded”.

## Not needed:
* Animations
* Desktop version
* Tests
* vuex
* vue-router

## Tips 

* Build Components
* Computed Properties might be helpful!

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
