

                     _____________  /^\    ____________
                    /             \/@@@\\ /            \
                    \__        ___/@@@@@@\\___         /
                       |       ||@@@@@@@@@@@//        /
                       |       ||@@@@@@@@@//        //
                       |       ||@@@@@@@//        //
                       |       ||@@@@@//        //\
                      /|       ||@@@//        //###\\
                    //@|       ||@@/        //#######\\
                  //@@@|       ||//       //###########\\
                <X@@@@@|       |/       //##############X>
                  \\@@@|              __###############//
                    \\@|            //__/############//
                      \|           /___  ___   __  //__
                       |        ///_  / /_  ^^^  ^^^   \
                       |      //###/  /##/ ____  ___   /
                       |    //####/  /##/  /#//  / /  /
                       \__//  \\#/  /##/  ////  / /  /_
                                \/___//___/ /___//____/
                                  \\###//
                                   \\//
                        Editing at the speed of thought



























Vim – but why?
================================================================================

* We edit text all day: Code, e-mails, documentation, ...
⇒ Invest in an efficient editor, learn the keyboard shortcuts
* No mouse. Learn touch typing!
* Keys enter your muscle and linguistic memory
* Ubiquitous: Every Linux machine
* Fast, insanely feature-rich
* Syntax highlighting, color schemes and plugins for everything
* Handles big files
* Settings per file type
* Configuration and plugins are text files (git-able)
* Since 1991, still actively developed, lively community
* Use it for one-off log analysis and data analysis/reformatting jobs



































Basics
================================================================================

* Modes: Normal, insert, command, visual selection, ...
* Keys depend on mode

    <Esc>       Return to normal mode
    i           Insert mode
    <Esc>:wq    Write and quit
    <Esc>:qa!   Quit wherever without saving
    <F1>        Help







































Editing
================================================================================

    i               Insert mode at the cursor position
    a               Append right of the cursor
    o               New line below and insert
    x               Delete one character
    R               Replace mode
    dd              Delete line
    cc              Change line
    yy              Yank (copy) line
    p               Paste below

    I               Insert at front of line
    A               Append at end of line
    O               New line above and insert
    X               Delete to left
    D               Delete until end of line
    C               Change until end of line
    P               Paste above

    J               Join with next line
    << >>           De/Increase indent
    Ctrl-a Ctrl-x   In/Decrease next number in the line


























Movement
================================================================================

    h j k l         ← ↓ ↑ →
    w W             Word/WORD forward
    e E             End of word/WORD forward
    b B             Back word/WORD
    ge gE           Goto end of word/WORD backward

    0               Start of line
    $               End of line
    gg              Goto first line
    G               Goto last line
    [count]G        Goto line number [count]

    ( )             Sentence back/forward
    { }             Paragraph back/forward

    %               Matching ( [ { } ] )

    f{char} F{char} Find {char} on the current line forward/backward
    t{char} T{char} Till before/after {char} to the right/left




























Movement (2)
================================================================================

    g; g,           Back/forward where you edited

    [{ ]} [( ])     Back/forward to unmatched {, } or (, )

    Ctrl-e Ctrl-y   Move screen up/down, cursor stays
    z<Enter>        Move line with cursor to top of screen
    z.              Move line with cursor to center of screen








































