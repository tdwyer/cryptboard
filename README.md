Cryptboard
==========

Cryptbaord - A X11 Encrypted Clipboard Manager


Encrypt primary selection or stdin with GnuPG and send to X11 Clipboard. Cryptboard also verifies the clipboards digital signature before pasting.

`cryptboard --paste` uses `xdotool type` to **Type** the decrypted clipboard to cursor position *(As Seen in on TV)*. A pleasant side effect of this is that it can paste into VNC windows without clipboard sharing.


### Dependencies


* **GnuPG** - For encryption and decryption
* **xclip** - For X11 clipboard input and output
* **xdotool** - For typing decrypted Cryptboard to cursor position


Command Options
---------------


`cryptboard [OPTION] [-r recipient]`

* -i, --stdin   :Read from stdin
* -o, --stdout  :Pipe to stdout
* -c, --copy    :Encrypt primary selection to clipboard
* -p, --paste   :Decrypt clipboard to cursor position
* -d, --delete  :Delete all the things
* -r  recipient :Email address associated with the PGP key to encrypt to. `This flag can be used multiple times`


### Shortened Names


**Cryptboard** is a long name. However, you can use symbolic links to `cryptboard` to preform the same actions.


`ln -s /usr/bin/cryptboard cb-[OPTION]`

* cb-i    :Read from stdin
* cb-o    :Pipe to stdout
* cb-c    :Encrypt primary selection to clipboard
* cb-p    :Decrypt clipboard to cursor position
* cb-d    :Delete all the things


Set these keyboard bindings in your DE or WM
--------------------------------------------


It is best to not stomp on the `Ctrl+C` and `Ctrl+V` key-combos. You will want them for the bonus features.


* `Super+C` = `cryptboard --copy`
* `Super+V` = `cryptboard --paste`
* `Super+D` = `cryptboard --delete`


Create OpenPGP ASCII armor message
----------------------------------


Highlight the text with your mouse and copy with `cryptboard -c`. You'll want to add one or two `-r email_addr` declaring who you want to be able to decrypt the message.


    $ cryptboard -c -r alice@example.com -r bob@example.com


Paste encrypted message with `Ctrl+V` or select *Paste* from right-click menu


Steps to Decrypt OpenPGP ASCII armor message
--------------------------------------------


* **First** Highlight encrypted message with your mouse and hit `Ctrl+C`
* **Then**  Decrypt `cryptboard -p`


Pipe Secrete Messages into and out Cryptboard
-----------------------------------------------


One of the very handy features of **Cryptboard** is it's support for *Piping*. With it you can *pipe* your decrypted message directly to a file, or where ever. You can also pipe a message into **Cryptboard** and use the normal `Ctrl+V` to paste the encrypted message block into a website form, email, IM, StasiBook post, or anywhere.


Technically you can *pipe* sexy photos into Cryptboard and paste the OpenPGP ASCII Armor Message on your wifes StasiBook page.


    cat porkNbeans.jpg | cryptboard -i


Then your wife can copy the encrypted message and decrypt to an image file.


    cryptboard -o > beans.jpg

