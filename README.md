home-assistant-tp-link-kasa-smart
# Home Assistant - TP-Link Kasa Smart

Based on "TP-Link Kasa Smart" at https://www.home-assistant.io/integrations/tplink/#:~:text=Go%20to%20Settings%20%3E%20Devices%20%26%20Services,screen%20to%20complete%20the%20setup.

Based on "kasa command line tool" at https://python-kasa.readthedocs.io/en/latest/cli.html#provisioning

Based on "Python Kasa" at https://python-kasa.readthedocs.io/en/latest/index.html

## 100 - Introduction

With TP-Link Kasa Smart we can manage TP-Link Kasa Smart Devices from Home Assistant.

For example, we own a TP-Link Kasa Smart Plug (**HS-110**) which we should be able to switch on/off remotely.

## 200 - Requirements

We require ```python``` to be installed on our Mac OS.

Anyone updating their macOS to Monterey 12.3 will find that they suddenly no longer have the system-provided Python 2.

The reason for this is that Apple removed the system-provided Python 2 installation ([details](https://macmule.com/2022/01/29/macos-monterey-12-3-will-remove-python-2-7-usr-bin-python/)).

So a workaround/solution for this is to use *pyenv* to install Python 2.7 (or any other specific version you need).

1. Install ```pyenv``` with ```brew``` to manage different Python versions: ```$ brew install pyenv```
2. List all installable versions with ```$ pyenv install --list```
3. Install Python 2.7.18 with ```$ pyenv install 2.7.18```
4. List installed versions with ```$ pyenv versions```
5. Set global python version with ```pyenv global 2.7.18```
6. Add ```eval "$(pyenv init --path)"``` to ```~/.zprofile``` (or ```~/.bash_profile``` or ```~/.zshrc```, whichever you need)
7. Relaunch the shell and check that Python works, or run ```$ source ~/.zprofile```

We are going to make use of python-kasa and will install it on Mac OS (Mac Mini).

Hence, we require ```pip``` on Mac OS, see [How to install pip on Mac step by step](https://macpaw.com/how-to/install-pip-mac).

After pip has been installed we follow the [instructions](https://python-kasa.readthedocs.io/en/latest/index.html) to install ```python-kasa``` on Mac OS.


## 300 - Building Our Application


## 400 - Conclusion
