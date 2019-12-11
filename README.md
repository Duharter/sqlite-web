`sqlite-web` is a web-based SQLite database browser written in Python.

### Installation

```sh
$ pip install sqlite-web
```

### Usage

```sh
$ sqlite_web /path/to/database.db
```

### Command-line options

The syntax for invoking sqlite-web is:

```console

$ sqlite_web [options] /path/to/database-file.db
```

The following options are available:

* ``-p``, ``--port``: default is 8080
* ``-H``, ``--host``: default is 127.0.0.1
* ``-d``, ``--debug``: default is false
* ``-x``, ``--no-browser``: do not open a web-browser when sqlite-web starts.
* ``-P``, ``--password``: prompt for password to access sqlite-web.
  Alternatively, the password can be stored in the "SQLITE_WEB_PASSWORD"
  environment variable, in which case the application will not prompt for a
  password, but will use the value from the environment.
* ``-r``, ``--read-only``: open database in read-only mode.
* ``-u``, ``--url-prefix``: URL prefix for application, e.g. "/sqlite-web".

### Using docker

A Dockerfile is provided with sqlite-web. To use:

```console

$ cd docker/  # Change dirs to the dir containing Dockerfile
$ docker build -t coleifer/sqlite-web .
$ docker run -it --rm \
    -p 8080:8080 \
    -v /path/to/your-data:/data \
    -e SQLITE_DATABASE=db_filename.db \
    coleifer/sqlite-web
```
