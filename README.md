# Schema Matching with Large-Language Models

This repository contains artefacts for the paper "Schema Matching with Large Language Models".

## Table of Contents

To generate results and integrate them, you need to run those notebooks in order:
* `generate_` notebooks to generate the results. Note that these notebooks use a tool `fm_matcher` that is not included in this repository, yet. This is why we include the results in the `results` folder.
* `integration_decisions.ipynb` to integrate the results (`all_decisions_df.csv`)

Afterwards, the integrated decisions can be analyzed with any of the remaining notebooks.
* `benchmark_overview.ipynb` gives an overview of the datasets and the ground truth
* `quality_` notebooks generate the results with regard to (median) results quality
* `complementarity_` notebooks investigate (average) results when combining two prompting approaches

### benchmark

Under `benchmark`, you can find the ground truth of matches that we aim to find using LLMs. In the `ground_truth.csv` file, each line corresponds to a match. `type` defines the type of match (currently only `one_to_one`), `source` is the full qualified name of the source attribute, `relationship` is currently always `corresponds`, and `target` is the full qualified name of the target attribute.

### results

`results` contain our experimental results. `gpt35_results.csv`, `gpt4_results.csv` and `baseline_results.csv` contain the actual votes per attribute pair; `all_decisions_df.csv` is an integrated version of the three files where majority voting has been applied.

### schema\_documentations

The `schema_docuemntations` folder contains the relation and attribute descriptions we used for our experiments. The MIMIC desciptions are scraped from the [MIMIC-IV documentation](https://mimic.mit.edu/docs/iv/modules/hosp/), the OMOP documentations stems from the [OMOP CDM documentation](https://ohdsi.github.io/CommonDataModel/cdm53.html). Refer to the corresponding documentation sites for more information and their publication licenses.

### templates

The prompt templates that we applied to generate prompts for our experiments, in JSON format.

## Requirements

Dependencies are listed in `requirements.txt`. Install them via `pip install -r requirements.txt`.

