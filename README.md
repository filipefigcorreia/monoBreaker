# MonoBreaker

MonoBreaker is a Python program for breaking Django Monoliths.

## Requirements

MonoBreaker has been tested with:

    Django: 1.11, 2.0, 2.1, 2.2
    Python: 3.6, 3.7


## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install MonoBreaker Dependencies.

```bash
pip install -r requirements.txt
```
In your Django Project use [django_extensions](https://github.com/django-extensions/django-extensions) and [Silk](https://github.com/jazzband/django-silk)  

Your `settings.py` should look like the following:
```python
MIDDLEWARE = [
    ...,
    'silk.middleware.SilkyMiddleware',
    ...
]

INSTALLED_APPS = (
    ...
    'rest_framework',
    'django_extensions',
    'silk'
)
```

## Usage

Extract data and models information to the source folder of you Django Project:
```python
python manage.py graph_models app_1 app_2 --json > models.json
python manage.py show_urls > urls.txt
```

Run MonoBreaker:
```python
Usage: python monoBreaker.py [options]

Options:
  -h, --help           show this help message and exit
  --pydir=PYDIR        Path to Django Project

```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.


## License
[MIT](https://choosealicense.com/licenses/mit/)
