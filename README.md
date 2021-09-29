# discourse-alt-icons

This is a utility repository to generate theme components that replace Discourse's default icon set (FontAwesome). Currently this repo supports using the following icon sets:

- https://github.com/feathericons/feather
- https://github.com/phosphor-icons/phosphor-icons
- https://github.com/Iconscout/unicons

Each icon set is provided as a separate repo:

- https://github.com/discourse/discourse-feather-icons
- https://github.com/discourse/discourse-phosphor-duotone-icons
- https://github.com/discourse/discourse-unicons

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

Take one of the existing sets, say, `discourse-feather-icons` and install the component in your local instance. Head over to `/styleguide/atoms/icons` to preview the icons.

You should see some icons there from Feather Icons, and some still using FontAwesome. If you find an equivalent, you can add it to the `mappings/feather.json` set. For example:

```
  "cog": "settings",
```

(The key in that JSON file refers to the Discourse icon name, the value refers to the selected icon set, i.e. Feather in this case.)

To test your changes, you can use the provided build script to generate the icons:

```
yarn build feather
```

That should update your feather icon set component, and if you are using `discourse_theme watch ...`, it should immediately update the component in your instance, too.

If that all works correctly, feel free to post your changes to the mappings file as a pull request.
