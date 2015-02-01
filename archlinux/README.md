# Arch Linux Docker Base Image

Stolen from https://github.com/docker/docker/blob/master/contrib/mkimage-arch.sh

## Building

Before building, make sure `/var/lib/docker` is on a good file system (i.e.
symlinked to `/mnt/raid/docker`)

As root:

```
TMPDIR=/mnt/raid/shorty/temp ./mkimage-arch.sh
```

... and then clean up `$TMPDIR`

## Changes from the stolen script

1. Changed tag from `archlinux` to `porty/archlinux`
1. Uses local Arch mirror
