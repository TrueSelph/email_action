# Email Action

## Overview

The `EmailAction` module is designed to handle various email-related operations such as sending, replying, forwarding, drafting, moving, and deleting emails. It integrates with an email API and leverages a language model to process email actions and directives dynamically. This module is part of the `jivas` framework and is configured to work with multiple email accounts.

---

## Features

- **Email Actions**: Supports actions like `delete`, `draft`, `send`, `reply`, `move`, and `forward`.
- **Language Model Integration**: Uses a language model to process email content and determine appropriate actions.
- **Email Automation**: Automates email processing, including marking emails as read, moving them to specific folders, or deleting them.
- **Customizable Functions**: Allows defining custom functions for handling email actions.
- **Multi-Account Support**: Handles multiple email accounts with individual configurations.
- **Error Handling**: Includes robust error handling and logging for email operations.

---

## Configuration

### Properties

- **`accounts`**: A list of email account configurations. Each account should include:
  - `sender_email`: The email address of the sender.
  - `sender_password`: The password for the email account.
  - `sender_session_id` (optional): A unique session ID for the sender.
  - `directives`: A list of directives for processing emails.

- **`mark_as_read`**: A boolean indicating whether to mark emails as read after processing. Default is `True`.

- **`email_actions`**: A list of supported email actions:
  - `delete`
  - `draft`
  - `send`
  - `reply`
  - `move`
  - `forward`

- **`channel`**: The communication channel, default is `"email"`.

- **`functions`**: A list of functions for handling email actions. Example:
  ```json
  {
    "type": "function",
    "function": {
      "name": "handle_email_action",
      "description": "Process email actions based on the content and directives.",
      "parameters": {
        "type": "object",
        "properties": {
          "actions": {
            "type": "array",
            "items": {
              "type": "string",
              "enum": ["delete", "draft", "send", "reply", "move", "forward"]
            },
            "description": "List of actions to be performed on the email."
          },
          "directives": {
            "type": "array",
            "items": {
              "type": "string"
            },
            "description": "Directives for processing the email."
          }
        },
        "required": ["actions"]
      }
    }
  }