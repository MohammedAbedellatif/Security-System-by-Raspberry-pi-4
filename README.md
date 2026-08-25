# Password-Based Access Control System — Raspberry Pi 4 Port

Personal follow-up project: a re-implementation of the
[PIC16F877A access control system](https://github.com/MohammedAbedellatif/Security-System-by-PIC16f877A)
on a Raspberry Pi 4, in Python — deliberately without a ready-made LCD
library, to understand and implement the hardware control at register/GPIO
level myself.

## Highlights

- Direct control of a 16×2 LCD over GPIO in 4-bit mode, with hand-written
  low-level functions (`lcd_byte`, `lcd_toggle_enable`) — no external LCD
  library used
- Software-based scanning of a 4×3 matrix keypad via GPIO rows/columns
- Password logic with a failed-attempt counter and relay control for the
  unlocked action
- Warning signal and lockout after three failed attempts

## Repository structure

| Folder | Content |
|---|---|
| [`Code`](Code) | `Security System.py` — main script |
| [`Main-Project`](Main-Project) | Project report (PDF) |

## Run

```bash
python "Code/Security System.py"
```

Requires `RPi.GPIO` on a Raspberry Pi with a 16×2 HD44780 LCD and a 4×3
matrix keypad wired as defined at the top of the script.
