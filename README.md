# discourse-alt-icons

This is a utility repository to generate theme components that replace Discourse's default icon set (FontAwesome). Currently this repo supports using the following icon sets:

- Feather icons (https://feathericons.com/)
- Heroicons (https://heroicons.dev, solid set, v1)
- Heroicons (https://heroicons.dev, outline set, v2)
- Phosphor duotone icons (https://phosphoricons.com, the duotone set)
- Unicons (https://iconscout.com/unicons, the line set)
- Material Design icons (https://github.com/marella/material-design-icons, filled and outlined)

Each icon set is provided as a separate repo:

- https://github.com/discourse/discourse-feather-icons
- https://github.com/discourse/discourse-heroicons
- https://github.com/discourse/discourse-heroicons-outline
- https://github.com/discourse/discourse-phosphor-duotone-icons
- https://github.com/discourse/discourse-unicons
- https://github.com/discourse/discourse-material-design-icons-filled
- https://github.com/discourse/discourse-material-design-icons-outlined

## Dev Setup

Clone the discourse-alt-icons repo and then run

```
yarn install
git submodule update --init --recursive
```

You should then see multiple theme components under the `repos` folder.

## Helpful Tools

For a full list of the icons included in Discourse, go to `/styleguide` in your Discourse instance. (If you get a 404, go to your admin settings and enable the styleguide.) Under `/styleguide/atoms/icons` you can see the full list of icons.

https://github.com/discourse/discourse_theme

Use the discourse_theme gem to quickly try out changes to a theme component by pointing it to one of the repos in the submodule.

For example, after you have made a change to mappings for, say, `feather-icons`, run `yarn build` and then try out the changes locally via:

```
cd repos
discourse_theme watch discourse-feather-icons
```

https://icones.js.org

A great resource, it lists 100+ freely available icon sets, and it helps you quickly find icons for a specific set via keyword search.

## Contributing

You can contribute to this project by proposing new (or better) icon matches for the included icon sets or by proposing a new icon set entirely.

The list of the currently supported icon libraries is in the `icon-sets.json` file, and each entry there has a JSON file under `mappings` that lists FontAwesome icon names and their mappings in the selected alternative icon set.

### To add a new mapping

Multiple steps are needed:

- add a new entry to `icon-sets.json`
- create a new file under `mappings` (you can copy/paste the `template.json` as an example)
- create a new blank repo, for example, at `discourse/discourse-sample-icons`
- add empty files under `assets/`, `javascripts/` and `LICENSE`
- add that repo as a submodule via `git submodule add git@github.com:discourse/discourse-sample-icons.git repos/discourse-sample-icons`

Start filling in the mappings for your new set. You can built it using

```
yarn build discourse-sample-icons
```

That should update the icon set component under `repos/discourse-sample-icons`. You can then use `discourse_theme watch discourse-sample-icons` to see updates in your local instance under the Styleguide > Icons screen.

If that all works correctly, you can post your changes as a pull request, both for `discourse-alt-icons` and as the new repo (submodule).

### More

You can also propose using a new set by posting to https://meta.discourse.org/t/alternative-icons/206693.
