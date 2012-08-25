# Nette Session panel

## Requirements ##

[Nette Framework 2.0.3](http://nette.org) or higher and PHP 5.3 or higher.

## Documentation ##
Simple DebugBar to show contents of session.

## Examples ##

To load SessionPanel into the DebugBar by insert following code into config.neon

```neon
nette:
	debugger:
		bar:
			- Kdyby\Diagnostics\SessionPanel\SessionPanel
```

You can also specify section to hide in debugbar by add setup section in service definition.

```neon
services:
	sessionPanel:
		class: Kdyby\Diagnostics\SessionPanel\SessionPanel
		setup:
			- hideSection('Nette.Forms.Form/CSRF')

nette:
	debugger:
		bar:
			- @sessionPanel
```
