# ScriptExit Widget

This is just a fork of the built-in QuickExit widget but with the ability to run a script before exiting.

## About
Qtile doesn't have a hook for exit events so this widget allows the user to run a custom script before exiting.

## Installation

You can clone the repository and run:

```
python setup.py install
```
or, for Arch users, just copy the PKGBUILD file to your machine and build.

## Configuration

Add the code to your config (`~/.config/qtile/config.py`):

```python
from scriptexit import ScriptExit
...
screens = [
    Screen(
        top=bar.Bar(
            [
                widget.CurrentLayout(),
                widget.GroupBox(),
                widget.Prompt(),
                widget.WindowName(),
                widget.Clock(format='%Y-%m-%d %a %I:%M %p'),
                ScriptExit(default_text="[X]",
                           countdown_format="[{}]",
                           countdown_start=3,
                           exit_script="~/my_shutdown_script.sh"),
            ],
            24,
        ),
    ),
]
```

## Customising

The options are the same as the QuickExit widget with the only addition being "exit_script"

<table>
	<tr>
		<td>default_text</td>
		<td>A text displayed as a button</td>
	</tr>
	<tr>
		<td>countdown_format</td>
		<td>This text is showed when counting down.</td>
	</tr>
	<tr>
		<td>timer_interval</td>
		<td>A countdown interval.</td>
	</tr>
	<tr>
		<td>countdown_start</td>
		<td>Time to accept the second pushing.</td>
	</tr>
	<tr>
		<td>exit_script</td>
		<td>Script to run on exit.</td>
	</tr>
</table>


## Contributing

If you've used this (great, and thank you) you will find bugs so please [file an issue](https://github.com/elParaguayo/qtile-widget-scriptexit/issues/new).
