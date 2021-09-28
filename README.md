# discourse-alt-icons

This is a utility repository that generates theme commponents for Discourse.

## Setup

Clone the repo and then run

```
git submodule update --init --recursive
```

You should then see multiple theme components under the `repos` folder.

## Contributing

You can contribute to this project by proposing new (or better) icon matches for the included icon sets or by proposing support for a new icon set. The list of the currently supported icon libraries is in the `icon-sets.json` file, and each entry there has a JSON file under `mappings` with the icon name mapping between the existing Discourse icon set (Font Awesome) and the new set.

To test your changes, you can use the provided build script by running:

```
yarn build
```

## Helpful Tools

For a list of the currently used icons in Discourse, go to `/styleguide` in your Discourse instance. If you get a 404, go to your admin settings and enable the styleguide.
