#Session-DebugBar ([WTFPL](http://en.wikipedia.org/wiki/WTFPL))#
Pavel Železný (2bfree), 2012 ([www.pavelzelezny.cz](http://www.pavelzelezny.cz))

## Requirements ##

[Nette Framework 2.0.3](http://nette.org) or higher and PHP 5.3 or higher.

## Documentation ##
Simple DebugBar to show content of session.

## Examples ##
To load SessionPanel into the DebugBar by insert following code into config.neon
```neon
common:
	services:
		sessionPanel:
			class: ZeleznyPa\SessionPanel

	nette:
		debugger:
			strictMode: true
			bar:
				- @sessionPanel
```

You can also specify section to hide in debugbar by add setup section in service definition.

```neon
common:
	services:
		sessionPanel:
			class: ZeleznyPa\SessionPanel
			setup:
				- hideSection('Nette.Http.UserStorage/')
				- hideSection('Nette.Forms.Form/CSRF')
```
