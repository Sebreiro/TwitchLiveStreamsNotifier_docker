TelegramBotMessageSender_docker
==
[Docker image](https://hub.docker.com/r/sebreiro/twitchlivestreamsnotifier_docker/) of [TwitchLiveStreamsNotifier](https://github.com/Sebreiro/TwitchLiveStreamsNotifier)

### Note ###  
Application has no environment variables, all settings located in the config file `appsettings.json`  
Information about confg files located in [TwitchLiveStreamsNotifier repository](https://github.com/Sebreiro/TwitchLiveStreamsNotifier#config)

When container starts, it's copy default config (if not exists) to `/app/Config`  

Logs located in `/app/Log`

# docker-compose
~~~
twitch:
    image: sebreiro/twitchlivestreamsnotifier_docker:latest
    container_name: twitch_streams_notifier
    restart: unless-stopped
    volumes:
      - /home/twitch_telegram/twitch/Config:/app/Config
      - /home/twitch_telegram/twitch/Log:/app/Log
~~~
