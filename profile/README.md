# HAICCing

Projects you can run, and the packages they need, ready to run. Everything
is managed with the HAICC tool, which declares what a project needs, checks it, and
makes it so.

HAICC stands for human-AI creative collaboration: the way the
[SPLectrum](https://splectrum.world) project is made, and now also the name of
the platform built that way, with AI autonomy in mind. A project here is a
whole: a swarm of nodes in containers, SPLectral to see it run, and what it is
meant to show. The two demos are the first: a node goes quiet and the swarm
notices; a node joins from another host by invitation.

## Start here

Linux on x86-64 (on Windows: inside WSL2), with `curl` and `tar`:

```sh
rm -f haicc-setup.sh && curl -fL --progress-bar --retry 5 --retry-all-errors --connect-timeout 20 \
     -o haicc-setup.sh https://github.com/haiccing/base-package-haicc/releases/latest/download/haicc-setup.sh \
  && sh haicc-setup.sh ~/haicc-work \
  && ~/haicc-work/boot \
  && cd ~/haicc-work && ./haicc list
```

One command: it stops at the first step that fails (a failed download included).
The setup is about 39 MB (it carries Bare's runtime). On a poor connection: if the download stops, `curl -fL -C - -o haicc-setup.sh https://github.com/haiccing/base-package-haicc/releases/latest/download/haicc-setup.sh` continues it where it stopped; run it again until it ends without an error, then `sh haicc-setup.sh ~/haicc-work && ~/haicc-work/boot`.

The setup carries everything HAICC runs on (Bare's runtime included: nothing
to download). The boot checks git and Docker Engine, and fixes what is missing
only with your yes. Everything stays in the work folder, in plain sight.
Everything it does is logged in the work folder's `log/` (`~/haicc-work/log/`): files named by their start, newest last.
Running the projects from there is the next step.

Part of the engineering of [SPLectrum](https://splectrum.world).
