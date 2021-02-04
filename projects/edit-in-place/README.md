# Tragically Slick Edit In Place

## Overview

Provides a means for having both an edit widget and a display widget in one place in a page and to 
swap between them based on user interaction.

## How To Use The Package

Simply add code to your HTML similar to the following:

```
<tsm-edit-in-place [editingTemplate]="optionEdit"
                   [displayTemplate]="optionDisplay"
                   [editing]="option.editing">
  <ng-template #optionDisplay>
    <span (click)="option.editing = true">{{ option.item.value }}</span>
  </ng-template>
  <ng-template #optionEdit>
    <input matInput [value]="option.item.value">
  </ng-template>
</tsm-edit-in-place>
```

### The Editing And Displaying Templates

The two templates uses are **editingTemplate** and **displayTemplate** which, as their names imply,
are used to name the template for editing the value and the template for displaying the value.

### The Editing Flag

Use the **editing** flag to toggle between the two ways of displaying the data.
