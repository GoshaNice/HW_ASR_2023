# ASR HW1
#### Implemented by: Pistsov Georgiy 202

You can find report here: 

## Installation guide

Current repository is for Linux

(optional, not recommended) if you are trying to install it on macos run following before install:
```shell
make switch_to_macos
```

Then you run:

```shell
make install
```

## Run tests:

```shell
make test
```

## Download Language model:

```shell
make download_language_model
```
The file "lm.bin" will be in language_models/


## Download checkpoint:

```shell
make download_checkpoint
```
The file "model_best.pth" will be in default_test_model/

## Recommended implementation order

You might be a little intimidated by the number of folders and classes. Try to follow this steps to gradually undestand
the workflow.


4) Implement functions in `hw_asr\metric\utils.py`
5) Implement missing function to run `train.py` with a baseline model
6) Write your own model and try to overfit it on a single batch
7) Implement ctc beam search and add metrics to calculate WER and CER over hypothesis obtained from beam search.
8) ~~Pain and suffering~~ Implement your own models and train them. You've mastered this template when you can tune your
   experimental setup just by tuning `configs.json` file and running `train.py`
9) Don't forget to write a report about your work
10) Get hired by Google the next day

## Before submitting

0) Make sure your projects run on a new machine after complemeting the installation guide or by 
   running it in docker container.
1) Search project for `# TODO: your code here` and implement missing functionality
2) Make sure all tests work without errors
   ```shell
   python -m unittest discover hw_asr/tests
   ```
3) Make sure `test.py` works fine and works as expected. You should create files `default_test_config.json` and your
   installation guide should download your model checpoint and configs in `default_test_model/checkpoint.pth`
   and `default_test_model/config.json`.
   ```shell
   python test.py \
      -c default_test_config.json \
      -r default_test_model/checkpoint.pth \
      -t test_data \
      -o test_result.json
   ```
4) Use `train.py` for training

## Credits

This repository is based on a heavily modified fork
of [pytorch-template](https://github.com/victoresque/pytorch-template) repository.


## TODO

These barebones can use more tests. We highly encourage students to create pull requests to add more tests / new
functionality. Current demands:

* Tests for beam search
* README section to describe folders
* Notebook to show how to work with `ConfigParser` and `config_parser.init_obj(...)`
