# Installation
## osx
#### via [Homebrew](https://brew.sh)
1. Add tap

```bash
brew tap hekmekk/git-team
```

2. Install git-team

Install stable release. Use `--HEAD` in case you want to install from the latest commit.
```bash
brew install git-team
```

## deb
#### via [bintray](https://bintray.com)
1. Add bintray GPG Key
```bash
curl -fsSL https://bintray.com/user/downloadSubjectPublicKey?username=bintray | sudo apt-key add -
```

2. Setup the `apt` repository
```bash
echo "deb [arch=amd64] https://dl.bintray.com/hekmekk/git-team $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/git-team.list
```

3. Update the `apt` package index and install `git-team`
```bash
sudo apt update && sudo apt install git-team
```

#### via [apt-sourc.es](https://apt-sourc.es)
1. Add *apt-sourc.es* GPG Key
```bash
curl -fsSL https://apt-sourc.es/admin/gpg.asc | sudo apt-key add -
```

2. Setup the `apt` repository
```bash
echo "deb [arch=amd64] https://apt-sourc.es/deb/hekmekk/git-team stable main" | sudo tee /etc/apt/sources.list.d/git-team.list
```

3. Update the `apt` package index and install `git-team`
```bash
sudo apt update && sudo apt install git-team
```

#### via an [ansible playbook](../master/contrib/ansible/roles/git-team/tasks/main.yml)
```
ansible-playbook git-team.yml --ask-become-pass
```

## rpm
1. Add bintray GPG Key
```bash
echo "`curl -fsSL https://bintray.com/user/downloadSubjectPublicKey?username=bintray`" > /tmp/bintray-public.key.asc && sudo rpm --import /tmp/bintray-public.key.asc && rm -f /tmp/bintray-public.key.asc
```

2. Setup the `yum` repository

Note: Automatic signing of packages during upload doesn't seem to work for `.rpm` files. Set `gpgcheck=0` as a workaround.

```bash
echo "[git-team]
name=git-team
baseurl=https://dl.bintray.com/hekmekk/git-team-rpm
gpgcheck=1
enabled=1" | sudo tee /etc/yum.repos.d/git-team.repo
```

3. Install `git-team`
```bash
sudo yum install git-team
```

## Manually
#### Download a Release
1. Download the [latest release](https://github.com/hekmekk/git-team/releases/latest)

2. Install it manually
```bash
sudo dpkg -i /path/to/downloaded/release.deb
```

#### Build from Source
The latest version of git-team has been built against go version 1.12.
```bash
make
sudo make install
```
