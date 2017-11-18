# ports

Various MacPorts that aren't in the main ports tree.

## Usage

1. Clone the repo:
    - ` git clone git@github.com:ajm188/ports.git /some/local/path`
1. Edit your sources.conf (usually /opt/local/etc/soures.conf) to include the path to your local checkout, like so:
    - `file:///some/local/path`

## Contributing

You are responsible for maintaining any ports that you add to this tree.
To add a port, add a Portfile to your repository, following [this guide][portfile_dev].
Then, submit a pull request which adds your repository as a submodule.
Note that for MacPorts to work correctly, your submodule should be inside a directory that matches the main category of your port.
So, if your port's main category is "devel", you would do:

```bash
$ mkdir -p devel
$ git submodule add git@github.com/myuser/my-port devel/my-port
$ git add .gitmodules
$ git commit
```

### Updating your port

If your port has had a new release and needs to be updated in the tree, first change the Portfile in your port's repository.
Then, submit a pull request to this repository that updates the submodule to the appropriate commit.

```bash
$ cd my-category/my-port
$ git checkout new-commit
$ cd -
$ git add my-category/my-port
$ git commit
```

[portfile_dev]: https://guide.macports.org/chunked/development.html
