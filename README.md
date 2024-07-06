# ColorPickerComponent

The `ColorPickerComponent` is an Angular component designed to display a customizable color picker. Users can specify the colors, the size of each color square, the maximum number of colors, and the number of columns in which the colors should be arranged. This component implements `ControlValueAccessor`, making it compatible with Angular forms.

## Installation

To use the `ColorPickerComponent` in your project, install it via npm:

```bash
npm install color-picker
```



## Usage


First, import the `ColorPickerComponent` into your Angular module:

```typescript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { ReactiveFormsModule } from '@angular/forms';
import { ColorPickerModule } from 'color-picker';
@NgModule({
  declarations: [AppComponent],
  imports: [BrowserModule, ReactiveFormsModule, ColorPickerModule],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

Then, you can use the `ColorPickerComponent` in your templates:

```html
<lib-color-picker
  [colors]="colorArray"
  [squareSize]="30"
  [maxColors]="50"
  [numColumns]="5"
  (colorChange)="onColorChange($event)"
>
</lib-color-picker>
```

## Inputs

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

```typescript
import { Component } from '@angular/core';
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
export class AppComponent {
  colorArray: string[] = [
    '#FF0000',
    '#00FF00',
    '#0000FF',
    '#FFFF00',
    '#FF00FF',
    '#00FFFF',
  ];
  selectedColor: string;
  onColorChange(color: string) {
    this.selectedColor = color;
  }
}
```

### HTML (Template)

```html
<div>
  <h1>Color Picker Example</h1>
  <lib-color-picker
    [colors]="colorArray"
    [squareSize]="30"
    [maxColors]="50"
    [numColumns]="5"
    (colorChange)="onColorChange($event)"
  >
  </lib-color-picker>
  <p>Selected Color: {{ selectedColor }}</p>
</div>

```

License
-------

This project is licensed under the MIT License - see the LICENSE file for details.

* * *

This documentation provides an overview of the `ColorPickerComponent`, including installation, usage, inputs, outputs, and an example. This should help users quickly understand how to integrate and use the component in their Angular applications.

