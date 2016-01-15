Valadoc-org
===========

Stays crunchy, even in milk.

Building
========

In order to build the docs you will need the following:
* `valadoc` past [this](https://git.gnome.org/browse/valadoc/commit/?id=69dab58994bb913f14bbaae3c32c37951cf74e02) commit
* `php`
* 4 GB of free space

On elementary OS or Ubuntu run:
```bash
$ sudo apt-get install libvaladoc-dev php5
```

Arch or derivatives run:
```bash
$ yaourt -S valadoc-git php
```

After you have `valadoc` installed, you can move to building the documentation. Simply run:

```bash
$ make serve
```

or:

```bash
$ make serve-mini
```

for a minimal test version and grab yourself a cup of coffee. This will take a bit of time. If you encounter an error at this step, please see the [common pitfalls](#common-pitfalls) section. After you completed building you should see a `valadoc.org` folder.

To access the documentation navigate your browser to http://localhost:7777.

Common Pitfalls
===============

`Uncaught Error: Class 'mysqli' not found`
- Uncomment `extension=mysqli.so` in your OS's php.ini (`find /etc -name php.ini`)

`error: failed to load driver`
- Your valadoc version does not support the requested vala version. Install a recent vala version and recompile valadoc.
- Change `VALAC_VERSION` in Makefile.

Other errors
- Check `LOG` in the root of this repo for more information
- Have you run out of disk space?