Combining
================================================================================

    Combine actions with motions

    ct(             Change to '('
    gU$             Go Uppercase to the end of the line
    V/foo()         Visual selection until finding foo()

    Combine counts with actions and motions

    3dd             Delete 3 lines
    2dw             Delete 2 words
    80A=<Esc>       Append 80 times '='

    Text objects allow to select surrounding text to act on
    (:help text-objects)

    daw             Delete a word
    gqip            Reformat inner paragraph
    ya(             Yank (copy) everything between and including ( )
    ci"             Change inner " "
    vat             Select between <tag> text </tag>



























Visual mode
================================================================================

    v               Visual selection character-wise
    V               Visual selection whole lines
    Ctrl-v          Visual block

    All movements and search work

    $               Extend visual block to end of each line
    o               Other side: Switch cursor to other side of selection

    d               Delete
    y               Yank (copy)
    gv              "Go visual", restore last selection

    I               Insert at front (in block mode)
    A               Append at end (in block mode)

    g Ctrl-a        Increase numbers +1 for each line






























Undo and Redo
================================================================================

    u                       Undo
    Ctrl-r                  Redo
    .                       Repeat last command

    :help undo-tree         There's an undo tree!
    :help undo-persistence  Persist undo info per file









































Completion
================================================================================

    Ctrl-n          Next keyword completion
    Ctrl-p          Previous keyword completion
    Ctrl-x Ctrl-f   File name completion
    Ctrl-x Ctrl-o   "Omni completion" – needs file type specific plugin











































Command Line
================================================================================

    :                   Enter the command line
    <Tab>               Tab completion
    <Up> <Down>         Browse history
    :{prefix}<Up>       Search history
    :w                  Write file
    :e [filename]       Edit [filename]
    :set 'setting'      To change settings for the session:
                        nocompatible
                        laststatus=2
                        wildmenu
                        textwidth=80 tabstop=4 shiftwidth=4 expandtab
                        nowrap
                        scrolloff=10
                        colorcolumn=80
                        filetype=markdown
                        fileformat=unix
                        fileencoding=utf-8






























Help
================================================================================

    :help user-manual   Help contains the user manual (like a book) and
                        reference manual

    :help B             Help about key 'B'
    :help diff          Help about the diff mode
    :help :s            Help about :commands
    :help 'tw'          Help about settings








































Search and Replace
================================================================================

    /<regex>            Search forward
    ?<regex>            Search backward
    n N                 next/previous match
    * #                 Search word under cursor forward/backward

    :set incsearch      Incremental search
    :set hls            Highlight search matches
    :nohls              Remove search highlight

    :%s/regex/replacement/[flags]
                        Search and replace
                        % = whole file
                        Replacement: & = whole match, \1 match group 1
                        Flags:
                            g   Replace every match
                            c   Confirm replacement
                            i   Ignore case

    :g/regex/{cmd}      Execute command {cmd} on every line matching regex
                        Commands:
                            d   Delete line
                            m$  Move to end of file

























Marks
================================================================================

    m[a-z]      Set mark a to z in the current file
    'a          Jump to line with mark a
    `a          Jump to position with mark a

    d'a         Delete from this line to mark a
    v'a         Visual selection from this line to mark a

    m[A-Z]      Global marks (including file)

    There are some special marks:

    `.          Jump to position of last change
    `< `>       Jump to beginning/end of last visual selection
    ``          Jump back

































Registers
================================================================================

    Registers are like named clipboards a-z

    "a to "z    Access register a-z
    "ayy        Yank line into register a
    "bdd        Delete line and put it into register b
    "ap         Paste register a below

    "0 to "9    Numbered registers: Contain last yanked texts
    :registers  Show registers' content

    "+          System clipboard

    "A to "Z    Append to register a
    "Ayy        Append line to register a

































Sorting
================================================================================

    :sort [flag]    Sort
                    !   Reverse
                    n   Numeric
                    f   Float











































Key mapping and abbreviations
================================================================================

    :map {lhs} {rhs}    Map keys {lhs} to act as if keys {rhs} were pressed
    :map                List all key mappings
    :map <key>          List mappings starting with <key>

    :abbreviate :smile: 😄
                        Abbreviations are expanded in insert mode









































External commands, read files
================================================================================

    :! ‹command›    Pipe through command
    :r! ‹command›   Read command output into file
    :w filename     Write filename (works with selection)
    :r filename     Read file below current line
    gf              Goto file under cursor










































Spell checking
================================================================================

    :set spell
    :set spelllang=en

    ]s [s           Next/previous misspelled word
    z=              Spelling suggestion

    zg              Good word, add to dictionary
    zw              Wrong word, add to "bad" dictionary







































Macros
================================================================================

    Macros record and replay key sequences

    qa      Record macro into register a
    q       Stop recording
    @a      Replay macro from register a
    @@      Replay last macro









































Split windows
================================================================================

    :split
    Ctrl-w s        Split window horizontally

    :vsplit
    Ctrl-w v        Split windo vertically

    Ctrl-w h/j/k/l  Move to window left/down/top/right

    :e file         Edit different file
    :enew           Edit new file
    :q              Close split window




































Directory browser, open ZIP files
================================================================================

    vim .           Interactive directory browser

    vim file.zip    Browse .zip file, open/edit/write contained files












































Diff mode
================================================================================

    vimdiff file1 file2

    ]c [c           Next/previous difference
    do              diff obtain: Fetch change from other side
    dp              diff put: Push change to other side










































Grep, quickfix
================================================================================

    :grep [options] regex files
                        Run 'grep' with the given arguments
    :cn                 Next match
    :cp                 Previous match

    :make               Same with 'make', jump to errors









































Plugins I use
================================================================================

    Airline             Enhanced status line ↓↓
    :Tabularize /|      Format tables
    :Gstatus            Fugitive: Git integration
    Ctrl-N              Multiple cursors
    ,uf                 Unite: Fuzzy file search
    ,ug                 Unite: grep
    <Space>             vim-space: Hit <Space> to repeat last movement








































Resources
================================================================================

    vimtutor                        Interactive tutorial inside Vim
    https://www.openvim.com/        Interactive tutorial website
    http://vimgenius.com/           Interactive companion to vimtutor
    http://vimcasts.org/            Screencasts
    https://vim.fandom.com/         Vim Tips Wiki
    https://vi.stackexchange.com/   Stackoverflow for Vi/Vim
    https://vim-adventures.com/     Adventure game using vi keys
    https://neovim.io/              Next generation fork of Vim
    https://spacevim.org/           Preconfigured Vim distribution





































vim: set ts=4 sw=4 et nospell:
