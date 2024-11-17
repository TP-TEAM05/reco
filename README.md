# 🚗 ReCo Polyrepository ☁️

`git clone --recursive --remote-submodules git@github.com:ReCoFIIT/reco.git`

## Updating Integration API

Go to `integration-api` and modify the structure of the API. Then push the changes to the `integration-api` repository.

In Github Create a new release and tag it with the version number. The version number should be in the format `vX.Y.Z` where `X`, `Y`, and `Z` are integers.
We are using [Semantic Versioning](https://semver.org/).

In projects that use the `integration-api` update the package:

```bash
go get -u github.com/ReCoFIIT/integration-api@vX.Y.Z
```

Rebuild the project container

```bash
docker-compose up -d --build <project_name>
```

## Using Golang private packages

- Create a personal access token on GitHub
- Add the following to your `~/.bashrc` or `~/.zshrc`:

```bash
export GOPRIVATE="github.com/ReCoFIIT"
```

If you have multiple private repositories, separate them with a comma:

```bash
export GOPRIVATE="github.com/ReCoFIIT,github.com/your-other-repo"
```

- Run `source ~/.bashrc` or `source ~/.zshrc`
- In `.gitconfig` add the following:

```bash
[url "ssh://git@github.com/"]
 insteadOf = https://github.com/
```

- create a file `~/.netrc` with the following content:

```bash
machine github.com
login <your-github-username>
password <your-github-token>
```
