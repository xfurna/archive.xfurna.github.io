+++
categories = ["AI"]
coders = []
date = 2020-11-15T19:44:17+05:30
description = "Ai solution for Luhmann's Zettelkasten"
github = ["https://github.com/xfurna/zettelkasten-ai/"]
image = "zettelkastenai/logo.png"
title = "Zmsai"
type = "post"

+++

Productivity is the core value of work. In the modern economy, where at every step one has to face cut-throat competition, it is becoming increasingly important to produce at an elite level. Professional activities demand an affiliation to the task at hand that can push one’s cognitive capability to its limits. In order to thrive in this new economy, one needs to master two core abilities- first, the ability to quickly master hard things and second, the ability to produce at the highest level in terms of both quality and speed. Humans have a natural tendency to alter the *form* of the idea and call it innovation. In contrast, according to first-principles thinking, it is the ideas which are perceived and worked upon for optimising the *function* that renders top-class results. Such a mindset helps in connecting the ideas from various domains and come up with the solution to the problem at hand relatively efficiently. 
Luhmann’s Zettelkasten is one technique which enables the user to organise their ideas and uncover the emergent connections between them in order to think creatively. Zettelkasten is essentially a note-taking technique, but unlike its alternatives, instead of simply jotting down the ideas on paper or cloud and burying them under some thousands of such notes, all the written pieces are kept dynamic. That means maintaining a knowledge bank where every new idea is linked with old ideas to form connections. The technique elegantly rectifies the chances of [collection fallacy](https://zettelkasten.de/posts/collectors-fallacy/) and genuinely generates value from the notes.

Zettelkasten was invented by a German scholar [Niklas Luhmann](https://en.wikipedia.org/wiki/Niklas_Luhmann). In his almost 40 years of a research career, he published [more than 400 scholarly articles and 70 books](https://www.researchgate.net/publication/278131440_Niklas_Luhmann_as_organization_theorist) on diverse topics ranging from biology and sociology to computer science. When asked how had been this prolific in his entire career, he replied *“I am not thinking everything on my own. Much of it happens in my Zettelkasten. My productivity is largely explained by the Zettelkasten method.”*
As Luhmann describes it, Zettelkasten was originally a piece of furniture consisting of several stacks of drawers. Each drawer was supposed to have paper notes filled to the brim.
Each new addition is meant to go in a specific drawer based on its ​topic​. Additionally, each card was supposed to be connected with all the cards that can possibly be related to that card, regardless of the drawer in which they are. As a result, an establishment as depicted below will be formed.

![mind_map](https://raw.githubusercontent.com/xfurna/xfurna.github.io/master/static/zettelkastenai/mind_map.png)

There are many note-taking apps and software out there that support filtering the notesbased on tags. However, when it comes to linking components, either they do not do it at all or ask for a premium subscription. This project seized this opportunity to developan AI-based solution for uncovering the hidden topical patterns in the collection of notes in the Zettelkasten, automating the annotation of each card (document) and using those annotations to organise, summarise and enable topic-wise search of the Zettelkasten.

Read the [report](https://drive.google.com/file/d/1IONbczPPcIZWUQib1kgxrN4nCNIoTyo8/view?usp=sharing) to know more.

# The Project
A command line utility for topic discovery and doc-linking within the Zettelkasten using AI approaches.

## Installation
Install `zmsai` by executing the following command-
```shell
$ pip3 install zmsai
```

## Test Run
Test run using dummy docs (see `./custom`)
```shell
$ zmsai test
```
It will work only if you install the project from the source code.

## Usage
To learn `n` topics in your Zettelkasten at `/path/to/your/zettelkasten/`-
```shell
$ zmsai run -t n -p "/path/to/your/zettelkasten/"
```
This will create a metadata file `meta.zms` storing all the distributions exhibited by the documents in your Zettelkasten.
```shell
[Running the model] it may take a while. Hang tight!
[Data stored] ... kb
``` 
You can delete your metadata file by executing-
```shell
$ zmsai delete
```

These learnt distributions can be printed using `zmsai display`. You can pass an additional argument `-w`, the number of top most occuring words that you want to print from the distributions involing words.

To display doc-topic distribution-
```shell
$ zmsai display -d dt
```
To display topic-word distribution-
```shell
$ zmsai display -w n -d tw
```
To display doc-word distribution-
```shell
$ zmsai display -w n -d dw
```
To display vocabulary-
```shell
$ zmsai display -w n -d voc
```
To display all distributions at once-
```shell
$ zmsai display -w n -d all
```
or simply
```shell
$ zmsai display
```
This will take default value of 5 for `nwords` argument.

## Troubleshooting
If you get `ModuleNotFoundError: No module named 'sklearn'` error with `display`, try installing `scikit-learn` manually.
```shell
$ sudo pip3 install -U scikit-learn
```
Alternatively, if you're on ubuntu, try executing the following command-
```shell
$ zmsai fix-ubuntu
```

Feel free to raise an issue if you feel stuck.

## Manual
```shell
usage: zmsai [-h] [--path [PATH]] [--topics [TOPICS]] [--nwords [NWORDS]] [--distro [DISTRO]] [task]

positional arguments:
  task                  Provide task to perform [default : 'run'] [values : 'run', 'delete', 'display', 'man', 'test', 'fix-ubuntu']

optional arguments:
  -h, --help            show this help message and exit
  --path [PATH], -p [PATH]
                        Provide directory of text files. [with : 'run'] [default : './custom']
  --topics [TOPICS], -t [TOPICS]
                        How many topics do you expect? [with : 'run'] [default : 'number of docs']
  --nwords [NWORDS], -w [NWORDS]
                        How many words per topic/doc do you want to display? [with : 'display'] [default : 5]
  --distro [DISTRO], -d [DISTRO]
                        What distributions do you want to display? [with : 'display'] [default : all] [values : 'dt', 'tw', 'dw', 'voc', 'all']
```

## Dependency Graph

```shell
attrs==20.2.0
  - pytest==6.1.1 [requires: attrs>=17.4.0]
iniconfig==1.1.1
  - pytest==6.1.1 [requires: iniconfig]
joblib==0.17.0
  - scikit-learn==0.23.2 [requires: joblib>=0.11]
    - sklearn==0.0 [requires: scikit-learn]
numpy==1.19.2
  - scikit-learn==0.23.2 [requires: numpy>=1.13.3]
    - sklearn==0.0 [requires: scikit-learn]
  - scipy==1.5.3 [requires: numpy>=1.14.5]
    - scikit-learn==0.23.2 [requires: scipy>=0.19.1]
      - sklearn==0.0 [requires: scikit-learn]
pip==20.1.1
pluggy==0.13.1
  - pytest==6.1.1 [requires: pluggy>=0.12,<1.0]
py==1.9.0
  - pytest==6.1.1 [requires: py>=1.8.2]
pyparsing==2.4.7
  - packaging==20.4 [requires: pyparsing>=2.0.2]
    - pytest==6.1.1 [requires: packaging]
setuptools==46.4.0
six==1.15.0
  - packaging==20.4 [requires: six]
    - pytest==6.1.1 [requires: packaging]
threadpoolctl==2.1.0
  - scikit-learn==0.23.2 [requires: threadpoolctl>=2.0.0]
    - sklearn==0.0 [requires: scikit-learn]
toml==0.10.1
  - pytest==6.1.1 [requires: toml]
wheel==0.34.2
```
## Contribution
Are welcome.

## License
[GNU General Public License v3 (GPLv3)](https://www.gnu.org/licenses/gpl-3.0)
