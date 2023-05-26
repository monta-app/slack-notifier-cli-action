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
    github-context: ${{ toJson(github) }}
    job-type: <job-type>
    job-status: <job-status>
    service-name: <service-name>
    service-emoji: <service-emoji>
    slack-app-token: <token>
    slack-channel-id: <channel-id>
```

See further documentation of options in [action.yml](./action.yml)
