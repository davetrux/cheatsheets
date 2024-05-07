# Python Commands

## Create a Virtual Environment

```
python -m venv venv
```

## Activate Virtual Environment

```
source venv/bin/activate
```

## Deactivate Virtual Environment

```
deactivate
```

## pip

### List installed packages

```
pip list
```

### Install packages from requirments

```
pip install -r requirements.txt
```

### Generate detailed requirments.txt
```
pip freeze > requirements.txt
```

### Remove all packages

```
pip freeze | xargs pip uninstall -y
```
For Github packages:
```
pip freeze | cut -d "@" -f1 | xargs pip uninstall -y
```
