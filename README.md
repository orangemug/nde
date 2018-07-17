# nde
A '**n**ode **d**ocker **e**nviroment' so I don't have to run untrusted code outside a container when developing software

[![stability-unstable](https://img.shields.io/badge/stability-unstable-yellow.svg)][stability]

[stability]:   https://github.com/orangemug/stability-badges#unstable


Developing software often requires trying libraries out on your local machine. But you are often running untrusted code which could be doing literally anything. This aims to be a really simple wrapper around docker with no dependencies (other than docker) to run node.js processes.

Features:

 - The first `-p PORT` gets included as an enviroment varaible
 - Gets the node version from your `package.json`
 - Mounts the local directory and `cd`'s to it


## Install
[Install docker](https://www.docker.com/) and copy `nde` to your `bin` directory


## Usage
Install a dependency, code only run inside the container

```
nde npm install semver
```

Run a process

```
nde node hello.js
```

Bind to a port, note that the container will have an enviroment variable `PORT` defined for the first `-p` option defined

```
nde -p 3000 node server.js
nde -p 3000 node -e "console.log('hello world!')"
```

Start a `bash` shell

```
nde
```

Start a `node` shell

```
nde node
```


## License
[MIT](LICENSE)
