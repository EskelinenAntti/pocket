# Pocket

You are deeply focused to build the next billion dollar app. Suddenly your coworker pokes you and asks for help – the backend is down and every second counts as lost customers. 

"No worries, we just need to revert back to previous version" you answer confidently knowing that you've done that a few times before in test environment. 

You open the terminal, and realize you've forgotten what the exact command for reverting previous version was. You hit ´ctrl R´, but no luck. It's been too long since you needed that command for the last time. You feel the cold sweat on your forehead. "There has to be a better way" you think before you dive into the pile of unstructured and outdated documentation.

<img src="https://th.bing.com/th/id/OIG3.FDFHK3tUdQ3l0qu0_AUy?pid=ImgGn" width="360"/>

There *is* a better way.

## What does it do?

- Removes the cognitive strain of remembering commands you rarely need
- Makes it very easy to write down new commands and retrieve them right where you need them – in your terminal!
- Really lightweight, just a few lines of bash code (You would probably do well by simply memoizing the the few bash commands this invokes under the hood. But hey, at least implementing this script was a fun learning experience for me 🤷)

```bash
$ pocket add 'git rebase main --update-refs'
$ pocket add 'adb exec-out screencap -p > screen.png'
$ pocket find adb
adb exec-out screencap -p > screen.png
```


## Install

Clone the repo and add the `/bin` folder to your path. E.g. if you're using Mac and Zsh, you might want to run the following commands:

```bash
# Clone the repository.
git clone git@github.com:EskelinenAntti/pocket.git

# Enter into the cloned repo.
cd pocket/

# Add pocket to PATH. Warning: You need to be in the correct folder 
# and using Zsh for this to work!
echo PATH=\$PATH:$PWD/bin >> ~/.zshrc

# Refresh the terminal session.
source ~/.zshrc

# start using pocket
pocket --help
```
