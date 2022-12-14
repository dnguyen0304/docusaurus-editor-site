---
sidebar_position: 1
---

# Manage Docs Versions

Docusaurus can manage multiple versions of your docs.

## 2022-09-29

- Released `@docupotamus/docusaurus-theme-editor@0.9.1` with visibility tracking. Fixed client-side only code in server-side rendering.

## 2022-09-26

- Released `@docupotamus/docusaurus-theme-editor@0.8.0` with githubAuthorizationRedirectUrl theme configuration and reading bands debug mode.

## 2022-09-24

- Released `@docupotamus/docusaurus-theme-editor@0.7.0` with welcome notification.

## 2022-09-23

- Released `@docupotamus/docusaurus-theme-editor@0.6.0` with discard button tooltip. Fixed dark mode for editor container.

## 2022-09-22

- Released `@docupotamus/docusaurus-theme-editor@0.5.0` with merge-specific tooltips and pull request title auto focus. Fixed saved content being overwritten.

- Inspect vscode.dev for the implementation.

## Create a docs version

Release a version 1.0 of your project:

```bash
npm run docusaurus docs:version 1.0
```

The `docs` folder is copied into `versioned_docs/version-1.0` and `versions.json` is created.

Your docs now have 2 versions:

- `1.0` at `http://localhost:3000/docs/` for the version 1.0 docs
- `current` at `http://localhost:3000/docs/next/` for the **upcoming, unreleased docs**

## Add a Version Dropdown

To navigate seamlessly across versions, add a version dropdown.

Modify the `docusaurus.config.js` file:

```js title="docusaurus.config.js"
module.exports = {
  themeConfig: {
    navbar: {
      items: [
        // highlight-start
        {
          type: 'docsVersionDropdown',
        },
        // highlight-end
      ],
    },
  },
};
```

The docs version dropdown appears in your navbar:

![Docs Version Dropdown](./img/docsVersionDropdown.png)

## Update an existing version

It is possible to edit versioned docs in their respective folder:

- `versioned_docs/version-1.0/hello.md` updates `http://localhost:3000/docs/hello`
- `docs/hello.md` updates `http://localhost:3000/docs/next/hello`
A