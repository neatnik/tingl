# TINGL

_Terminal Implementation Non-intimidatinG Language_

TINGL is a simple language used for scripting interaction between players and objects in Terminal Land.

## Very Messy Unstable Draft Specification (October 31, 2020)

Note: This is all brand new stuff and will change _a lot_.

### Basics

TINGL is intended to be a straightforward, linear scripting language. The preferred file extension for TINGL scripts is `.tingl`.

Comments are indicated with a semicolon `;` character, followed by one or more spaces. If a comment appears on the same line as a function, it must be placed at the end, with one or more spaces preceding the semicolon. If a comment appears on a line by itself, the line may begin with a semicolon.

TINGL instructions must be placed on their own line. Two or more instructions cannot be placed on the same line. Whitespace before or after a function will be ignored, so developers are free to adopt whatever indendtation preferences they wish for readability or stylistic purposes.

Instructions are parsed and processed in the order in which they are presented in the script. Instructions are presented in uppercase for readability, but TINGL’s parser is case-insensitive.

### Special characters

* Constants begin with the `@` character
* Variables begin with the `$` character

To use these characters within TINGL for other purposes (e.g. within outputs), they must be escaped with a single `\` backslash character.

### Instructions

| Item | Syntax | Description |
| --- | --- | --- |
| UNDERSTAND | `UNDERSTAND x AS y` | Assigns an ad-hoc alias of one verb to another.  |
| RESPOND | `RESPOND [response]` | Respond directly to the player, privately. |
| SHARE | `SHARE [scope] [output]` | Share specified _output_ to specified _scope_. |

## Reference Script

```
; This is the TINGL script for Minneke, Terminal Land’s first NPC. As the primary 
; reference script for TINGL, this will be updated often. If you have any questions 
; or visit https://discord.gg/gJQ7ZphsB7 to discuss TINGL.

UNDERSTAND pat AS pet ; This makes it so that if the player types PAT MINNEKE,
                      ; it will be interpreted as PET MINNEKE.

ON test:
  EMOTE works just fine, thankyouverymuch. ; Emotes originate from the noun 
                                           ; to which the script is attached.
ON pet:
  RESPOND You pet Minneke.                 ; Private response sent directly to the 
                                           ; player (and only the player).
  SHARE @subject.place @subject.name pets Minneke.  ; This shares output to @subject’s 
  EMOTE purrs.                                      ; place, indicating that the @subject
                                                    ; (specified by name) pets the cat.

```
