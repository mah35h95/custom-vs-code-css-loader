# Custom VsCode CSS loader

Guide to setup a custom css loader to enable the use of more than one [Monaspace font][1] in VsCode

### Useful Links

Original Article - [Customize Visual Studio Code for Multiple Fonts and styles](https://razvanpredescu.medium.com/customize-visual-studio-code-for-multiple-fonts-and-styles-96f83562af58)  
VsCode Extension - [Custom CSS and JS Loader][2]

## Steps

### Step 1

Install [Custom CSS and JS Loader][2]

### Step 2

Download and Install the [Monaspace font][1] of your liking

### Step 3

-   Write your custom CSS into `styles.css` file
-   Place the file in any accessible location of your liking
-   Here is an example of the contents of the file [`styles.css`](styles.css)

### Step 4

Add the following like to your VsCode User settings file

```json
"vscode_custom_css.imports": ["file://C:/User/path/to/styles.css"],

```

### Step 5

Define the following editor's font settings in your VsCode User settings file

```json
"editor.fontFamily": "Monaspace Xenon",
"editor.fontLigatures": "'ss01', 'ss02', 'ss03', 'ss04', 'ss05', 'ss06', 'ss07', 'ss08', 'calt', 'dlig'", // For Monaspace fonts
"editor.fontWeight": 200,
"workbench.colorTheme": "Night Coder Ember Contrast Italic", // Optional: Theme of your choosing
"editor.fontSize": 12, // Optional: Define Font size
"editor.tokenColorCustomizations": { // Optional: Define each token elements font style and color
		// "variables": "#dc77ee",
		"textMateRules": [
			{
				"scope": [
					// following will be in italic in Monaspace Argon style
					// "comment"
					// "entity.name.type.class", //class names
					// "keyword", //import, export, return…
					// "storage.modifier", //static keyword
					// "storage.type", //class keyword
					// "support.class.builtin",
					// "keyword.control",
					// "constant.language",
					// "string.quoted.single",
					"entity.other.attribute-name",
					"entity.name.method",
					"entity.name.tag"
				],
				"settings": {
					"fontStyle": "italic"
				}
			},
			{
				"scope": [
					// following will be in italic
					// "comment",
					// "entity.name.type.class", //class names
					"keyword", //import, export, return…
					"storage.modifier", //static keyword
					"storage.type", //class keyword
					"support.class.builtin",
					"keyword.control",
					"constant.language"
					// "string.quoted.single",
					// "entity.other.attribute-name",
					// "entity.name.method",
					// "entity.name.tag"
				],
				"settings": {
					"fontStyle": "bold"
				}
			},
			{
				"scope": [
					//following will be in italic
					// "comment",
					"entity.name.type.class" //class names
					// "keyword", //import, export, return…
					// "storage.modifier", //static keyword
					// "storage.type", //class keyword
					// "support.class.builtin",
					// "keyword.control",
					// "constant.language"
					// "string.quoted.single",
					// "entity.other.attribute-name",
					// "entity.name.method",
					// "entity.name.tag"
				],
				"settings": {
					"fontStyle": "italic bold"
				}
			}
		]
	},

```

### Step 6

-   Close all instances of VsCode
-   Now Open VsCode in Administrator mode
-   Open Command pallet e.g. for 🪟 use the shortcut: `ctrl + shift + p` for 🍎 use the shortcut: `cmd + shift + p`
-   Type “Enable Custom CSS and JS” and hit enter
-   Restart VsCode (the extension will also prompt for restarting VsCode as well)
-   Incase you made any changes in `styles.css` and changes are not reflecting just repeat `Step 6`
-   `Step 6` is necessary to be run every time VsCode gets updated

[1]: https://github.com/githubnext/monaspace#monaspace
[2]: https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css
