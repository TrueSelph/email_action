# Email Action

![GitHub release (latest by date)](https://img.shields.io/github/v/release/TrueSelph/email_action)
![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/TrueSelph/email_action/test-email_action.yaml)
![GitHub issues](https://img.shields.io/github/issues/TrueSelph/email_action)
![GitHub pull requests](https://img.shields.io/github/issues-pr/TrueSelph/email_action)
![GitHub](https://img.shields.io/github/license/TrueSelph/email_action)

This action is designed to handle various email-related operations such as sending, replying, forwarding, drafting, moving, and deleting emails. It processes email actions and directives dynamically, ensuring efficient and automated email management.

## Package Information

- **Name:** `jivas/email_action`
- **Author:** [V75 Inc.](https://v75inc.com/)
- **Architype:** `EmailAction`
- **Version:** 0.0.1

## Meta Information

- **Title:** Email Action
- **Description:** The email action automates email management by enabling sending, reading, replying, and deleting of emails. This action streamlines email workflows by handling repetitive tasks efficiently.
- **Group:** core
- **Type:** action

## Configuration
- **Singleton:** true

## Dependencies
- **Jivas:** ^2.0.0


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
  ```

---

## 🚀 Email Action Setup Guide

### Step 1: Configure Email Accounts

1. Define your email accounts in the configuration file.
2. Include the sender email, password, and optional session ID.

### Step 2: Define Directives

1. Specify directives for processing emails, such as moving to folders or marking as read.

### Step 3: Implement Custom Functions

1. Add custom functions to handle specific email actions as needed.

---

## 🔰 Contributing

- **🐛 [Report Issues](https://github.com/TrueSelph/email_action/issues)**: Found a bug or want to request a feature? Submit it here.
- **💡 [Submit Pull Requests](https://github.com/TrueSelph/email_action/blob/main/CONTRIBUTING.md)**: Check out open PRs or submit your own improvements.

<details closed>
<summary>Contributing Guidelines</summary>

1. **Fork the Repository**: Start by forking the project repository to your GitHub account.
2. **Clone Locally**: Clone the forked repository to your local machine using a git client.
   ```sh
   git clone https://github.com/TrueSelph/email_action
   ```
3. **Create a New Branch**: Always work on a new branch, giving it a descriptive name.
   ```sh
   git checkout -b new-feature-x
   ```
4. **Make Your Changes**: Develop and test your changes locally.
5. **Commit Your Changes**: Commit with a clear message describing your updates.
   ```sh
   git commit -m 'Implemented new feature x.'
   ```
6. **Push to GitHub**: Push the changes to your forked repository.
   ```sh
   git push origin new-feature-x
   ```
7. **Submit a Pull Request**: Create a PR against the original project repository. Clearly describe the changes and their motivations.
8. **Review**: Once your PR is reviewed and approved, it will be merged into the main branch. Congratulations on your contribution!
</details>

<details open>
<summary>Contributor Graph</summary>
<br>
<p align="left">
    <a href="https://github.com/TrueSelph/email_action/graphs/contributors">
        <img src="https://contrib.rocks/image?repo=TrueSelph/email_action" />
   </a>
</p>
</details>

## 🎗 License

This project is protected under the Apache License 2.0. See [LICENSE](../LICENSE) for more information.