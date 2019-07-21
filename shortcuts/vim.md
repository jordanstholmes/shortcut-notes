# Vim
## Inserts
| action | command | notes |
| --- | --- | --- |
| Enter **insert** | `i` |  |
| **Insert** at start of line | `I` (uppercase)|  |
| Insert **After** cursor | `a` |  |
| Insert **After** line | `A` (uppercase)|  |
| **Open** new line below | `o` |  |
| **Open** new line above | `O` (uppercase) |  |

## Motions
| action | command | notes |
| --- | --- | --- |
| **Correct** line | `cc` |  |

## Using Registers (copy and paste)
| action | command | notes |
| --- | --- | --- |
| Register yank to | `"<register-char>y` | Note that the double quotes are not a typo |
| | **EXAMPLE:** `"ryy` | Register 'r', yank the whole line | 
| Register paste from | `"<register-char>p` | Note that the double quotes are not a typo | 
| | **EXAMPLE:** `"rp` | Register 'r', paste contents | 
| Register paste during insert mode | `CTRL + r  <register-char>  ENTER` |  | 
| View register contents | `:reg` |  | 
| Unnamed register paste | `""p` | the last thing changed or deleted is saved here |
| Previous deletes 0 - 9 | `"<num>p` | last 9 deletions are automatically stored |

### ReadOnly Registers
| action | command | notes |
| --- | --- | --- |
| Last inserted text register | `".` | (readonly) |
| Current file path register | `"%` | (readonly) |
| Last command register | `":` | (readonly) useful to run last command again `@:` |

## Macros
| action | command | notes |
| --- | --- | --- |
| Write to macro | `q<char-for-name>q` | |
| Run macro | `@<char>` | |

## Running Commands
| action | command | notes |
| --- | --- | --- |
| Run external shell command | `:! <command>` | |

## Navigation
### Line nav
* start of line: `0`
* first char of line: `SHIFT + ^`
* end of line: `$`
* start of **w**ord: `w`
* **e**nd of word: `ea`
* **b**ack word: `b`
### File nav
* top of file: `gg`
* bottom of file: `G`
* Move by code block/paragraph `}/{`
* Go to last insertion `gi`
* Go backwards for every move `g;`
* Go forwards for every move `g,`  
* Full page **Forward**: `CTRL + f`
* Full page **Backward**: `CTRL + b`
* page halfpage **u**p: `CTRL + u`
* page halfpage **d**own: `CTRL + d`
* **G**o to line: _line-number_ `+ G`
* previous/next token under cursor: `#/*`
* **H**igh **M**iddle **L**ow of screen: `H || M || L`
## Undoing Redoing Repeating
### Undo Redo
* **u**ndo: `u`  
* **r**edo: `CTRL + r`
### Cut and Paste
* select (**v**isual): `v`
* copy (**y**ank): `y`
* copy line: `yy`
* cut (**d**elete): `d`
* **d**elete line: `dd`
* **p**aste: `p`
> note this can paste anything that was deleted
### Repeat
* repeat previous edit: `.` _(period)_

| action | command |
|---|---|
| change every occurrence of string in file | `%s/**old**/**new**/g` |
## Manipulating Text
| action | command | notes |
| --- | --- | --- |
| select by characters | `v` | |
| select by lines | `V` (capital) | |
| select by columns | `CTRL + v` | | 
| indent line in or out | `>> OR <<` | prepend the number of lines to move; if text is selected, use one carrot instead of two | 
## Correct or Delete to Character
**use `c` or `d` followed by motion followed by char**
`<c|d><motion><boundingChar>`
  * apply to text bounded by <char>
  * must be quotes, parens, brackets, etc.
  * inclusive inner match: `a<char`

| action | command | notes |
| --- | --- | --- |
| up to but NOT including char | `t<char>` | |
| up to AND including char | `f<char>` | |
| exclusive inner match | `i<char>` | |
| delete a word under cursor | `daw` | includes space after word |
| delete a word under cursor (leave space) | `diw` | does not delete space after word |

## Search
| action | command | notes |
| --- | --- | --- |
| find and replace next occurence | `:s/<pattern>/replacement/` | Only replaces one occurrence |
| find and replace most recently searched pattern | `:s//replacement/` | |
| find char | `f<char>` | |
| find char backwards | `F<char>` | |
| yank, delete, change forward or backwards to a search | `y/search` or `y?search` | |


* to search down: `/searchTerm <enter>`
	* same term down: `n`
	* same term up: `N`
	* go back: `CTRL + o`
	* go forward: `CTRL + I`
* to search up: `?searchTerm <enter>`
## Fun Combos
* delete until end of file: `dG` 
