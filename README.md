# ColorPickerComponent

The `ColorPickerComponent` is an Angular component designed to display a customizable color picker. Users can specify the colors, the size of each color square, the maximum number of colors, and the number of columns in which the colors should be arranged. This component implements `ControlValueAccessor`, making it compatible with Angular forms.

## Installation

To use the `ColorPickerComponent` in your project, install it via npm:

```bash
npm install your-package-name

## Usage


First, import the `ColorPickerComponent` into your Angular module:

typescript

Копировать код

`import { NgModule } from '@angular/core'; import { BrowserModule } from '@angular/platform-browser'; import { ReactiveFormsModule } from '@angular/forms'; import { ColorPickerModule } from 'color-picker';  @NgModule({   declarations: [     AppComponent   ],   imports: [     BrowserModule,     ReactiveFormsModule,     ColorPickerModule   ],   providers: [],   bootstrap: [AppComponent] }) export class AppModule { }`

Then, you can use the `ColorPickerComponent` in your templates:

html

Копировать код

`<lib-color-picker   [colors]="colorArray"   [squareSize]="30"   [maxColors]="50"   [numColumns]="5"   (colorChange)="onColorChange($event)"> </lib-color-picker>`

Inputs
------

*   `colors` (string\[\]): An array of color strings to be displayed in the color picker.
*   `squareSize` (number): The size of each color square in pixels. Default is 20.
*   `maxColors` (number): The maximum number of colors that can be displayed. Default is 100.
*   `numColumns` (number): The number of columns to arrange the colors into. Default is 10.

Outputs
-------

*   `colorChange` (EventEmitter<string>): Emits the selected color when a color is chosen.

Example
-------

Here's a complete example of how to use the `ColorPickerComponent` in an Angular application:

### TypeScript (Component)

typescript

Копировать код

`import { Component } from '@angular/core';  @Component({   selector: 'app-root',   templateUrl: './app.component.html',   styleUrls: ['./app.component.css'] }) export class AppComponent {   colorArray: string[] = ['#FF0000', '#00FF00', '#0000FF', '#FFFF00', '#FF00FF', '#00FFFF'];   selectedColor: string;    onColorChange(color: string) {     this.selectedColor = color;   } }`

### HTML (Template)

html

Копировать код

`<div>   <h1>Color Picker Example</h1>   <lib-color-picker     [colors]="colorArray"     [squareSize]="30"     [maxColors]="50"     [numColumns]="5"     (colorChange)="onColorChange($event)">   </lib-color-picker>   <p>Selected Color: {{ selectedColor }}</p> </div>`

Styling
-------

You can customize the appearance of the `ColorPickerComponent` by modifying the CSS classes used in the component:

css

Копировать код

`.color-picker {   display: flex;   flex-wrap: wrap;   gap: 2px;   max-width: 100%; }  .color-container {   position: relative;   display: flex;   align-items: center;   justify-content: center; }  .color-square {   cursor: pointer;   transition: border 0.3s; }  .color-border {   position: absolute;   border: 2px solid black;   box-sizing: border-box; }`

Development
-----------

To contribute to the development of the `ColorPickerComponent`, clone the repository and install the dependencies:

bash

Копировать код

`git clone https://github.com/your-repo/color-picker.git cd color-picker npm install`

You can then start the development server to see your changes:

bash

Копировать код

`npm start`

Publishing
----------

To publish the library to npm, follow these steps:

1.  Build the library:
    
    bash
    
    Копировать код
    
    `ng build color-picker`
    
2.  Navigate to the `dist/color-picker` directory:
    
    bash
    
    Копировать код
    
    `cd dist/color-picker`
    
3.  Log in to npm (if you are not already logged in):
    
    bash
    
    Копировать код
    
    `npm login`
    
4.  Publish the library:
    
    bash
    
    Копировать код
    
    `npm publish --access public`
    

License
-------

This project is licensed under the MIT License - see the LICENSE file for details.

* * *

This documentation provides an overview of the `ColorPickerComponent`, including installation, usage, inputs, outputs, and an example. This should help users quickly understand how to integrate and use the component in their Angular applications.

go

Копировать код

``Скопируйте этот текст в ваш `README.md` файл, и он будет готов для использования в вашем репозитории на GitHub и для публикации на npm. Не забудьте заменить `your-repo` на реальный URL вашего репозитория на GitHub и `color-picker` на имя вашего пакета на npm.``
