# Best Mirrors

Before we start, create backup of your sources list in case anything would go wrong. You can do so using the following command:

```bash
sudo cp /etc/apt/sources.list{,.backup}
```

Next step, we need to install several python utilities. The first one, `pip` is a package manager for python. The second one, `venv` is a tool to create virtual environments for python packages. The third one, `pipx` would be used to install python executable packages in independent environments. You can read about pipx more [here](https://pipx.pypa.io/stable/). Install these tools with this command:

```bash
sudo apt install python3-pip python3-venv pipx
```

Then, we need to complete `pipx` installation process. To do so, run:

```bash
pipx ensurepath
```

Update `PATH` global variable by activating `.profile` file using the following command:

```bash
source ~/.profile
```

Install [`apt-select`](https://github.com/jblakeman/apt-select) tool using pipx.

```bash
pipx install apt-select
```

### Best Mirror Selection

Select best mirrors based on single run for the country:

```bash
apt-select --country RU
```

Show and select one of top 5 mirrors  for the country:

```bash
apt-select -c -t 5 --country RU
```

Find the top 10 mirrors, output latency info only, and choose mirror:

```bash
apt-select -t 10 -p -c --country RU
```
