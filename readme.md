## Containerized Slack-IRC bridge module

### What does this do?

You're a heavy or a casual IRC user. However, lack of a good native smart-phone app for IRC (i.e. IRC client) compels you look for solution(s). Here is a solution that will likely work for you.

Get yourself a free Slack account [here](https://slack.com/), and download the native app for your smartphone ([IOS](https://itunes.apple.com/us/app/slack-team-communication/id618783545?mt=8), [Android](https://play.google.com/store/apps/developer?id=Slack%20Technologies%20Inc.&hl=en)).

Use this bridge module, and now your native Slack app is your always-on offline-capable search-history-capable IRC client. Rejoice. 

### Nodejs based bot

This docker wrapper uses the nodejs based bot module written by ekmartin, open sourced under MIC License.
Original module: https://github.com/ekmartin/slack-irc

### How to install and use this?  (below is a one-time setup procedure)

1. **Required**: Linux based VM / machine with outbound access to internet. (i.e. ping google.com should work) (*Avg. 1-CPU, 756mb ram, 15GB disk should suffice.*)
2. Install docker and docker-compose on the VM / machine. (Use this [guide](https://docs.docker.com/linux/step_one/), Docker-compose install [guide](https://docs.docker.com/compose/install/))
3. Verify that your userid / login has required access to invoke docker commands. (i.e. `docker ps` should run successfully)
4. Log in to your **slack.com** account, and generate your Slack API user token at https://api.slack.com/docs/oauth-test-tokens
5. This token will be long alphnumeric string token composed of numbers and characters. Save it, as you'll need this later.
6. **Required**: Go to your slack home page https://**your-team-name**.slack.com/admin/settings#gateways and look for **Permissions** tab. Once you get there, scroll down and look for **Gateways** setting. Hit `expand` and click `Enable IRC gateway (SSL only)` setting to enable it.
7. Git clone this repo:
<pre>
git clone https://github.com/amit213/slackirc-app.git
</pre>
8. Within your cloned repo, please modify `irc-slack-config.json` to update all the **TODO** mentions with your information, including your slack API token.
9. **Required**: Build and Run docker compose using following commands
<pre>
$ cd slackirc-app
$ docker-compose build --force-rm --no-cache
$ docker-compose up -d
$ docker-compose ps  (Confirm that your container is running properly, and that it has not gone in a exit-restart loop)
</pre>
10. Create new channels in Slack, corresponding to the IRC channel names and add them to `irc-slack-config.json` as needed



### Tips and Troubleshooting

* Successful `docker-compose build` command will result into below output
<pre>
Step 10 : CMD node /usr/src/app/index.js --config /usr/src/app/irc-slack-config.json
 ---> Running in a97517e9d629
 ---> ed0cdd6dfaf3
Removing intermediate container a97517e9d629
Successfully built ed0cdd6dfaf3
user@linuxVM1:~/slackirc-app$
</pre>


## License

*The MIT License*

Copyright (c) 2014

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


