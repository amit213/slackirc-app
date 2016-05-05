## Containerized Slack-IRC bridge module

### What does this do?

You're a heavy or a casual IRC user. However, lack of a good native smart-phone app for IRC (i.e. IRC client) compels you look for solution(s). Here is a solution that will likely work for you.

Get yourself a free Slack account [here](https://slack.com/), and download the native app for your smartphone ([IOS](https://itunes.apple.com/us/app/slack-team-communication/id618783545?mt=8), [Android](https://play.google.com/store/apps/developer?id=Slack%20Technologies%20Inc.&hl=en)).

Use this bridge module, and now your native Slack app is your always-on offline-capable search-history-capable IRC client. Rejoice. 

### Nodejs based bot

This docker wrapper uses the nodejs based bot module written by ekmartin, open sourced under MIC License.
Original module: https://github.com/ekmartin/slack-irc

### How to install and use this?  (below is a one-time setup procedure)

1. **Required**: Linux based VM / machine with outbound access to internet. (i.e. ping google.com works)
2. Install docker and docker-compose on the VM / machine. (Use this [guide](https://docs.docker.com/linux/step_one/), Docker-compose install [guide](https://docs.docker.com/compose/install/))
3. Verify that your userid / login has required access to invoke docker commands. (i.e. `docker ps` should run successfully)
4. Log in to your **slack.com** account, and generate your Slack API user token at https://api.slack.com/docs/oauth-test-tokens
5. This token will be long alphnumeric string token composed of numbers and characters. Save it, as you'll need this later.
6. Git clone this repo:
<pre>
git clone https://github.com/amit213/slackirc-app.git
</pre>
7. Modify `irc-slack-config.json` inside your cloned repo, to update all references of **TODO** with your specific information
8. 



## License

*The MIT License*

Copyright (c) 2014

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


