Cryptboard
==========

Cryptbaord - A X11 Encrypted Clipboard Manager


Encrypt stdin, primary selection, or pinentry<Via pish> with GnuPG and send to X11 selection Clipboard


Helpful keybindings
-------------------

Encrypt the test you highlighted with your mouse to Clipboard. Then clear primary selection.
    Ctrl-C = cryptboard -s


Pipe Clipboard contents into GnuPG to decrypt and pipe into xdotool to type to current mouse position
    Ctrl-V = cryptboard -p


Open pinentry with `pish` pipe pinentry stdout to GnuPG stdin and pipe that to X11 Clipboard
    Ctrl-A = cryptboard -a

