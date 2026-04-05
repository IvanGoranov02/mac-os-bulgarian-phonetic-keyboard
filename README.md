# Bulgarian Phonetic Keyboard Layout for macOS

## Introduction

The **original** Bulgarian Phonetic keyboard layout for macOS was created by **[Kristiyan Velkov](https://www.linkedin.com/in/kristiyan-velkov-763130b3/)** (see also his [Medium article](https://medium.com/kristiyan-velkov/bulgarian-phonetic-keyboard-layout-for-macos-92cf2bae35b7)). That work used **traditional phonetic** placement (Cyrillic aligned with QWERTY letter sounds).

This repository keeps the same project and file names but **updates the `.keylayout` definitions**: the layout files here have been **remapped to match the Bulgarian national (Standard / KBDBULG) letter positions**, with a small set of custom changes on specific physical keys (see **Recent layout changes** below). The input source still appears in macOS as **BG - Phonetic**.

Tested in the latest MacOS version: **macOS 14 Sonoma**

![](./bg-keyboard.png)

## Recent layout changes

The following updates were made on top of Kristiyan’s original layout files in both **`KV-BG - Phonetic.keylayout`** (ANSI) and **`KV-BG - Phonetic ISO.keylayout`** (ISO):

- **National (Standard) mapping.** The main typing layers (plain, Shift, Caps Lock, and the related map used for Caps combinations) were rebuilt so that letters follow the **Bulgarian Standard** arrangement—the same letter-to-key idea as the built-in **Bulgarian** / **Bulgarian – Standard** style layout on macOS and the widespread Windows **KBDBULG** mapping—instead of the older strict “Latin sound → Cyrillic” phonetic grid.
- **Custom § / ч / grave placement (macOS key codes).** On top of Standard, these physical keys were set explicitly:
  - **Key code 10** (the key to the left of `1`, where **§** usually appears on Standard): **ч**
  - **Key code 39** (the key where **ч** sits on Standard, next to Enter): **grave** (**`` ` ``**)
  - **Key code 50** (the key next to the left **Shift** on ISO, often **`` ` ``** on Standard): **grave** (**`` ` ``**)
- **Modifier maps.** The same letter logic was applied consistently across the main **key map indices** used for normal typing (including Shift and Caps Lock). Option-only and Control-heavy layers are mostly unchanged from the original project files; the special Cmd+Shift+Option layer was not fully realigned.
- **Comments inside the `.keylayout` files** note the Standard base and the §/ч/` overrides for maintainers.

If you rely on **comma** and **period** on the same keys as in the old phonetic build, note that on Standard those keys often carry letters (**р**, **л**); punctuation may require **Shift+digits** or other layers, similar to Apple’s Bulgarian Standard behavior.

## Keyboard Layout Variants

The original repository includes two keyboard layout files:

- **`KV-BG - Phonetic.keylayout`** - For standard ANSI keyboards (most US MacBooks and keyboards)
- **`KV-BG - Phonetic ISO.keylayout`** - For ISO keyboards (European MacBooks and external keyboards)

### Which layout should I use?

**Use the ISO layout if:**

- You have a European MacBook or an external keyboard with an **ISO** physical layout (tall Enter, extra key between left Shift and **Z**).

**Use the ANSI (standard) layout if:**

- You have a US-style MacBook or an **ANSI** keyboard (narrow Enter, no extra key next to left Shift).

Pick the file that matches **your hardware**; letter placement in the XML follows the same national mapping in both files, but **scan codes differ** between ANSI and ISO (notably around **key code 10** and **50**), so the wrong file will feel “shifted” on the wrong keyboard.

## Installation on macOS

The layout is a **`.keylayout`** file. macOS loads custom layouts only from your user **Keyboard Layouts** folder (or the system-wide one).

1. **Download the layout file**

   Use either `KV-BG - Phonetic.keylayout` (ANSI) or `KV-BG - Phonetic ISO.keylayout` (ISO), depending on your physical keyboard (see **Which layout should I use?** above).

2. **Put the file in the correct folder**

   Copy the `.keylayout` file into:

   **`~/Library/Keyboard Layouts/`**

   - `~` is your home folder (e.g. `/Users/yourname`).
   - If **`Keyboard Layouts`** does not exist inside **`~/Library/`**, create that folder yourself (Finder → Go → Go to Folder → `~/Library` → New Folder → name it **`Keyboard Layouts`**), then copy the file in.

   Optional system-wide install (for all users on that Mac): copy to **`/Library/Keyboard Layouts/`** (may require an administrator password). Per-user `~/Library/Keyboard Layouts/` is usually enough.

3. **Restart the Mac**

   Log out and back in, or restart, so macOS picks up the new layout.

4. **Add the input source**

   - Open **System Settings → Keyboard → Input Sources**.
   - Click **Edit** or **+**, then at the bottom open **Others**.
   - Select **BG - Phonetic** and click **Add**.

If **BG - Phonetic** does not appear under Others, double-check that the file is really named with the **`.keylayout`** extension, sits inside **`Keyboard Layouts`** (not elsewhere in Library), and that you restarted once after copying.

## iOS and iPadOS

**These `.keylayout` files cannot be installed on iPhone or iPad.** iOS and iPadOS do not read `~/Library/Keyboard Layouts/` and do not support dropping a macOS keyboard layout file into a folder to register a new system keyboard.

What you can do on iPhone/iPad:

- Use Apple’s built-in **Bulgarian** keyboard: **Settings → General → Keyboard → Keyboards → Add New Keyboard → Bulgarian** (choose the variant you prefer if several are listed).
- Or install a **third-party keyboard app** from the App Store if you need a specific layout; that is a separate app, not this repo’s `.keylayout` file.

An **external keyboard** paired with an iPad still uses the iPad’s keyboard software; it does not load macOS `.keylayout` files either.

## Usage

After restarting your Mac and adding the keyboard layout, select **BG - Phonetic** from the input source options in your system menu bar to start using it.

## Developer support

- **This fork (layout updates, bugs in this repo):** [Ivan Goranov on LinkedIn](https://www.linkedin.com/in/ivan-goranov/)
- **Original Bulgarian Phonetic project:** [Kristiyan Velkov](https://www.linkedin.com/in/kristiyan-velkov-763130b3/)

## Support

**Original author (Kristiyan Velkov):** [Revolut](https://revolut.me/kristiyanvelkov) · [Buy me a coffee](https://www.buymeacoffee.com/kristiyanVelkov)

**Maintainer of this fork (Ivan Goranov):** [Revolut](https://revolut.me/ivgoranov) · [LinkedIn](https://www.linkedin.com/in/ivan-goranov/)

## Contributing

Contributions are welcome. Feel free to submit pull requests or open issues for suggestions, improvements, or bug reports.

## Credits

- **Original layout and project:** [Kristiyan Velkov](https://www.linkedin.com/in/kristiyan-velkov-763130b3/) — author of the initial **Bulgarian Phonetic Keyboard** for macOS and the baseline this repo started from.
- **This fork:** [Ivan Goranov](https://www.linkedin.com/in/ivan-goranov/) — remapping to Bulgarian Standard (KBDBULG), custom § / ч / grave placement, README updates, and related changes (see **Recent layout changes**). Tips: [Revolut](https://revolut.me/ivgoranov).

## License

Released under the [MIT License](LICENSE). See the LICENSE file for more details.
