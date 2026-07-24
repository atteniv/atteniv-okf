---
type: Reference
title: Getting Started with the Atteniv OKF Knowledge Base
description: End-user setup for the OKF Editor, GitHub synchronization, OpenRouter AI, and optional Perplexity website research.
tags: [setup, okf-editor, github, openrouter, perplexity]
---

# Getting Started

This repository is an [Open Knowledge Format (OKF)](https://okf.md) bundle for
Atteniv. The Markdown files remain readable in GitHub or any text editor, but the
recommended authoring experience is the
[Atteniv OKF Editor](https://github.com/atteniv/okf-editor).

## What You Need

| Item | Required? | Purpose |
|---|---:|---|
| Atteniv OKF Editor | Recommended | Browse, edit, validate, and synchronize this bundle |
| GitHub personal access token | For GitHub sync | Clone, pull, commit, and upload through the editor |
| OpenRouter API key | Optional | AI document drafting, chat, and merge assistance |
| Perplexity API key | Optional | Create a new OKF bundle by researching a public website |

OpenRouter and Perplexity are not required for ordinary editing. API usage is
billed by those providers under your own accounts.

## 1. Install or Run the OKF Editor

Follow the current instructions in the
[OKF Editor README](https://github.com/atteniv/okf-editor#compile-and-run-from-source).
If you already have the editor installed, open it and continue below.

> The editor stores credentials in your operating system keychain. Do not add
> tokens or API keys to this repository, Markdown files, `.okf-editor.json`, or
> an `.env` file.

## 2. Create a GitHub Personal Access Token

Use a fine-grained token so access is limited to this repository.

1. Open [GitHub's fine-grained token page](https://github.com/settings/personal-access-tokens/new).
2. Enter a descriptive name such as `OKF Editor` and choose an expiration date.
3. Select **atteniv** as the resource owner. If GitHub does not offer that
   choice, confirm that your GitHub account has access to the Atteniv
   organization and this repository.
4. Under **Repository access**, choose **Only select repositories**, then select
   **atteniv-okf**.
5. Under **Permissions → Repository permissions**, set **Contents** to
   **Read and write**. No other repository permission is required for working
   with an existing bundle repository.
6. Generate the token and immediately copy the value beginning with
   `github_pat_`; GitHub displays it only once.
7. If the Atteniv organization requires token approval, wait for an organization
   owner to approve it before using Git synchronization.

In the OKF Editor:

1. Open **Settings → GitHub**.
2. Paste the token into **Token** and select **Save token**.
3. Confirm that the editor reports `connected as @your-user-name`.
4. Choose **Clone from GitHub** and use:

   ```text
   https://github.com/atteniv/atteniv-okf.git
   ```

5. Choose an empty parent folder when prompted. The editor creates the
   `atteniv-okf` folder during cloning.

If you already cloned this repository outside the editor, choose
**Open bundle folder…** and select the repository root instead.

### GitHub Token Notes

- A fine-grained token is preferred over a classic token because it can be
  restricted to one repository.
- If organization policy requires a classic token, ask an Atteniv organization
  administrator which scope to use. The classic `repo` scope is broad and should
  only be used when fine-grained tokens are unavailable.
- When a token expires, create a replacement and save it in
  **Settings → GitHub**.
- Revoking the token does not delete local bundle files or Git history.

## 3. Configure OpenRouter AI (Optional)

OpenRouter powers AI-assisted document generation, document chat, and merge
assistance.

1. Create or sign in to an account at [OpenRouter](https://openrouter.ai).
2. Add credit on the [Credits](https://openrouter.ai/settings/credits) page.
3. Open [Keys](https://openrouter.ai/keys), select **Create Key**, and name it
   something recognizable such as `OKF Editor`.
4. Optionally set a credit limit on the key to cap its spending.
5. Copy the key beginning with `sk-or-`.
6. In the OKF Editor, open **Settings → AI (OpenRouter)**, paste the key, and
   select **Save key**.
7. Select a default model from the model picker. The editor retrieves the
   available model catalog after the key is saved.

Using an AI feature sends the relevant document content and instructions to
OpenRouter under your account. Review content sensitivity and your selected
model provider's data policy before submitting confidential material.

## 4. Configure Perplexity Website Research (Optional)

Perplexity is only needed for the editor's **Research a website** workflow when
creating a new bundle. It is not needed to edit this repository.

1. Open the [Perplexity API Console](https://console.perplexity.ai).
2. Add API billing credit and generate an API key. A consumer Perplexity Pro
   subscription does not include API usage.
3. Copy the key beginning with `pplx-`.
4. In the OKF Editor, open **Settings → Website research (Perplexity)**, paste
   the key, and select **Save key**.
5. Select **Test key** and confirm that the editor reports a successful
   connection.

Website research sends the target URL, retrieved public content, bundle schema,
and your instructions to Perplexity. Model and search/fetch tool usage may both
incur charges.

## 5. Everyday Editing Workflow

1. Select **Pull Updates** before starting work.
2. Edit documents in the bundle. Keep YAML frontmatter intact on concept files.
3. Review validation diagnostics and fix broken links or missing required fields.
4. In the Git panel, enter a concise description and select **Save Changes**.
   For a connected repository, this commits and uploads the changes to GitHub.
5. If the editor reports a conflict, review both versions before choosing which
   content to keep.

The root [`index.md`](index.md) is the bundle's content directory.
[`.okf-editor.json`](.okf-editor.json) defines the document types and editable
frontmatter fields.

## Security and Troubleshooting

- **Never commit credentials.** The editor uses the OS keychain; this repository
  intentionally has no `.env.example` because end-user credentials are not read
  from environment files.
- **Token check fails:** confirm the token has not expired, is approved by the
  organization, can access `atteniv/atteniv-okf`, and has **Contents: read and
  write**.
- **Clone works but upload fails:** public repositories can often be cloned
  without authentication, but uploading requires write access and a valid token.
- **OpenRouter model list is empty:** verify the key, account credit, and any
  key-level spending limit, then reopen Settings.
- **Perplexity test fails:** verify API credit and the API key; Perplexity Pro
  billing is separate.
- **Linux keychain error:** ensure a Secret Service provider such as GNOME
  Keyring or KWallet is installed, unlocked, and running.
- **Suspected exposure:** revoke the credential immediately at the provider,
  create a replacement, and update it in the editor's Settings.
