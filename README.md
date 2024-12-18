# NL2SQL
NL2SQL and METASQL Implementation of Group 12

## :dizzy:Overview

**NL2SQL360** is a testbed for fine-grained evaluation of NL2SQL solutions. Our testbed integrates existing NL2SQL benchmarks, a repository of NL2SQL models, and various evaluation metrics, which aims to provide an intuitive and user-friendly platform to enable both standard and customized performance evaluations. Users can utilize **NL2SQL360** to assess different NL2SQL methods against established benchmarks or tailor their evaluations based on specific criteria. This flexibility allows for testing solutions in specific data domains or analyzing performance on different characteristics of SQL queries. **SuperSQL** is experimented to compare performance on the Spider test set.


## :wrench:Installation

```bash
pip install nl2sql360
```

## :rocket:Quick Start

<details><summary>Prepare Dataset</summary>

Download NL2SQL dataset to `DATASET_DIR_PATH`. The directory structure should be like:
```bash
DATASET_DIR_PATH:
├─database
│  ├─academic
│  │  ├─academic.sqlite
│  ├─college
│  │  ├─college.sqlite
├─dev.json
├─tables.json
```

- `database` directory contains multiple subdirectories, which include the corresponding `sqlite` database file.
- `dev.json` is the samples file in JSON format, which at least contains three keys for `NL Question`, `Gold SQL`, `Databae Id`. You can also add the key for `Sample Complexity` for categorizing samples into different difficulty levels.
- `tables.json` contains all database schema, following [Spider Preprocess Procedure](https://github.com/taoyds/spider/tree/master/preprocess). **You can also ignore this file if you do not want to evaluate Exact-Match Accuracy Metic.**
- Note that the name for `database` directory, samples file `dev.json` and tables file `tables.json` can be changed.

</details>

<details><summary>Import Dataset into NL2SQL360</summary>

- CLI Usage:

  - Create / Modify the YAML configuration following [NL2SQL360/examples/cli_examples/dataset_spider.yaml](https://github.com/HKUSTDial/NL2SQL360/blob/master/examples/cli_examples/dataset_spider.yaml).

  - Save the YAML file to the path `DATASET_YAML_PATH`. Then run the command line:

    ```bash
    nl2sql360-cli dataset DATASET_YAML_PATH
    ```

- Code Usage:

  - Create / Modify Python File following [NL2SQL360/examples/py_examples/dataset_import.py](https://github.com/HKUSTDial/NL2SQL360/blob/master/examples/py_examples/dataset_import.py).
  - Run the python file to import dataset.

</details>

<details><summary>Evaluation NL2SQL Model</summary>

- CLI Usage:

  - Create / Modify the YAML configuration following [NL2SQL360/examples/cli_examples/evaluation.yaml](https://github.com/HKUSTDial/NL2SQL360/blob/master/examples/cli_examples/evaluation.yaml).

  - Save the YAML file to the path `DATASET_YAML_PATH`. Then run the command line:

    ```bash
    nl2sql360-cli evaluate DATASET_YAML_PATH
    ```

- Code Usage:

  - Create / Modify Python File following [NL2SQL360/examples/py_examples/evaluation.py](https://github.com/HKUSTDial/NL2SQL360/blob/master/examples/py_examples/evaluation.py).
  - Run the python file to evaluate the model.

</details>

<details><summary>Query Multi-angle Performance</summary>

- CLI Usage:

  - Create / Modify the YAML configuration following [NL2SQL360/examples/cli_examples/report.yaml](https://github.com/HKUSTDial/NL2SQL360/blob/master/examples/cli_examples/report.yaml).

  - Save the YAML file to the path `DATASET_YAML_PATH`. Then run the command line:

    ```bash
    nl2sql360-cli report DATASET_YAML_PATH
    ```

  - The generated report will be in `save_path` specified in the YAML file.

- Code Usage:
  - Create / Modify Python File following [NL2SQL360/examples/py_examples/report.py](https://github.com/HKUSTDial/NL2SQL360/blob/master/examples/py_examples/report.py).
  - Run the python file to generate report.

</details>

<details><summary>Delete History Cache</summary>

- CLI Usage:

  - Create / Modify the YAML configuration following [NL2SQL360/examples/cli_examples/delete_history.yaml](https://github.com/HKUSTDial/NL2SQL360/blob/master/examples/cli_examples/delete_history.yaml).

  - Save the YAML file to the path `DATASET_YAML_PATH`. Then run the command line:

    ```bash
    nl2sql360-cli delete DATASET_YAML_PATH
    ```

- Code Usage:

  - Create / Modify Python File following [NL2SQL360/examples/py_examples/delete_history.py](https://github.com/HKUSTDial/NL2SQL360/blob/master/examples/py_examples/delete_history.py).
  - Run the python file to delete dataset / evaluation cache.

</details>


## :floppy_disk:Experiment Data

We have released all experiment data used in our paper.

[Download Link](https://drive.google.com/drive/folders/1SDwY30H2r6XNYeS53wcZNocVFm0hVgpz?usp=sharing)
