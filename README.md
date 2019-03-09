Vim introduction – Editing at the speed of thought
==================================================

Introduction talk about the text editor [Vim] aimed at IT people who probably
heard about Vim already but never got around to try it seriously. The talk is
meant to show off the most important features rapidly in about 1 hour
presentation.  Hopefully it gets people interested in Vim or at least let them
understand why one would use it.

The presentation is meant to be held using Vim itself, so all features can be
demonstrated live.

[Vim]: https://www.vim.org/


How to present
--------------

Open [vim-intro.md](vim-intro.md) in Vim in a fullscreen terminal. Increase the
font size such that at least 80 × 25 characters are visible.

The presentation contains form feed characters `^L` to delimit slides. As you
may know you can use `]]` and `[[` to jump to the next or previous section in
Vim. So to go to the next slide you could press `]]` to jump to the next `^L`,
`j` to move one line down such that `^L` will not be visible on screen and
finally `z<Enter>` to move the line with the cursor to the top of the screen.

Map the following keys to navigate the slides backward and forward with `<F2>`
and `<F3>`:

    :map <F3> ]]jz<CR>
    :map <F2> k[[z<CR>

Additionally you may run a tool like [screenkey] which displays your keypresses
to the audience.

[screenkey]: https://gitlab.com/wavexx/screenkey
