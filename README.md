# Run Jupyter Notebook action for neuro-flow to be used with Neu.ro template

This is a [`neuro-flow`](https://github.com/neuro-inc/neuro-flow) action launching [Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/stable/). It's intended to be used with Neu.ro [platform template](https://github.com/neuro-inc/cookiecutter-neuro-project), but can be adapted for other use cases as well.

It requires image name to run Notebook on as well as references to 5 volumes: data, code, config, notebooks and results, which will be mounted to `/project/data`, `/project/modules`, `/project/config`, `/project/notebooks` and `/project/results` respectively.

After launch web UI open up in default browser automatically.