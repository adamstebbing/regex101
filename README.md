# REGEX TUTORIAL

## Regular
Ex. grep, sed, vi

**Anchors** - ^-beginning of line, $-end

**Character Sets** - [abcdef][A-Z][a-z0-9][[:alnum:]]-range,\<\>- word boundaries, \(\)-pattern matching (up to 9 different patterns), \{\}-amount of something (ex. \(192.\)\1

**Modifiers** - .-anything,*-0 or more, ^- means NOT when used in a range

**Special Sets** - \b - word boundaries, \B - non-word-boundaries, \d - digit, \D - non-digit, \w - word \W, \s - whitespace, \t - tab, \n - new line, [[:alnum:]] - alphanumeric, :digit:. 
[^a-z][a-z]*

**GREP Flags:** -v - inverted match, -E - extended, -i - case insensitive, -c - count, -l - files with match, -L - files without match, -n - line numbers, -B # - show # of lines before, -A # - show # of lines after

## Extended
Ex. awk, nawk, egrep, grep -E
**(word|word)** - either operator, exe. (From|To):adamstebbing@gmail.com; **?** - match 0 or 1; **+** - match 1 or more

Don't have to use backslashes
{}, <>, () - not used in extended

`egrep "a[n]? (simple |easy )?solution"`

### SED - stream editor
& - represents input_stream

`sed "s/input_stream/output_stream/"` - regular sed syntax

`sed "s_\(^[A-Z][a-z]*\s\)_THIS IS A MESSAGE FROM THE AIR FORCE \1_"`

`sed "s_^[A-Z][a-z][a-z]*\s_THIS IS A MESSAGE FROM THE AIR FORCE &_"`

`sed -nr "s_^[A-Z][a-z]+\s_THIS IS A MESSAGE FROM THE AIR FORCE &_p"`

**Regular Flags:** -n - quiet, -r - extended, -e <sed expression>, primarily used for multiple sed expressions, -f - read in sed commands from script (cmds should be on seperate lines), -V - version, -h - help
  
**End Flags** (after final delimiter): /p - print, /g - global (do multiple times on the same line), /I - ignore case, /w <filename>, write to file, /#q - quit after # iterations
Use sed like grep - sed "s/phrase//10q"
