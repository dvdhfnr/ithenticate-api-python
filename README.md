[<img src="http://www.ithenticate.com/Portals/92785/images/iThenticate_Logo.png" height="75">](http://www.ithenticate.com/)
[<img src="http://go.turnitin.com/l/45292/2015-07-07/37ty9m/45292/77056/turnitin_logo_primary_rgb.png" height="100">](http://turnitin.com/)

# iThenticate API Client Python

This package provides an [iThenticate](http://www.ithenticate.com/) API Client for Python. You may also use this client for a [Turnitin](http://turnitin.com/) account, which uses the iThenticate API.

[![PyPI version](https://badge.fury.io/py/ithenticate-api-python.svg)](https://badge.fury.io/py/ithenticate-api-python)

## Installation ##

The easiest way to install is with [pip](https://pip.pypa.io).
```shell
$ pip install ithenticate-api-python
```

## Getting started ##

Requiring the iThenticate API Client.

```python
>>>> import iThenticate
```

Initializing the iThenticate API client and login.

```python
>>>> client = iThenticate.API.Client('test_username', 'test_password')
>>>> client.login()
True
```

## Method reference ##

### Folders ###

Use the `folders` property is to list and get folders related to your account.

#### List all folders ####
##### `folders.all()` #####

```python
>>>> client.folders.all()
{
  "data": [
    {
      'name': 'My Folder',
      'group': None,
      'id': '1234567'
    }
  ],
  "messages": [],
  "status": 200
}
```

#### Get folder ####
##### `folders.get(folder_id)` #####

```python
>>>> client.folders.get('1234567')
{
  "data": [
    {
      'name': 'My Folder',
      'group': None,
      'id': '1234567'
    }
  ],
  "messages": [],
  "status": 200
}
```

### Documents ###

Use the `documents` property is to all document related methods.

#### Submit a document ####
##### `documents.add(path, folder_id, author_first_name, author_last_name, document_title)` #####
```python
>>>> client.documents.add('/absolute/path/to/document.pdf', '123456', 'John', 'Doe', 'Document Title')
{
  "data": [
    {
      'filename': 'document.pdf',
      'id': '123456'
    }
  ],
  "messages": [
    'Uploaded 1 document successfully'
  ],
  "status": 200
}
```


## License ##
[BSD (Berkeley Software Distribution) License](https://opensource.org/licenses/bsd-license.php).
Copyright (c) 2017, Jorran de Wit.
