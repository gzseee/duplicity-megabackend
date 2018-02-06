# Duplicity megabackend

THIS WAS ADDRESSED IN Duplicity 0.7.15. USE UPDATED VERSION INSTEAD.

This repository contains slightly modified megabackend implementation from Duplicity
[Bug #1394386](https://bugs.launchpad.net/duplicity/+bug/1394386), attached
by Tomas Vondra (tomas-v). Original file can be downloaded from
[Launchpad](https://bugs.launchpad.net/duplicity/+bug/1394386/+attachment/4813806/+files/megabackend.py).

This implementation of megabackend should be used only with Duplicity versions before
0.7.13. Then the megabackend should work out of the box.

If you can, then use Duplicity 0.7.15 or above. Note that this release was not
available at the time this repository was created.

## Installation

If you decided to use this implementation, then feel free to just replace the
megabackend implementation in your current Duplicity installation.

On typical Ubuntu installation, with Duplicity from packages, you can do
something like:

```bash
sudo apt install git megatools
cd /usr/lib/python2.7/dist-packages/duplicity/backends
cp megabackend.py megabackend.py.bak
cd /tmp
git clone git@github.com:gzseee/duplicity-megabackend.git
cd duplicity-megabackend
cp megabackend.py /usr/lib/python2.7/dist-packages/duplicity/backends/megabackend.py
cd /tmp && rm -rf duplicity-megabackend
```

## Practical experience

The backend is not perfect and it may hang during large backups. Due to that it
might not be the best solution for production deployment.

Use at your own risk.
