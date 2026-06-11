# Monta `slack notifier cli action`

Github action for posting a message to Slack.

This is used as part of our builds to post progress messages to Slack.

Most projects don't use this directly, but indirectly through the [github-workflows](https://github.com/monta-app/github-workflows)

## Example of Github workflow job

```yaml
steps:
- name: Publish progress message to slack
  uses: monta-app/slack-notifier-cli-action@main
  id: publish-slack
  with:
    job-type: <job-type>
    job-status: <job-status>
    service-name: <service-name>
    service-emoji: <service-emoji>
    slack-app-token: <token>
    slack-channel-id: <channel-id>
```

See further documentation of options in [action.yml](./action.yml)

## Graceful failure

By default (`fail-on-error: 'false'`), the action will **not** fail your workflow if the Slack notification cannot be delivered (e.g. the target channel has been archived or deleted). Instead it emits a warning annotation and continues. If you need strict failure behaviour, set `fail-on-error: 'true'`.
