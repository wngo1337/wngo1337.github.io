---
layout: post
title: I Used An AI to Write Songs
subtitle: GPT-2 Model finetuned to sound like the Jonas Brothers
cover-img: /assets/img/ibm.png
thumbnail-img: /assets/img/gpt2.jpeg
share-img: /assets/img/gpt2.jpeg
tags: [machine learning, python, tensorflow]
---

Generative Pre-trained Transformer 2 (GPT-2) is an open-source artificial intelligence created by OpenAI in February 2019. GPT-2 can generate text outputs that sound human! GPT-2 was pretrained on general data from the internet and was done so to model the general distribution of human language from the internet. One of way of extending the functionality of GPT-2 is to finetune the model using a more targeted dataset. By showing the model a more focused set of data, one can steer the model to generate text that models the finetune training data more closely. 

This has numerous benefits, most notably allowing different groups to modify the behaviour of GPT-2 to adopt regional vernacular or industry-specific language without training a completely new model.

Today, we're gonna get it to write pop songs like the Jonas Brothers.

|![JonasBrothers]({{ "/assets/img/lyrics/jonasbrothers.jpg" | relative_url }})|
|:--:|
|You know these guys, right? Of course you do.|

To accomplish our task, we are going to use minimaxir's aitextgen package for Python. You can read more about it [here](https://github.com/minimaxir/aitextgen). It offers a variety of useful methods that abstract away the complexities of the process so that we can focus on generating new lyrics! We are also going to take advantage of Google Colab's free GPU access to speed up the training process.

For now, we want to find a dataset. In this case, a collection of song lyrics. [Kaggle](https://www.kaggle.com/) is a great source of public datasets for training your models. I chose [this one](https://www.kaggle.com/neisse/scrapped-lyrics-from-6-genres). Most datasets require a bit of cleaning (processing) depending on the context that you are using the data for, but that's a process that can be explained another day. 

Once the lyric data is cleaned, we load it into our notebook and can already start training thanks to aitextgen. We let the model train and then download it to our computer.

Now all we have to do is make a barebones Flask app so that we can use our newly trained AI to generate lyrics on the web! You might have trouble finding a free host like I did though. Anyway, let's take a look at the results.

![FirstTry]({{ "/assets/img/lyrics/lyrics1.jpg" | relative_url }})

![SecondTry]({{ "/assets/img/lyrics/lyrics2.jpg" | relative_url }})

They're not perfect, right? But they're passable, kind of cheesy and sentimental. Some attempts are worse than others of course. If I had to train another model next time, I would probably choose a more pop-centric dataset and spend a bit more time cleaning the data. Nonetheless, I feel happy about what I've done and what I've learned, and I hope you enjoyed reading about the process too.

See you guys in the next post!



<!-- ![UI]({{ "/assets/img/ui.png" | relative_url }}) 

Neoquest Auto is a simple-to-use program built with Python and Selenium that helps users to easily
complete the game and get the game trophies by automating the majority of gameplay including map movement, grinding, 
and weapon upgrades, taking the player all the way from the starting square to the final bosses.
It follows a predefined completion strategy that has been tested and modified over multiple runs 
(not tested on InSaNe mode). 
The only user interaction required is choosing the corresponding program option to complete 
each part of the game.

As of now, the program does not keep track of game state on exit.
This may change in the future, but make sure you can run each function to completion before starting.

### Prerequisites

- [Python 3](https://www.python.org/downloads/)
- [Google Chrome](https://www.google.com/intl/en_ca/chrome/)
- [Adblock for Chrome](https://chrome.google.com/webstore/detail/adblock-%E2%80%94-best-ad-blocker/gighmmpiobklfepjocnamgkkbiglidom)

This program has only been tested for Windows.

### Installing

to prepare the program's starting point, login to Neopets and start a new Neoquest game. Once you see the following page, you are finished:

![Skillscreen]({{ "/assets/img/skillscreen.jpeg" | relative_url }}) 

After making a copy of this repository, open the folder in the terminal of your choice and create and activate your virtual environment (venv). 

[Your virtual environment creation instructions](https://docs.python.org/3/library/venv.html) will differ based on what terminal you use.

For example, Windows users using Powershell might perform the following commands:

```
py -m venv venv

venv/Scripts/Activate.ps1
```

Once your venv is activated, use the following command to install the necessary requirements to 
your venv:

```
pip install -r requirements.txt
```

The program is almost ready to run. There are two text files in the src/txtfiles folder named userinfo.txt and 
adblockpath.txt. In userinfo.txt, enter your Neopets username on the first line of the file, 
and your password on the second line.

![Userinfoexample]({{ "/assets/img/userinfoexample.jpeg" | relative_url }}) 

The program can run without adblock enabled, but it will run slowly.
For now, [consult this thread](https://www.reddit.com/r/learnpython/comments/4zzn69/how_do_i_get_adblockplus_to_work_with_selenium/)
for instructions on how to find the path to your adblock extension folder. 
Copy this folder path into adblockpath.txt.
Below is an example of what the folder path could look like for a windows user:

![FolderPath]({{ "/assets/img/extensionfolderexample.jpeg" | relative_url }}) 

Note: I have tried implementing an "Eager" pageLoadStrategy for the Selenium WebDriver, 
and while it does speed up the program, it is still far slower than blocking ads altogether.

Now, navigate to the src directory and run autoplayerlauncher.py to start the program:

```
cd src

py ./autoplayerlauncher.py
```

The program should now launch and present you the following interface:

![ProgramMenu]({{ "/assets/img/programmenuexample.jpeg" | relative_url }}) 

At this point, simply make sure you are on the skill screen and enter 1 in the program.
Below is a list of very rough completion times one can expect for each function:

Option 1: 20~ minutes

Option 2: 50~ minutes

Option 3: 3~ hours

Option 4: 3~ hours

Option 5: 1 hour 40~ minutes

Option 6: 55 minutes

Option 7 (end of game): 1 hour 20~ minutes

## Built With

* [Python](https://www.python.org) - The programming language used
* [Selenium](https://www.selenium.dev) - Used for automating browser navigation -->
