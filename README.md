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

pictures's font list: bookerly, ubuntumono, firacode, terminess, bookerly blod ltalic.

## Features:
1. **Not Greyscale**, no blur anymore, it's much better to use eink screen for pure black and white!
2. **Easy** to customize, can set the only two colors by config the default face's foreground/background color.
3. **Distraction-free**, no extra info-overwhelming causing by font-lock, only few font diversity in magit/dired etc for better function recognize.
4. **Full**, configed 370+ faces, I didn't see any monochrome theme can reach that much, as my daily driver, it's good enough.

## Tips for mono:
- (global-hide-mode-line-mode 1), build your own brain memory
- (no-emoji 1), alter emacs to be "text editor" instead of discord
- (show-paren-mode -1), build your own eye insight
- (window-divider-mode  -1), too, build your memory
- (display-line-numbers-mode -1), too, build your own eye insight
- font switch, switch between proportion font and mono font
``` lisp
(defvar my-alternate-font "-DAMA-UbuntuMono Nerd Font-regular-normal-normal-*-13-*-*-*-m-0-iso10646-1")
(defvar my-default-font "bookerly")
(defvar fontfont 1)
(defun my-toggle-font ()
  "Toggle between UbuntuMono and bookerly fonts."
  (interactive)
  (if (= fontfont 1)
      (progn (set-face-attribute 'default nil :font my-default-font :height 160) (setq fontfont 0))
    (progn (set-face-attribute 'default nil :font my-alternate-font :height 210) (setq fontfont 1))))
```

- fringe specific mode auto hide
``` lisp
(defun my-set-fringe-face ()
  "auto hide fringe face depending on major mode."
  (if (derived-mode-p '(occur-mode gud-mode))
      (set-face-attribute 'fringe nil
                          :background (face-attribute 'default :background)
                          :foreground (face-attribute 'default :foreground))
    (set-face-attribute 'fringe nil
                        :background (face-attribute 'default :background)
                        :foreground (face-attribute 'default :background))))
(add-hook 'after-change-major-mode-hook #'my-set-fringe-face)

- elisp for toggling paperlike-hd to swtich between read and watch.
``` elisp
(defvar monitor-state 0
  "Current monitor state, either 0 for read or  1 for watch.")
(defun monitor ()
  "swtich monitor from read mode to watch mode"
  (interactive)
  (let((monitorpath "-i2c  /dev/i2c-4")
       (monitorcli "paperlike-cli ")
       (monitorarg '(" -contrast " " -speed " " -mode " " -clear"))
       (mode-state '(("9" "5" "1")  ("2" "1" "3"))))
    (split-window-below)
    (other-window 1)
    (switch-to-buffer "*Shell Command Output*")
    (split-window-below)
    (other-window 1)
    (switch-to-buffer "*Async Shell Command*")
    (progn
      (dotimes (number 3)
        (shell-command (concat
                        monitorcli
                        monitorpath
                        (car (nthcdr number monitorarg))
                        (car (nthcdr number (car (nthcdr monitor-state  mode-state)))))
                       ))
      (sleep-for 1))
    (setq monitor-state  (if (= 0 monitor-state) 1 0 ))
    (sleep-for 1.5)
    (sleep-for 0.5)
    (async-shell-command (concat monitorcli monitorpath " -clear"))
    (let ((async (get-buffer-window "*Async Shell Command*"))
          (shell (get-buffer-window "*Shell Command Output*")))
      (when async (delete-window async))
      (when shell  (delete-window shell)))
    (sleep-for 0.5)
    (kill-buffer "*Async Shell Command*")
    (kill-buffer "*Shell Command Output*")
    (donothing)))
```

Installation
============

Manual installation
-------------------
You can install real-mono-themes manually by downloading the elisp files in this repo and place them somewhere in your <code>load-path</code> and <code>custom-theme-load-path</code> (see example below).

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
- minimal-emacs, a easy use config which bring me into emacs world.
- eink-theme, without it I will never try emacs with eink screen.
- paperlike-go, without it I will never try sway/linux with eink screen.
- almost-mono-theme, because it's "almost"-mono not "real"-mono, so I creat this real-mono-theme.
