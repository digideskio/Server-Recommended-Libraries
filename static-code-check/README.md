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

#### Key Binding ####

Once you install sublime plugin for Rubocop, it will automatically check text view and mark it the warnings. If you don't want it to mark, you can disable it by `Preferences` > `Package Settings` > `RuboCop` > `Settings - User`. From you can decide if you want to enable/disable this feature by default.

```javascript
{
	"mark_issues_in_view": false // disable by default
}
```

You can also use key binding to toggle this setting on the fly. `Preferences` > `Package Settings` > `RuboCop` > `Key Bindings - User`.

```javascript
[
	// you can set any keys you want. In this case, I use Command + Option + Shift + r
    { "keys": ["super+alt+shift+r"], "command": "rubocop_pause_toggle" }
]
```


### Atom ###
You can use [Atom](https://atom.io/) edit if you want. Rubocop also has plugin for this. 

#### Plugin Installation ####

Go go `Atom` > `Preference` > `Packages` > search for `Rubocop` > install `Policeman Rubocop`.

#### Usage ####

Default key binding to toggle Rubocop is `Control` + `Option` + `L`.










