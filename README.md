# Run a Jupyter Notebook instance

This is a [`neuro-flow`](https://github.com/neuro-inc/neuro-flow) action launching a [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/stable/). It's intended to be used with the Neu.ro [platform template](https://github.com/neuro-inc/cookiecutter-neuro-project), but can be adapted for other use cases as well.

It requires the name of the image on which to run Notebook, as well as references to 5 volumes: data, code, config, notebooks and results. These volumes will be mounted to `/project/data`, `/project/modules`, `/project/config`, `/project/notebooks`, and `/project/results` respectively.

After the Notebook instance is launched, its Web UI will be automatically opened in the default browser.

### Quick example:

```
jobs:
  jupyter:
    action: gh:neuro-actions/jupyter@master
    args:
      image: neuromation/base
      preset: cpu-small
      volumes_data_remote: ${{ volumes.data.remote }}
      volumes_code_remote: ${{ volumes.code.remote }}
      volumes_config_remote: ${{ volumes.config.remote }}
      volumes_notebooks_remote: ${{ volumes.notebooks.remote }}
      volumes_results_remote: ${{ volumes.results.remote }}
```

## Arguments

### `jupyter_mode`

The mode in which to run Jupyter - `"notebook"` or `"lab"`. Uses `"notebook"` by default.

### Example

```
args:
    jupyter_mode: "lab"
```

### `job_name`

Predictable subdomain name which replaces the job's ID in the full job URI. `""` by default.

### Example

```
args:
	job_name: "jupyter-job"
```

### `image`

The name of the image on which to run the Notebook instance.

### Example

```
args:
    image: neuromation/base
```

### `preset`

Resource preset to use when running the Jupyter job.

### Example

```
args:
    preset: cpu-small
```

### `multi_args`

Additional arguments. `""` by default.


### `http_port`

HTTP port to use for Jupyter. `"8888"` by default.

### Example

```
args:
    http_port: "4444"
```

### `http_auth`

Whether to use HTTP authentication for Jupyter or not. `"True"` by default.

### Example

```
args:
    http_auth: "False"
```

### `volumes_data_remote`

Reference to a data volume

### Example

```
args:
	volumes_data_remote: ${{ volumes.data.remote }}
```

### `volumes_code_remote`

Reference to a code volume

### Example

```
args:
	volumes_data_remote: ${{ volumes.code.remote }}
```

### `volumes_config_remote`

Reference to a config volume

### Example

```
args:
	volumes_data_remote: ${{ volumes.config.remote }}
```

### `volumes_notebooks_remote`

Reference to a notebooks volume

### Example

```
args:
	volumes_data_remote: ${{ volumes.notebooks.remote }}
```

### `volumes_results_remote`

Reference to a results volume

### Example

```
args:
	volumes_data_remote: ${{ volumes.results.remote }}
```