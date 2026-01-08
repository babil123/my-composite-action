📦 My Composite GitHub Action

A reusable Composite GitHub Action that demonstrates how to package common workflow steps into a single, versioned action.

🚀 What This Action Does

Accepts an input value

Executes shell commands using bash

Can be reused across multiple repositories

Versioned using Git tags (v1)

📁 Repository Structure
.
├── action.yml
└── README.md

🧩 Inputs

| Name      | Required | Default                       | Description                      |
| --------- | -------- | ----------------------------- | -------------------------------- |
| `message` | Yes      | `Hello from composite action` | Message to print in the workflow |

▶️ Usage

Use this action in any GitHub Actions workflow.
name: Use Composite Action

on:
  push:
    branches:
      - main

jobs:
  demo:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Run custom composite action
        uses: <username>/<repo-name>@v1
        with:
          message: "Hello from my workflow 🚀"
🔁 Replace:

<username> → your GitHub username

<repo-name> → your action repository name


🛠 How It Works

GitHub downloads the repository at the specified tag (v1)

Reads action.yml

Executes the defined composite steps

Runs inside the same runner as the calling workflow

🏷 Versioning Strategy

This action follows GitHub Actions best practices:

Use tags (v1, v1.1, v2)

Avoid using branches like main in workflows

Update tags for stable releases

Example:
git tag -a v1 -m "Release v1"
git push origin v1

❗ Important Notes

Composite actions do not create their own runner

All steps run in the caller’s job environment

shell must be explicitly defined for each step

🧠 When to Use Composite Actions

✅ Reusable shell logic
✅ Build / test / scan steps
✅ Organization-wide standardization
❌ Heavy tooling (use Docker actions instead)


