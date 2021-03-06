Install 
```
python3 -m venv env
virtualenv venv
source ./venv/bin/activate
pip install -r requirements.txt
```

Run
```
jupyter lab .
```

Add Plotly support to jupyter lab
```
# Avoid "JavaScript heap out of memory" errors during extension installation
# (OS X/Linux)
export NODE_OPTIONS=--max-old-space-size=4096
# (Windows)
set NODE_OPTIONS=--max-old-space-size=4096

# Jupyter widgets extension
jupyter labextension install @jupyter-widgets/jupyterlab-manager@1.1 --no-build

# FigureWidget support
jupyter labextension install plotlywidget@1.5.1 --no-build

# and jupyterlab renderer support
jupyter labextension install jupyterlab-plotly@1.5.1 --no-build

# Build extensions (must be done to activate extensions since --no-build is used above)
jupyter lab build

# Unset NODE_OPTIONS environment variable
# (OS X/Linux)
unset NODE_OPTIONS
# (Windows)
set NODE_OPTIONS=
```

Export

```
jupyter nbconvert overlay.ipynb --to markdown --output overlay.md
```