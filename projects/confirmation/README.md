# Tragically Slick Confirmation

## Overview

The confirmation library provides a easy to use and reusable confirmation system composed of:

 * a component to provide a standard dialog box, and
 * a service to initiate the process.

## How To Use The Package

Your will need to inject the ```ConfirmationService``` class into the component that will prompt the user
and then responds to their input. Then, at the appropriate time, your code will call the ```confirm()```
method, passing it the title and message for the dialog box as well as a callback hook for what to do if
the user confirms the message.

Look at the following code snippet:

```
import { ConfirmationService } from '@tragically-slick/confirmation';

@Component({...})
export class MessagingBarComponent {
  constructor(private confirmationService: ConfirmationService) {}
  
  onPromptUser(): void {
    this.confirmationService.confirm({
      title: 'Delete This Message',
      message: 'Are you sure you want to delete this message?',
      confirm: () => this.onDeleteMessage()
    });
  }
...
}  
```

In this code sample, when the time comes to prompt a user to delete a message, this service is told to show
a dialog box with the given title and message. If the user approves then the ```onDeleteMessage()``` method
is called. Otherwise, the dialog box is closed and no action is taken.
