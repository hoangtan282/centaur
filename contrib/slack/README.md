# Slack App Manifest

Use `contrib/slack/manifest.yaml` in Slack's "Create New App from manifest" flow.

Before pasting the manifest, replace every `https://YOUR_PUBLIC_SLACKBOT_HOST`
with the public HTTPS URL that routes to the slackbot service.

After creating the app:

1. Install it to the workspace.
2. Copy **OAuth & Permissions -> Bot User OAuth Token** into `SLACK_BOT_TOKEN`.
3. Copy **Basic Information -> Signing Secret** into `SLACK_SIGNING_SECRET`.
4. Set `SLACKBOT_API_KEY` to the same service key configured for the API.
5. Invite the bot to target channels, or keep `chat:write.public` if it should reply in public channels before being invited.

The default manifest includes `/website-feedback` because the slackbot has a
Linear feedback command handler. If that command is not needed, remove the
`features.slash_commands` entry and the `commands` scope.
