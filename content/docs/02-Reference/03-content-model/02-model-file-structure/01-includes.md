---
title: Includes
weight: 10
---

# Includes

In addition to using a single ```model/base``` config file, one can use the ```poppygo/model/includes/```
directory to maintain an easier organization.

You can split up the ```model/base-file``` and use seperate files
for ```menu```, ```collections```, ```dynamics```, and ```singles```.

Poppygo automatically reads the files in ```./poppygo/model/includes/``` and
merges these tree inside ```model/base```.

Each file represents a configuration root object, such as collections.toml for
[Collections], menu.toml for [menu], singles.toml for [single] etc… 

Each file’s content must be top-level, for example:

The configuration in ```./poppygo/model/base.yaml```

```yaml
menu:
  - key: pages
    title: Pages
    menuItems:
      - key: about

  - key: config
    title: settings
    menuItems:
      - key: config
```

Equals ```./poppygo/model/includes/menu.yaml```
```yaml
- key: pages
  menuItems:
  - key: about
  title: Pages
- key: config
  menuItems:
  - key: config
  title: settings
```
