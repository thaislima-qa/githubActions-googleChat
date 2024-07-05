# GitHub Action-Google Chat

Integration between Github Actions and Google Chat to trigger a notification after a workflow has been executed.

## Preview

Default (non-collapsible):

Image

Collapsed:

Image

Expanded:

Image

## Example

```yaml
- name: Notification GitHub Actions to Google Chat
  uses: thaislima-qa/githubActions-googleChat@v0
  with:
    name: Tests E2E
    url: ${{ secrets.GOOGLE_CHAT_WEBHOOK }}
    status: ${{ job.status }}
  if: always()
  continue-on-error: true

```

## Usage

```yaml
- name: Notification GitHub Actions to Google Chat 
  uses: thaislima-qa/githubActions-googleChat@v0
  with:
    name: Tests E2E
    # The name of the job. Used in the card title
    # Required
    url: ${{ secrets.GOOGLE_CHAT_WEBHOOK }}
    # Google Chat Webhook URL
    # Required
    status: ${{ job.status }}
    # Job status. It may be one of `success`, `failure`, `cancelled`. 
    # Required
    collapse: 3
    # The number of widgets in the card section that are not collapsible
    # Defaults to -1: card is not collapsible.
    # Optional
  if: always() 
  continue-on-error: true
  # this allows the build to succeed even when the notification fails
```
