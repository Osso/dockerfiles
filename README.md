[Dockerfiles][] for assorted [Ubuntu][]-based [Docker][] images.

Dockerfiles are sorted into directories with names matching their function.
To avoid duplication all images extend base which defines the maintainer
and contains updated packages. The `Makefile` script builds each tag
with:

    $ docker build -t $image_name .

for example:

    $ docker build -t smartmontools .

The dependency graph is:

    base  (ubuntu,amd64)
    `-- smartmontools  (disks monitoring)

Run:

    $ make

to build all images.

[Docker]: http://www.docker.io/
[Dockerfiles]: http://www.docker.io/learn/dockerfile/
