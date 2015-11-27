# Welcome

> It's dangerous to go alone. Here's a quick run through of optional post-install setup

**Prerequisite:** Readme client side setup

Assuming you have cloned the repo and done your first gulp, here are a few things you may need to do after initial setup.

* [Adding a new component](#adding-a-new-component)
* [Adding Project Credentials](#adding-project-credentials)
* [Adding images](#adding-images)
* [Adding custom fonts](#adding-custom-fonts)
* [Setting the default development homepage](#setting-the-default-development-homepage)
* [Pretty URLs](#pretty-urls)

---

##Adding a new component

Handlebars allows seperate components/partials to be created. This approach allows the structure and the styles to be seperate and then included in the view files where needed.

To add a create partial:

1. Inside of `views/_partials` folder, create a new folder with the name of the new partial e.g `newComponent`.
2. Inside of this new folder, `views/_partials/newComponent`, create two files.
    * `newComponent.hbs` - the handlebars HTML file.
    * `newComponent.scss` - the Sass file.
    * Both of the above files follow the convention of being named the same as the folder. This makes it easier to find the partial files inside of a code editor.
3. At the top of the newly created Sass file, add a comment giving a small description of what the file is for. This is to ensure this Sass file is included in the build. An example of this would be `//styles for newComponent`. Running `gulp` will include the Sass file - ready for styling.
4. To include the component in a view, include it by using the following code `{{> newComponent/newComponent }}`.

Partials can be made a modular as required - allowing you to have a `button` and `input` partial, which are included in a `search` partial which itself is used in the `header` partial.

##Adding Project Credentials

`_config/creds.json` is a small file where anchillary project details are kept. These are used through the generator and include the following:

* Site - the name of the site.
* Author - the person or organisation that developed the site.
* packageName - The name of the package which is used when creating a release zip file. It is recommended to include characters instead of spaces here e.g. "package-name" instead of "package name"

##Adding images

The directory `images` in the `_source` directory is copied over during the build process.

This folder is copied to the `public` folder whenever the `gulp` task is run **and will need to be re-run when adding new images**

When referencing images in the styles, reference them as:  

`url('/_client/images/<path>')`

##Adding custom fonts

Creating the directory `fonts` in the `_source` directory will mean that anything inside of this folder is copied over during the build process.

This folder is copied to the `public` folder whenever the `gulp` task is run **and will need to be re-run when adding new images**

When referencing fonts in the styles, reference them as:

`/_client/fonts/<font-name>`

##Setting the default development homepage

By default, the development server directs to a placeholder index view if a view file cannot be found. To change this, in the file `main.js` change line 28 to be the view name that you want to act as the homepage / default. For example, changing it to the following will make the root level `styleguide.hbs` file act as the default homepage.

```
url = 'styleguide'
```

##Pretty URLs

When developing views, by following a directory structure you can ensure URLs are displayed without the file extension both locally and on a remote server.

An address such as `localhost/pretty-url` can be achieved by following the structure below

```
└── views/
    └── pretty-url/
        └── index.hbs
```

Similarily, `localhost/pretty-url/another-pretty-url` can be achieved via the following

```
└── views/
    └── pretty-url/
        └── index.hbs
        └── another-pretty-url
            └── index.hbs
```