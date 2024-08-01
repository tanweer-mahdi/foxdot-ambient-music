# System setup instructions
Installation of FoxDot and startup has been quite a task. Reasons being:
- FoxDot is not anymore maintained by the core developers. It is not supported with current mainstream Python versions (e.g: 3.11)
- FoxDot has some external dependencies (e.g: _tkinter) which themselves can be tedious setup and run

This repo uses a forked repo for FoxDot installation (see pyproject.toml) to make it work with Python 3.11

Apart from that, a major issue is with Tkinter when you use Pyenv (which is detailed here: https://github.com/pyenv/pyenv/issues/94). TLDR:
- Pyenv does not maintain tkinter
- Any Python installation done via Pyenv does not bind with tkinter even if that's installed via brew in the system

To resolve this, followins steps are taken:
- Uninstall your target Python version from Pyenv
- `brew install tcl-tk`
- Reinstall your target Python version using `pyenv install 3.**`

It should be bound with `tk` now. 

Given you have followed the startup instructions from the FoxDot docs, running the following command shall work now
`pdm run python3 -m FoxDot`


