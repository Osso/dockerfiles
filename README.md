[Dockerfiles][] for assorted [Gentoo][]-based [Docker][] images.

Dockerfiles are sorted into directories with names matching the
suggested repository.  To avoid duplicating ephemeral data (namespace,
timestamp tag, …), they appear in the `Dockerfile.template` as markers
(`${NAMESPACE}`, `${TAG}`, …).  The `build.sh` script replaces the
markers with values while generating a `Dockerfile` from each
`Dockerfile.template` (using [envsubst][]), and then builds each tag
with:

    $ docker build -t $NAMESPACE/$REPO:$TAG $REPO

for example:

    $ docker build -t osso/gentoo-stage3:20140130 gentoo

The dependency graph is:

    osso/gentoo-stage3  (amd64 stage3)
    `-- gentoo  (adds portage directory)

Run:

    $ ./build.sh

to seed from the Gentoo mirrors and build all images.  There are a
number of variables in the `build.sh` script that configure the build
(`AUTHOR`, `NAMESPACE`, …).  We use [POSIX parameter
expansion][parameter-expansion] to make it easy to override variables
as you see fit.

    $ NAMESPACE=jdoe DATE=20140130 ./build.sh


[Docker]: http://www.docker.io/
[Dockerfiles]: http://www.docker.io/learn/dockerfile/
[Gentoo]: http://www.gentoo.org/
[envsubst]: http://www.gnu.org/software/gettext/manual/html_node/envsubst-Invocation.html
[parameter-expansion]: http://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap02.html#tag_18_06_02
