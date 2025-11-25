Real mono themes
==================
Real Mono Theme, two colors are enough for emacs.

## Feels:
A collection of real monochrome emacs themes in a couple of variants.

![real-mono-eink](https://raw.githubusercontent.com/NestorLiao/real-mono-themes/main/image/real-mono-eink.png)
![real-mono-dark](https://raw.githubusercontent.com/NestorLiao/real-mono-themes/main/image/real-mono-dark.png)
![real-mono-girl](https://raw.githubusercontent.com/NestorLiao/real-mono-themes/main/image/real-mono-girl.png)
![real-mono-old](https://raw.githubusercontent.com/NestorLiao/real-mono-themes/main/image/real-mono-old.png)
![real-mono-sea](https://raw.githubusercontent.com/NestorLiao/real-mono-themes/main/image/real-mono-sea.png)

Pictures's font list: Bookerly, UbuntuMono, FiraCode, Terminess, Bookerly blod ltalic.

## Features:
1. **Not Greyscale**, no blur eyesight anymore, pure black/white and  pure soul!
2. **Easy to customize**, only need to change default face's foreground/background color.
3. **Distraction-free**, no info-overwhelming causing by font-lock, font diversity only in  magit/dired/diff etc for better function recognize.
4. **Full**, configed 410+ faces, I didn't see any monochrome theme can reach that much, as my daily driver, it's good enough.

## Tips for mono:
- (global-hide-mode-line-mode 1), build your *own* brain memory.
- (window-divider-mode  -1), too, build your *own* brain memory.
- (no-emoji 1), alter emacs to be "text editor" instead of reddit.
- (show-paren-mode -1), build your *own* eye insight.
- (display-line-numbers-mode -1), too, build your *own* eye insight.
- font switcher/hide fringe by mode... etc.
- setq hl-todo-keyword-faces

Installation
============

Use package
-----------
If you have use-package setup on your system loading real-mono-themes is as simple as:

```lisp
(use-package real-mono-themes
  :config
  ;; (load-theme 'real-mono-dark  t)
  ;; (load-theme 'real-mono-girl t)
  ;; (load-theme 'real-mono-old t)
  (load-theme 'real-mono-eink t))
```

Manual installation
-------------------
You can install real-mono-themes manually by downloading the elisp files in this repo and place them somewhere in your <code>load-path</code> and <code>custom-theme-load-path</code> (see example below).

You can set your paths by adding these lines to your <code>.emacs.d</code> or <code>.emacs.d/init.el</code>:

```lisp
;; Put the main theme file real-mono-themes.el in your load path
(add-to-list 'load-path "~/.emacs.d/elisp")

;; Put the induvidual theme files real-mono-{dark, eink, etc.}-theme.el in your theme load path
(add-to-list 'custom-theme-load-path "~/.emacs.d/themes")
```

You should now be able to load real-mono-themes with <code>M-x load-theme RET real-mono-{dark, eink, etc.} RET</code>!

If you hate eyecandy colors too and found color face this package missed or you think can add slant/weight/underline/box, etc(except colors) to faces for better identify, welcome to PR! Let's creat a two-color-mode for "Free emacs from the slave of colors".

Thanks For
-------------------
- minimal-emacs.d, a easy to use config that bring me into emacs world.
- eink-theme, without it I will never try emacs with eink screen.
- paperlike-go, without it I will never try sway/linux with eink screen.
- almost-mono-theme, because it's "almost"-mono not "real"-mono, so I creat this real-mono-theme.
