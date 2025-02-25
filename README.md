# pyNextcloud

`pyNextcloud` is a Python library for interacting with Nextcloud via WebDAV. It provides functions to upload, download, rename, delete files and directories, and check for directory existence.

## Features

- Upload files and folders to Nextcloud
- Download files from Nextcloud
- Rename or move files and directories
- Delete files and directories
- Check if a directory exists
- Configuration using environment variables or a `.env` file

## Installation

To install `pyNextcloud`, use pip:

```bash
pip install pyNextcloud
```

## Configuration

To store the `NEXTCLOUD_URL`, `USERNAME`, and `PASSWORD` securely in your library, you can make use of environment variables or a configuration file to keep them safe and accessible in your app. Here's how you can do both:

### 1. **Using Environment Variables** (Recommended for security)

You can store these sensitive values in environment variables, so they aren't hardcoded in your source code.

#### Steps:

- Set up environment variables on your system or in your deployment environment:
  - On Unix/Linux/Mac:
    ```bash
    export NEXTCLOUD_URL="your_nextcloud_url"
    export USERNAME="your_username"
    export PASSWORD="your_password"
    ```

  - On Windows:
    ```cmd
    set NEXTCLOUD_URL="your_nextcloud_url"
    set USERNAME="your_username"
    set PASSWORD="your_password"
    ```

### 2. **Using a Configuration File** (Not as secure as environment variables)

If you'd rather use a configuration file, you can store them in a `.env` or JSON file.

#### `.env` File Example:

- Create a `.env` file:
  ```
  NEXTCLOUD_URL=your_nextcloud_url
  USERNAME=your_username
  PASSWORD=your_password
  ```

## Usage

### Upload a File

```python
from pyNextcloud.nextcloud import UploadFile

UploadFile('local_path.txt', 'remote_path.txt')
```

### Download a File

```python
from pyNextcloud.nextcloud import DownloadFile

DownloadFile('local_path.txt', 'remote_path.txt')
```

### Check if a Directory Exists

```python
from pyNextcloud.nextcloud import DirectoryExists_Check

result = DirectoryExists_Check('remote_directory')
print(result)
```

### Create a Directory

```python
from pyNextcloud.nextcloud import CreateDirectory

result = CreateDirectory('new_directory')
print(result)
```

### Rename or Move a File/Directory

```python
from pyNextcloud.nextcloud import RenamePath

result = RenamePath('current_path.txt', 'new_path.txt')
print(result)
```

### Delete a File/Directory

```python
from pyNextcloud.nextcloud import DeletePath

result = DeletePath('target_path.txt')
print(result)
```

### Upload a Folder

```python
from pyNextcloud.nextcloud import UploadFolder

result = UploadFolder('local_folder', 'remote_folder')
print(result)
```

## Running Tests

To run the tests, use the following command:

```bash
python -m unittest discover -s tests
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes.

## Acknowledgements

- [Nextcloud](https://nextcloud.com/) for providing the WebDAV interface.
- [Requests](https://docs.python-requests.org/en/master/) for making HTTP requests simple.
- [python-dotenv](https://github.com/theskumar/python-dotenv) for managing environment variables.