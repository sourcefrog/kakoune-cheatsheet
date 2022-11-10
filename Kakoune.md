# Kakoune / Dance notes

## Changing/inserting text

- `i`: enter insert mode before each selection
- `a`: enter insert mode after each selection
- `I`: enter insert mode at the start of each line with a selection
- `A`: enter insert mode at the end of each line with a selection
- `.`: repeat the last insert mode change
- `r`: replace all selected characters with the single character entered next

## Case

- `` ` ``: to lower case
- `~`: to upper case
- ` a-` `: swap case

## Copy/paste
- `y`: yank selections
- `c`: _change_: yank and delete each selection and enter insert mode
- `p`: paste after each selection end
- `P`: paste before each selection end
- `R`: _replace_ each selection with yanked text
- `a-R`: replace each selection with _every_ yanked text (???)
- `c-R`: pick a register interactively and insert it (works in insert mode too)

## Selections
- `%`: select the whole buffer
- `x`: expand selections to contain full lines (including end-of-lines)
- `_`: trim whitespace surrounding each selection, dropping those containing only whitespace

## Saving selections

By default these use the `^` register.

- `Z`: save selections
- `z`: restore selections

## Selecting objects

For nestable objects, a _count_ can be used in order to specify which surrounding level to select.

    ((((a b) (c (d)))))

- `a-.`: repeat an object selection: for whole-object selections this will extend to the enclosing object of the same type
- `a-a`: select a whole object (including surrounding characters); object type to follow

## Object types
- `b`, `(`, `)`: parenthesis
- `B`, `{`, `}`: `{}` block
- `r`, `[`, `]`: _rectangle?_ -- `[]` block
- (more)

## Search
- `*`: set the search pattern to the current selection
- `/`: prompt for a search pattern, then select the next match after each selection
- `a-/`:
- `?`: (shift-`/`): extend to the next match after each selection
- `n`: select the next match of the search pattern after the main selection

## Multiple selections

- `,` (or `space` in Dance?): clear selections and keep only the main one
- `a-,`: clear the main selection
- `)`: rotate selections: the main selection becomes the next one
- `enter`: show selection numbers at the end of lines
- `s`: create a selection for each match of the given regex within the current sel; selects the count-th capture if a count is given
- `N`: add new selections with the next match of the search pattern after the main selection
