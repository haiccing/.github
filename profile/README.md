# HAICCing

The packages of the HAICC platform, ready to run, and the `haicc` command
that runs them. Each package is one bundle, run with
[Bare](https://github.com/holepunchto/bare), tested from that bundle, its
test report inside it.

HAICC stands for human-AI creative collaboration: the way the
[SPLectrum](https://splectrum.world) project is made, and now also the name of
the platform built that way, with AI autonomy in mind. An install is a boot
mrepo, a repository that runs, on your machine, with mrepos deployed beside
and below it: a host, a swarm's nodes, each node's replica in a Docker
container, and SPLectral to watch it in a browser. Everything is done with
`haicc`, and every command is a request, recorded with its log.

## Start here

Linux on x86-64 (on Windows: inside WSL2), with `curl`, `tar` and
`sha256sum`, and Docker for the nodes' containers. The command and the
packages install from their releases here:

```sh
curl -fsSLO https://github.com/haiccing/base-linux-haicc/releases/latest/download/haicc-install.sh
sh haicc-install.sh
haicc sources download bare haiccing
haicc prereq                        # every line ok
```

Then from nothing to a running cluster, with SPLectral showing it:

```sh
haicc boot/deploy
haicc . boot/deploy splectral base-package-splectral --flags continuation=start
haicc splectral splectral/status    # the page's address: http://127.0.0.1:4400
haicc . boot/deploy host base-component-haicc --flags continuation=cluster
haicc host howto                    # what can be done here
haicc boot/teardown                 # everything stopped and removed
```

`haicc --help` lists the commands. The repositories here named `base-demo-`
and `base-swarm-`, and `base-package-pkgm`, `-p2p` and `-third-party`, are of
the earlier platform and do not run on this one.

## The five organisations

SPLectrum's engineering is spread over five GitHub organisations:

- **[splectrum](https://github.com/splectrum)**: where SPLectrum, the
  philosophy project, lives, and where its engineering is planned.
- **[bare-for-pear](https://github.com/bare-for-pear)**: outside code
  changed to run on Bare. It rests until the platform needs it.
- **[pear-full-square](https://github.com/pear-full-square)**: the engines,
  all of the platform's code, one module a repository.
- **[HAICCing](https://github.com/haiccing)** (this one): the packages made from those
  modules, and the `haicc` command: what you can run. Start here.
- **[SPLectral](https://github.com/splectral)**: components for seeing and
  working with running systems in the browser.

Part of the engineering of [SPLectrum](https://splectrum.world).
