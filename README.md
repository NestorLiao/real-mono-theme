Real mono themes
==================
Just A Real Mono Theme

## Feels:
A collection of real monochrome emacs themes in a couple of variants.

![real-mono-white](https://raw.githubusercontent.com/qingsongliao/real-mono-themes/main/image/real-mono-white.png)
![real-mono-black](https://raw.githubusercontent.com/qingsongliao/real-mono-themes/main/image/real-mono-black.png)
![real-mono-girl](https://raw.githubusercontent.com/qingsongliao/real-mono-themes/main/image/real-mono-girl.png)
![real-mono-oldfastion](https://raw.githubusercontent.com/qingsongliao/real-mono-themes/main/image/real-mono-oldfastion.png)

pic's font list: bookerly, ubuntumono, firacode,

## Features:
1. **Not Greyscale**, no blur anymore, it's much better to let eink for pure black and white!
2. **Easy** to customize, can set the only two colors by config the default face's foreground/background color.
3. **Distraction-free**, no extra info-overwhelming causing by font-lock in progn-mode, just have few diversity in magit/dired etc for better function recognize.
4. **Full**, configed 360+ faces, I didn't see monochrome theme have so many faces, and my daily driver.

## Tips for more mono:
1. global-hide-mode-line-mode, build your own brain memory
2. no-emoji, alter emacs to be "text editor" instead of discord
3. fringe specific mode auto hide
4. turn off show-paren-mode, build your own eye insight
5. window-divider-mode, too, build your memory
6. font switch, switch between proportion font and mono font
7. display-line-numbers-mode, too, build your own eye insight

Installation
============


Use package
-----------
If you have use-package setup on your system loading real-mono-themes is as simple as:

```lisp
(use-package real-mono-themes
  :config
  ;; (load-theme 'real-mono-black t)
  ;; (load-theme 'real-mono-girl t)
  ;; (load-theme 'real-mono-oldfasion t)
  (load-theme 'real-mono-white t))
```

Manual installation
-------------------
If you prefer, you can install real-mono-themes manually by downloading the elisp files in this repo and place them somewhere in your <code>load-path</code> and <code>custom-theme-load-path</code> (see example below).

You can set your paths by adding these lines to your <code>.emacs.d</code> or <code>.emacs.d/init.el</code>:

```lisp
;; Put the main theme file real-mono-themes.el in your load path
(add-to-list 'load-path "~/.emacs.d/elisp")

;; Put the induvidual theme files real-mono-{black, white, etc.}-theme.el in your theme load path
(add-to-list 'custom-theme-load-path "~/.emacs.d/themes")
```

You should now be able to load real-mono-themes with <code>M-x load-theme RET real-mono-{black, white, etc.} RET</code>!


Thanks For
-------------------
minimal-emacs, bring me into emacs world
paperlike-go, without it i will never use sway with eink screen
eink-theme, without it i will never use emacs with eink screen
almost-mono-theme, because it's "almost"-mono not "real"-mono
