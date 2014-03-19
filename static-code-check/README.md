# Static & Lint Check #

## Goal ##
Eventually we want to have a uniform coding style so that you don't have to hear too many **wtf**s when you are on holidays because someone else edits your code.


## Code Check Tools ##
There are many available tools to check the code styling, convention and lint

1. [Ruboto Style Check](https://github.com/bbatsov/rubocop): check general Ruby code style
2. [Rails Best Practices](https://github.com/railsbp/rails_best_practices): check conventional Rails styling

## Useful Tips ##
### Sublime Space vs Tab ###

If you are using sublime, probably you are using tab by default. See below image:

![Tab vs Space](https://dl.dropboxusercontent.com/u/358323/screenshots/work/server-recommendation-gems/tab-vs-space.png)

You can switch between tab and space, but you may want to default tab to space. Go to `Preferences` > `Settings - User` and use below settings:

```javascript
{
	"show_full_path": true,
	"translate_tabs_to_spaces": true
}
```

If you want to have a specific setting on file type (e.g. say Ruby), you can open a Ruby file and go to `Preferences` > `Settings - More` > `Syntax Specific - User`

```javascript
{
	"extensions":
	[
		"rb",
		"Vagrantfile",
		"Guardfile",
		"Berksfile"
	], // up to you for this extension formats
	"tab_size": 2,
	"translate_tabs_to_spaces": true
}
```

### Sublime plugin for Rubocop ###

You can install plugin of Rubocop so that it can highlight in real-time. First, you need to install [Sublime Package Control](https://sublime.wbond.net/installation). Once installed, you can look for package manager by `shift + command + p` > look for `Package Control: Install Package` > type `Rubocop`

















