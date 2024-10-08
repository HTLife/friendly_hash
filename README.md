# friendly_hash

A tool to rename files with human-readable hashes.

## Installation

```sh
pip3 install friendly_hash
```

add `export PATH=$PATH:~/.local/bin` to your .bashrc or .zshrc

## Usage

To show the resulting filename:
```sh
friendly_hash 2024-07-05-09-15-18.bag
# peaceful-week-2024-07-05-09-15-18.bag
```

To actually rename the file:
```sh
friendly_hash -f 2024-07-05-09-15-18.bag
# peaceful-week-2024-07-05-09-15-18.bag
```

## For Developer

1. **Install the package**:
    ```sh
    pip3 install -r requirements.txt
    pip3 install .
    ```
2. **Run the script** to show the resulting filename:
    ```sh
    friendly_hash 2024-07-05-09-15-18.bag
    ```
3. **Run the script** to rename the file:
    ```sh
    friendly_hash -f 2024-07-05-09-15-18.bag
    ```

4. **Run tests**:
    ```sh
    python -m unittest discover
    ```
 5. **Build Package**:
    ```sh
    pip3 install setuptools wheel
    python3 setup.py sdist bdist_wheel
    pip3 install twine
    twine upload dist/*
    ```

6. Update version

    ```sh
    rm dist/*
    pip wheel . --wheel-dir dist/ --no-deps && pip install dist/*.whl 
    ```

    # pypi upload method 1 - poetry
    ```
    curl -sSL https://install.python-poetry.org | python3 -
    poetry self add poetry-version-plugin
    poetry build
    poetry publish
    ```

    ```bash
    # use this to replace the mis-uploaded version
    poetry publish --skip-existing
    ```
    # pypi upload method 2 - twine
    ```
    twine upload dist/*
    ```