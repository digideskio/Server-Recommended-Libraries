# Static & Lint Check #

## Goal ##
Eventually we want to have a uniform coding style so that you don't have to hear too many **wtf**s when you are on holidays because someone else edits your code.


## Code Check Tools ##
Currently we are going to use two types of check:

1. [Ruboto Style Check](https://github.com/bbatsov/rubocop): check general Ruby code style
2. [Ruby Lint Check](https://github.com/YorickPeterse/ruby-lint): check semantic

## Useful Tips ##
### Sublime Space vs Tab ###

If you are using sublime, probably you are using tab by default. See below image:

![Tab vs Space](http://grab.by/vefC)

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

