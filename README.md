Cryptboard
==========

Cryptbaord - A X11 Encrypted Clipboard Manager


Encrypt stdin, primary selection, or **pinentry** via [pish](https://github.com/tdwyer/pish "pish") with GnuPG and send to X11 selection Clipboard. Cryptboard also brings strong integrity checking to your clipboard by signing your clipboard and verifying the signature before pasting.

`cryptboard --paste` uses `xdotool type` to send decrypted clipboard to cursor position. A pleasant side effect of this is that it can paste into VNC windows without clipboard sharing.


### Dependencies


* **GnuPG** - For encryption and decryption
* **xclip** - For X11 clipboard input and output
* **xdotool** - For typing decrypted Cryptboard to cursor position
* **[pish](https://github.com/tdwyer/pish "pish")** - For pinentery to Cryptboard


Command Options
---------------


- `cryptboard -i`   :Read from stdin, or `--stdin`
- `cryptboard -a`   :Ask with pinentry via pish, or `--ask`
- `cryptboard -c`   :Encrypt primary to clipboard, or `--copy`
- `cryptboard -p`   :Decrypt clipboard and type to cursor position, or `--paste`
- `cryptboard -d`   :Delete all the things, or `--delete`



Set these Helpful keybindings in your DE/WM
-------------------------------------------

Encrypt the test you highlighted with your mouse to Clipboard. Then clear primary selection.


    Super-C = cryptboard -c


Pipe Clipboard contents into GnuPG to decrypt and pipe into xdotool to type to current mouse position


    Super-V = cryptboard -p


Delete all selections, and delete the X11 Clipboard 10 times by default to overflow clipboard buffer


    Super-D = cryptboard -d


Pipe to Cryptboard
------------------


Pipe to Cryptboard to encrypt into your X11 clipboard


    echo "encrypt me" | cryptboard -i


Paste ASCII Armor Encrypted GPG Message
---------------------------------------


Your clipboard has the contents already in OpenPGP ASCII armor message format. There are no more excuses not to encrypt all the tings. Privacy is just a click away.


    Ctrl+V or Right-Click select Paste


Bam! IM me :)


        -----BEGIN PGP MESSAGE-----
    Version: GnuPG v2.0.22 (GNU/Linux)

    hQIMA5srMV1XK+PwAQ/+KTEak5NCfKd2fEt2onSwbkLfXf8dmX25y2eo9pChTbrn
    wIFQpaXSwWYjx4Brqo6ZqYrR+Eh2qT7vK0KqyziIG9DDYyV84KJRbSkp6O7dxnSm
    FMqwKPo4jF2ubvdSTFi9nBCBgeMYTGRFcx2KS3nOgI12OJa68rA32vAyBkWu+2ap
    fiSFJQm8UmDh80t8N1xknBIVqTF+2egOQNfj24wRT19/uJDS3Cq5lFUJlZPDXgmQ
    p7y33nNQIvtS963Jb00IEN8Xv++PvI9+aIDZl813nq7QhFnbwd+whBmFPY4HGykd
    NW4PvaHJ081f/RkYkg9Wx16YaxaaLGxSmtg+q0Rdk+foW5YFKORaCS+7DAV8TDUq
    X04t7nguQrTXKgPjDwWmOlnJZ5kedL7XNxp1jbJtJZiKvsvP5BP5n5mbVUyaLkfR
    cgWvhIQQuU38/ov4EkqJRkygd+i8Q86mwhAmbFN1KTR7jbH1WjySLnERPO2oEzZX
    U4dQBaRQ1wFVDO0F6UCBcS6C+7bhlBa9UY9f9t7VKlXAbDD7vc/XrTp9Daq86ofl
    v/VPTanToGHkBvmNP0HFiTVfYMnxytf/G23rVuYYGX5Dy6invttH6zu2AKFXAqEY
    zsd0afMIl4gXjwgN6cprD1VzaRJxwZfWIA/K7gCFXXMBX9N60ll9IWjtkjAEgpTS
    6QGr0Je2ZLf0ph0n4K92E/u5sFvWmQMrVA7bO3n2+zsHacMqcBycHfGSCvD9sArY
    v867YNq5CSE1jh3oaCkHJtGFAwl3YHWaO9Em+ss91dkEvGC/KWoQ4FzwoqkXnhLJ
    jtyZ3IvMSQFs8N8qh60ng7SPHOeQ7mWm5BKmcezot4g31dXIu6nI1U76LQ5hHivM
    7ZuNG/pTk7bXG7SQaO7lfi0hNnUY8jDNUgWSI15Mp3lHbU7nfIKbjJhy+rXYU3i4
    tWVo3qewJKi53Ash20J/2MYmk823AoM3hLs03IPHMB/njwiyCIm4vxzHGYuQRdBu
    +lKoHLH+FBvJXH19A8LbwoVG40gPLWTlVC8ZtljlCuzWjw4ckZmr0tm3wBShH87T
    YjhBil2UGzufNaYF2qJOhiqZGC038pB+i1lVay0xAedKV5m7g6FaBefcBi/Ae9Y/
    VEnUrU433h11XliCzhqqJSAyNCGrip9vsij1zJvJWphmIbUrKA4PnXHftcafX0It
    Q0kcNK3j5iRApyRvldhEvXRv9sZjf39UDxenF8d4g/vfiQJGJDKaUnAlHHgE5qDJ
    LjqUV8wqSd0n04XA5MHQ2CNZOPnPeqkdqUVeb7l01k+9tTi2kd9OcG7QdZXEu54o
    zzZ3TZZ92oemT9rpLQMZJTyVI7MaVsGdfeftWtlKwGutwIvOl3M9BRqPHQIoNkfX
    7J7nzu1V8VLf/jqH1d98aJMMadJUqmhjalv+IDsWFnNDmYCh0StXcDta4GLBYRYh
    UgqPuDppBGaWceNpEA4lbT7GSU+1CFv+t17f9j9xwmZgOUF/OGcymAUBMT2JvZgW
    3Y+2dYnBl0TXoZQFZYhzlIJj/u/bXzX5rKIHqyjuXm5NCLcRX+hvPAqbEN694a6m
    rp1dflLypOWNT4lkM1MTwooBVHpAohltkICIjjwC7aLxsNBJzE5hjleNJSi0zT2a
    9y8eAb6ydt3qFN0LepDPsBSfsEFBEeipDqikgx3hlxvFuhQc2Tg8nzyMlRYurJsZ
    KWtL/cuwqV0TQrSqJnwquvbxTAG0K/F5Ls0TKQHsNngdCik56rj+fiofO2rDtZSJ
    Z92dnAuNr63eG0/0PvhEO8tmmt61laWnI8Ecu9h9
    =2Z0k
    -----END PGP MESSAGE-----


Decrypt GPG Encrypted Messages
------------------------------


You can copy a GPG encrypted message block to your clipboard line normal `Ctrl+C`. Then `cryptboard -p` will *type* the decrypted message to your cursor position.


    Cryptboard not only secures your clipboard,
    but it also makes gpg easier to use.

