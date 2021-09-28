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

If that builds correctly, feel free to post your changes as a pull request.

## Helpful Tools

For a full list of the icons included in Discourse, go to `/styleguide` in your Discourse instance. (If you get a 404, go to your admin settings and enable the styleguide.) Under `/styleguide/atoms/icons` you can see the full list of icons.

https://github.com/discourse/discourse_theme
Use the discourse_theme gem to quickly try out changes to a theme component by pointing it to one of the repos in the submodule, i.e.:

```
cd repos
discourse_theme watch discourse-feather-icons
```

https://icones.js.org
This is a good resource, it lists 100+ freely available icon sets, and it helps you find icons using a search tool for each set.
