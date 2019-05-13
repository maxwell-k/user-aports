# 'user-aports'

Extra packages for Alpine Linux published to GitLab pages.

Building these packages has been tested:

1. Manually
2. Locally using "gitlab-runner" and the shell executor
3. Remotely using the CI on <https://gitlab.com>

## Building everything

### Manually

1. New Alpine Linux "chroot" with SSH keys, Ansible and git available
1. Clone this repository to "~/aports/":
   `git clone git@gitlab.com:keith.maxwell/user-aports.git ~/aports`
1. Add the current user to the "abuild" group:
   `sudo adduser chronos abuild && exec sudo -iu "$LOGNAME"`
1. Run the shared configuration:
   `cd ~/aports && ansible-playbook -i , site.yaml`
1. Set 'PACKAGER_PRIVKEY' to the private key in '/etc/abuild.conf':
   `sudo vim /etc/abuild.conf`
1. Add the corresponding public key to "/etc/apk/keys"
1. Build everything: `buildrepo user`
1. Packages are in `~/packages`

### Locally using "gitlab-runner" and the shell executor

Complete the manual steps above and then:

1. Manually install `gitlab-runner` onto `$PATH`
1. Install any unmet dependencies like bash: `sudo apk add bash`
1. Build everything: `gitlab-runner exec shell build`
1. Packages are in `./builds/0/project-0/public`

## Checking

Before submitting packages upstream run `abuild sanitycheck`. To also check the
value of the licence variable, make sure `spdx-licenses-list` is installed.

## Debugging

First move to the directory containing the "APKBUILD" then change to the
"abuild" user with `sudo -iu abuild`, then complete each step below using
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

Running `abuild -r` will run through the whole process:

- `abuild` without any arguments runs through all of the stages and
- `-r` will install dependencies as required

## Resources

To get a copy of the main Alpine Linux repository use:

```
git clone --depth 1 git://git.alpinelinux.org/aports
```

The "abuild" repository includes a [sample] "APKBUILD" nd the The [Python
package policies wiki page] includes two sample "APKBUILD"s.

[sample]: https://wiki.alpinelinux.org/wiki/Python_package_policies
[python package policies wiki page]:
  https://wiki.alpinelinux.org/wiki/Python_package_policies

```sh
curl -o APKBUILD \
    https://git.alpinelinux.org/cgit/abuild/plain/sample.APKBUILD
```

The ["APKBUILD Reference"](https://wiki.alpinelinux.org/wiki/APKBUILD_Reference)
is a wiki page.

The default functions can be seen in
["abuild.in"](https://github.com/alpinelinux/abuild/blob/master/abuild.in).

<https://repology.org> links for new versions:

- ["beancount"](https://repology.org/metapackage/beancount/information)
- ["dash"](https://repology.org/metapackage/dash/information)
- ["isync"](https://repology.org/metapackage/isync/information)
- ["jbig2enc"](https://repology.org/metapackage/jbig2enc/information)
- ["sane-backend-canon_dr"](https://repology.org/metapackage/sane-backends/information)
- ["sane-frontends"](https://repology.org/metapackage/sane-frontends/information)
  which incorrectly shows that a more recent version number, matching
  "sane-backends", is available
- "sasl2-oath" has zero releases

The `.githooks` folder contains a copy of the git hooks from
<https://github.com/alpinelinux/aports/tree/master/.githooks> and these can be
activated with `git config core.hooksPath .githooks`.

```sh
grep pkgver= ./user/*/APKBUILD
```
