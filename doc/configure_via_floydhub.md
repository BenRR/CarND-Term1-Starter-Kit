# Running projects on FloydHub

[FloydHub](https://www.floydhub.com) is an experimentation platform for Machine Learning and Deep Learning.
You can get a deep learning environment (Keras, Tensorflow or Theano) up in seconds and run your code inside that.
It is easy to select the type of instance you want to run your project on (CPU vs GPU) and you can also work 
on your project interactively with Jupyter / IPython.

## Overview

Using Floyd to run your code consists of the following:

1. Setup Floyd on your machine
2. Run you code in the cloud on Floyd.

### GPU support

If you want access to a GPU when running your project, just add `--gpu` flag when you run your project.
More info on this is available [here](http://docs.floydhub.com/home/getting_started/#training-on-cpu-vs-gpu).

---


### Setup Floyd

- Install [floyd-cli](https://pypi.python.org/pypi/floyd-cli) on your machine. Instructions for installation 
is same for all OS:

```sh
pip install -U floyd-cli
```

More info on installation is available [here](http://docs.floydhub.com/home/getting_started/#installing-floyd-cli).

- Create a [FloydHub account](https://www.floydhub.com/). You get started with Free credits.

- Use the [floyd login](http://docs.floydhub.com/commands/login/) command in the cli to login to FloydHub.

```sh
floyd login
```
---

### Run your code on Floyd

The list of dependencies required for the first 
term projects is added to `floyd_requirements.txt` file. 
These will be pre-installed before your code is run. Make sure that this file 
is present at the root of your project directory.

In your shell, navigate to the directory of a project, e.g.

```bash
$ cd ~/src/CarND-LaneLines-P1
```

Download the [floyd_requirements.txt](https://raw.githubusercontent.com/floydhub/CarND-Term1-Starter-Kit/master/floyd_requirements.txt) 
file here. 
here.

```bash
$ wget https://raw.githubusercontent.com/floydhub/CarND-Term1-Starter-Kit/master/floyd_requirements.txt
```

Now you can now start running [floyd commands](http://docs.floydhub.com/commands/). First initialize your project:

```sh
floyd init CarND-LaneLines-P1
```

You can run a IPython notebook with the code in the current directory.

```sh
floyd run --mode jupyter
```

You should get a URL that you can use to interact with your notebook.

### GPU

If you need an environment with GPU setup, just add `--gpu` to the run command.

```sh
floyd run --gpu --mode jupyter
```

To learn more about FloydHub by [visiting the docs](http://docs.floydhub.com/)

### Upload delay

In case your project is taking a while to upload it is probably because of the video 
files present in the repo. We have made those videos available as a [dataset](http://docs.floydhub.com/home/using_datasets/) 
on Floyd. You can just refer to it using the `--data` paramter when running your project.

```sh
rm *.mp4
floyd run --mode jupyter --data MmSYSyWoZ63nQeTxmrhGRQ
```

The contents of [MmSYSyWoZ63nQeTxmrhGRQ](https://www.floydhub.com/viewer/data/3nu5uBhbFiXk7J3vLUJnHN/) will be 
available at `/input` path. More information on this is available in the [docs](http://docs.floydhub.com/home/using_datasets/)

---
