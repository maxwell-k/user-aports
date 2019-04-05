# Building locally

1.  Enter a new Alpine Linux "chroot", with Ansible installed and acquire root
2.  Clone this repository to "/builds/keith.maxwell/aports-local" and move there
    ```
    mkdir /builds /builds/keith.maxwell /builds/keith.maxwell/aports-local &&
    cd /builds/keith.maxwell/aports-local &&
    git clone git@gitlab.com:keith.maxwell/aports-local .
    ```
3.  Add the private key as "keith.maxwell@gmail.com-5a1151a5.rsa"
4.  Install build tools and add user with:
    `ansible-playbook -i localhost, ./site.yaml`
5.  Match the ID of the "abuild" user inside this "chroot" to the
    user configured for commits: `vim /etc/passwd`
6.  Change the owner of the checked out repository to "abuild:abuild" and
    `chown -R abuild:abuild /builds/keith.maxwell/aports-local`
7.  Build with `su abuild -c 'buildrepo local'`

# Manual steps

First move to the directory containing the "APKBUILD" then change
to the "abuild" user with `sudo -iu abuild`, then complete each step below using
`abuild <step>`:

```
1   checksum
2   deps
3   unpack
4   prepare
5   build
6   check
7   rootpkg
8   undeps
```

Running `abuild -r` with run through the whole process:

- `abuild` without any arguments runs through all of the stages and
- `-r` will install dependencies as required

# Main repository

To get a copy of the main Alpine Linux repository use:

```
git clone --depth 1 git://git.alpinelinux.org/aports
```

# Resources

A [sample](https://git.alpinelinux.org/cgit/abuild/log/sample.APKBUILD)
"APKBUILD" is available:

```sh
curl -o APKBUILD \
    https://git.alpinelinux.org/cgit/abuild/plain/sample.APKBUILD
```

The ["APKBUILD Reference"](https://wiki.alpinelinux.org/wiki/APKBUILD_Reference)
is a wiki page.

The default functions can be seen in
["abuild.in"](https://github.com/alpinelinux/abuild/blob/master/abuild.in).

<https://repology.org> links for new versions:

-   ["ansible-lint"](https://repology.org/metapackage/ansible-lint/information)
-   ["beancount"](https://repology.org/metapackage/beancount/information)
-   ["dash"](https://repology.org/metapackage/dash/information)
-   ["isync"](https://repology.org/metapackage/isync/information)
-   ["jbig2enc"](https://repology.org/metapackage/jbig2enc/information)
-   ["py-ply"](https://repology.org/metapackage/python:ply/information)
-   ["sane-backend-canon_dr"](https://repology.org/metapackage/sane-backends/information)
-   ["sane-frontends"](https://repology.org/metapackage/sane-frontends/information)
    which incorrectly shows that a more recent version number, matching
    "sane-backends", is available
-   "sasl2-oath" has zero releases

```sh
ls -1 aports/local | sed 's/.*/`\0 <>`__/'
grep -H pkgver= ./aports/local/*/APKBUILD
```
