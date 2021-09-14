# SSL Metrics Git LOC Timeline

> Using Git, provide insight into a branches commit LOC changes over time

[![Publish to PyPi](https://github.com/SoftwareSystemsLaboratory/ssl-metrics-git-commits-loc/actions/workflows/pypi.yml/badge.svg)](https://github.com/SoftwareSystemsLaboratory/ssl-metrics-git-commits-loc/actions/workflows/pypi.yml)

## Table of Contents

- [SSL Metrics Git LOC Timeline](#ssl-metrics-git-loc-timeline)
  - [Table of Contents](#table-of-contents)
  - [About](#about)
  - [How to Run](#how-to-run)
    - [Note on Command Line Arguments](#note-on-command-line-arguments)
    - [From pip](#from-pip)
    - [Command Line Arguments](#command-line-arguments)
      - [ssl-metrics-git-commits-loc](#ssl-metrics-git-commits-loc)
      - [ssl-metrics-git-commits-graph](#ssl-metrics-git-commits-graph)
        - [Note on Graph Export Options](#note-on-graph-export-options)

## About

This project is a proof of concept demonstration that **it is possible** to generate useful insights into a Git project via the `git` command line interface.

Currently, this project generates a graph of:

- Number of lines of code against days

## How to Run

### Note on Command Line Arguments

See [Command Line Arguments](#command-line-arguments) for program configuration from the command line

### From pip

1. Install `Python 3.9.6 +`
2. (Recommended) Create a *virtual environment* with `python3.9 -m venv env` and *activate* it
3. Run `pip install ssl-metrics-git-commits-loc`
4. Generate a JSON data set with `ssl-metrics-git-commits-loc -r REPOSITORY -t GH_TOKEN -s FILENAME.json`
5. Generate graphs with `ssl-metrics-git-commits-graph -o OPEN_ISSUES_GRAPH_FILENAME.* -c CLOSED_ISSUES_GRAPH_FILENAME.* -x JOINT_ISSUES_GRAPH_FILENAME`

### Command Line Arguments

#### ssl-metrics-git-commits-loc

- `-h`, `--help`: Shows the help menu and exits
- `-r`, `--repository`: GitHub repository to be used. Format needs to be "OWNER/REPO". Default is numpy/numpy
- `-t`, `--token`: [GitHub personal access token](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- `-s`, `--save-json`: Save analysis to JSON file

#### ssl-metrics-git-commits-graph

##### Note on Graph Export Options

Arguements `-c`, `-o`, and `-x` can be of any of the formats that `matplotlibs.pyplot.savefig` function exports to.

- `-h`, `--help`: Shows the help menu and exits
- `-c`, `--closed-issues-graph-filename`: The filename of the output graph of closed issues
- `-i`, `--input`: The input JSON file that is to be used for graphing
- `-o`, `--open-issues-graph-filename`: The filename of the output graph of open issues
- `-x`, `--joint-issues-graph-filename`: The filename of the output graph of open and closed issues
