
System: MacOS Mojave. Other OS can refer to this as well, as long as the Vim command is changed accordingly.

## Download a Chrome extension called [Markdown preview](https://chrome.google.com/webstore/detail/markdown-preview/jmchmkecamhbiokiopfpnfgbidieafmd).

Download this extension and check "Allow access to file URLs" in chrome://extensions listing.

## Map a key in Vim to pen the file with Chrome

I map `<F5>` to a command that saves the current file and open it in Chrome:


```
autocmd BufEnter *.md exe 'noremap <F5> :w <bar> silent ! /Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome %:p<CR>' 
```
