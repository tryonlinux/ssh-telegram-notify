# ssh-telegram-notify

A bash script that notifies your via telegram when someone SSH's into your server

The idea and most of the bash code comes from [Send message to Telegram on any SSH login
](https://bogomolov.tech/Telegram-notification-on-SSH-login/) by Konstantin Bogomolov.

Set Environmental Vars for Telegram in your /etc/bash.bashrc (if using bash of course). Make a backup just incase.

```
export telegram_Group_ID="-100......."
export telegram_Bot_Token="............."
```

Also in same file add these lines to call your ssh notify script on ssh login

```
if [[ -n $SSH_CONNECTION ]] ; then
    sshLoginNotify
fi
```

Place your Send Telegram script in the below location:

```
/usr/bin/sendTelegramMessage
```

Place your SSH Notify Script in the below location:

```
/usr/bin/sshLoginNotify
```

Logout and back in and see the notification on your telegram group.
