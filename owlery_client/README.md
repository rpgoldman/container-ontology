# owlery-client
Owlery provides a web API for an [OWL API](http://owlapi.sourceforge.net)-based reasoner containing a configurable set of ontologies (a \"knowledgebase\"). 

This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen

## Requirements.

Python >= 3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/GIT_USER_ID/GIT_REPO_ID.git`)

Then import the package:
```python
import owlery_client
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import owlery_client
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import owlery_client
from pprint import pprint
from owlery_client.api import dl_queries_api
from owlery_client.model.inline_response200 import InlineResponse200
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = owlery_client.Configuration(
    host = "http://localhost"
)



# Enter a context with an instance of the API client
with owlery_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = dl_queries_api.DLQueriesApi(api_client)
    kb = "uberon" # str | label for a knowledgebase in this Owlery
object = "<http://purl.obolibrary.org/obo/UBERON_0002101>" # str | Manchester-syntax OWL class expression
prefixes = "{"obo": "http://purl.obolibrary.org/obo/", "part_of": "http://purl.obolibrary.org/obo/BFO_0000050"}" # str | JSON format prefix map, used to expand prefixes in the 'object' expression (optional)
direct = True # bool |  (optional) (default to True)
include_deprecated = True # bool | Include `owl:deprecated` terms in the result (optional) (default to True)

    try:
        # Equivalent classes
        api_instance.kbs_kb_equivalent_get(kb, object, prefixes=prefixes, direct=direct, include_deprecated=include_deprecated)
    except owlery_client.ApiException as e:
        print("Exception when calling DLQueriesApi->kbs_kb_equivalent_get: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*DLQueriesApi* | [**kbs_kb_equivalent_get**](docs/DLQueriesApi.md#kbs_kb_equivalent_get) | **GET** /kbs/{kb}/equivalent | Equivalent classes
*DLQueriesApi* | [**kbs_kb_instances_get**](docs/DLQueriesApi.md#kbs_kb_instances_get) | **GET** /kbs/{kb}/instances | Instances
*DLQueriesApi* | [**kbs_kb_satisfiable_get**](docs/DLQueriesApi.md#kbs_kb_satisfiable_get) | **GET** /kbs/{kb}/satisfiable | Satisfiability
*DLQueriesApi* | [**kbs_kb_subclasses_get**](docs/DLQueriesApi.md#kbs_kb_subclasses_get) | **GET** /kbs/{kb}/subclasses | Subclasses
*DLQueriesApi* | [**kbs_kb_superclasses_get**](docs/DLQueriesApi.md#kbs_kb_superclasses_get) | **GET** /kbs/{kb}/superclasses | Superclasses
*DLQueriesApi* | [**kbs_kb_types_get**](docs/DLQueriesApi.md#kbs_kb_types_get) | **GET** /kbs/{kb}/types | Types
*KnowledgebasesApi* | [**kbs_get**](docs/KnowledgebasesApi.md#kbs_get) | **GET** /kbs | List available knowledgebases
*KnowledgebasesApi* | [**kbs_kb_get**](docs/KnowledgebasesApi.md#kbs_kb_get) | **GET** /kbs/{kb} | Knowledgebase
*SPARQLApi* | [**kbs_kb_expand_get**](docs/SPARQLApi.md#kbs_kb_expand_get) | **GET** /kbs/{kb}/expand | Expand SPARQL query encoded in URL parameter
*SPARQLApi* | [**kbs_kb_expand_post**](docs/SPARQLApi.md#kbs_kb_expand_post) | **POST** /kbs/{kb}/expand | Expand SPARQL query contained in request body
*SPARQLApi* | [**kbs_kb_sparql_get**](docs/SPARQLApi.md#kbs_kb_sparql_get) | **GET** /kbs/{kb}/sparql | Perform SPARQL query encoded in URL parameter
*SPARQLApi* | [**kbs_kb_sparql_post**](docs/SPARQLApi.md#kbs_kb_sparql_post) | **POST** /kbs/{kb}/sparql | Perform SPARQL query contained in request body


## Documentation For Models

 - [InlineResponse200](docs/InlineResponse200.md)


## Documentation For Authorization

 All endpoints do not require authorization.

## Author

balhoff@renci.org


## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in owlery_client.apis and owlery_client.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from owlery_client.api.default_api import DefaultApi`
- `from owlery_client.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import owlery_client
from owlery_client.apis import *
from owlery_client.models import *
```
