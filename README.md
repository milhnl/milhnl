# An overview of my repositories and related information

## vis, the editor

### You probably want `vis-lspc`

[And you can find it here](https://gitlab.com/muhq/vis-lspc). This one made it
possible for me to use vis for everything. If you don't know what it is, this
elevates vis from an editor to a full-fledged IDE. If you're interested in
that, get it.

### And maybe these?

I wrote some plugins, this is probably the most useful one:

- [vis-format](https://github.com/milhnl/vis-format): Integrates vis with
  external formatters. Has some formatters predefined, but makes it very easy
  to add new ones. Has features like format-on-save, proper cursor positioning
  (ok, both are still in the `next` branch).

Then there are the "I want to set my options automatically" plugins. All of
these existed already when I started working on them. Stubborn, NIH, sure, but
I had actual reasons to write my own.

- [vis-filetype-options](https://github.com/milhnl/vis-filetype-options): Well,
  except for this one. Set default options for files, based on their
  `win.syntax`. Hooks support is coming.
- [vis-editorconfig-options](https://github.com/milhnl/vis-editorconfig-options):
  Basically `.editorconfig` support for vis. There was already another plugin
  that did that, but I didn't like the compiled dependency it has. This one is
  pure Lua (and a shell snippet to find the file — Lua has no concept of
  directories).
- [vis-modeline-options](https://github.com/milhnl/vis-modeline-options): Reads
  a `vi(m)` modeline and applies the options.

If you want all three, that's the order I'd `require` them in. Hooks run in the
registered order, and you'll probably want modelines to override editorconfig
which overrides file type defaults.

Then there's these miscellaneous little helpers:

- [vis-backspace](https://github.com/milhnl/vis-backspace): Pressing backspace
  at the beginning of the line aligns the line (and cursor) to the nearest
  shorter tabstop when indenting with spaces. Uses the new-ish `win.options` to
  detect the amount of spaces to be used.
- [vis-sudoedit](https://github.com/milhnl/vis-sudoedit): This one doesn't work
  yet. When it is finished, it should help vis opening files that you can't
  edit. And probably prompt to create directories if they don't exist. On the
  backburner.
- [vis-term-title](https://github.com/milhnl/vis-term-title): Integrate vis
  with the Terminal.app title and file icon.
