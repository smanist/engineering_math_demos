# Visualized Demos for Engineering Mathematics

Developed for `AERSP 313` Aerospace Analysis at the Pennsylvania State University.

**Under development for Fall 2022.**

The Jupyter-based web application is generated using [Mercury](https://mljar.com/mercury/) and hosted on [Heroku](https://aersp313.herokuapp.com).

## To directly play with Jupyter notebook
Just download the `ipynb` file and run it on your computer.  Make sure to install the Python environment and the Jupyter package.  For first-time users, the easiest way to start is to install [Anaconda](https://www.anaconda.com/).

## Workflow for developers
0. Installation
   + Follow the guide [here](https://devcenter.heroku.com/articles/heroku-cli) to install Heroku CLI tools.
   + Then [here](https://github.com/mljar/mercury) to install Mercury CLI tools.  Make sure `mercury` is in `PATH`.
   + Clone the current repo.
1. Develop the Jupyter notebook application locally, with the file in the root path.  One can check the web application locally by
   ```
   mercury watch <path_to_your_notebook>
   ```
   To delete the notebook,
   ```
   mercury delete <path_to_your_notebook>
   ```
   If `CTRL+C` does not kill the Django server, on Mac one can use
   ```
   sudo lsof -t -i tcp:8000 | xargs kill -9
   ```
   If done with the local edits, commit and push to **the current repo**.
2. If everything looks good, one can push to the Heroku website
   ```
   git push heroku <branch_name>
   ```
   The branch name for the current repo is `master`, instead of `main` as suggested by some Mercury documentation.
3. If a library/driver is not available on Heroku, it typically can be added via `settings/buildpack` of the app.