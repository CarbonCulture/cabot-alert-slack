Cabot Slack Plugin
=====

Based on: https://github.com/bonniejools/cabot-alert-hipchat

This is an alert plugin for the cabot service monitoring tool. It allows you to alert users by their user handle in a slack channel.

## Installation

Enter the cabot virtual environment.

```
    $ pip install git+git://github.com/CarbonCulture/cabot-alert-slack.git
    $ foreman stop
```

Edit `conf/*.env`. Icon fields are optional, if not set alerts should fall back to the bell emoji (URL takes precedence over emjoi setting)

```
CABOT_PLUGINS_ENABLED=cabot_alert_slack==0.5
...
SLACK_ALERT_CHANNEL=channel_name_without_hash
SLACK_WEBHOOK_URL=url_of_your_webhook_integration_from_slack
```
Optional:
```
SLACK_ICON_EMOJI=':satellite:'
```
or
```
SLACK_ICON_URL=http://lorempixel.com/40/40/
```

Add cabot_alert_slack to the installed apps in settings.py
```
    $ foreman run python manage.py syncdb
    $ foreman start
```
