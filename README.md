# Journify Python SDK
The official python client for [Journify](https://journify.io) — The hassle-free way to integrate Journify into any Python application.

## Installation
```sh
pip install journify-python-sdk
```

## Usage
```python
import journify as journify

def on_journify_error(error, items):
    print("A Journify error occurred:", error)

journify.debug = True
journify.on_error = on_journify_error
journify.write_key = '<YOUR_WRITE_KEY>'

journify.identify('user-123-id', {
    'email': 'john@example.com',
    'name': 'John Smith',
})

journify.track('user-123-id', 'Python event', {
  'plan': 'Enterprise'
})

journify.page('user_id', 'Page category', 'Page name', {
  'url': 'http://journify.io'
})

journify.group('user_id', 'group_id', {
  'name': 'Initech',
  'domain': 'Accounting Software'
})
```

## Documentation
Documentation is available at [https://docs.journify.io/sources/python-sdk](https://docs.journify.io/sources/python-sdk).

# Contributing
You can contribute to Journify Python SDK by forking the repo and making pull requests on the `master` branch.

To publish a new version, you need to add a prefix to your pull request title following the [semantic versioning spec](https://semver.org/):
* **[MAJOR]** \{Pull request title\}
* **[MINOR]** \{Pull request title\}
* **[PATCH]** \{Pull request title\}

Once your PR is merged and the CI pipeline is passed, your code will be published to npm.