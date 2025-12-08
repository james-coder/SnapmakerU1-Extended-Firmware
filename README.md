# Snapmaker U1 Extended Firmware (Unofficial)

> **Unofficial — use at your own risk.**
> **May void your warranty.**
> **Intended not to contain any Snapmaker proprietary files.**

This is a community project and is **not** affiliated with, endorsed by, or supported by Snapmaker.

Installing custom firmware can cause **printer damage, loss of data, or fire**.  
You are solely responsible for anything that happens to your printer, your property,
or yourself when using this project.

---

## What this project is

**Snapmaker U1 Extended Firmware** is a toolkit that:

- Downloads an official Snapmaker U1 firmware update from Snapmaker’s servers.
- Unpacks it on your machine.
- Applies overlays and modifications (configs, services, OSS components).
- Repackages the result into a firmware update you can flash to your U1.

The repository itself contains **only**:

- Scripts, configuration files, and overlays created by this project.
- Build tooling needed to unpack, patch, and repackage firmware.
- Documentation.

It **does not** include any original Snapmaker proprietary firmware components.

Snapmaker U1 is known to run a modified stack of:

- **Klipper** firmware (GPL‑3.0)
- **Moonraker** API server (GPL‑3.0)
- **Fluidd** web UI (GPL‑3.0)

This project sits on top of that stack and adds functionality while trying to respect
upstream licenses and Snapmaker’s terms.

---

## Features

### Basic firmware overlay

- **SSH access** (root & user accounts) for debugging and advanced configuration.
- **USB Ethernet support** for hot‑plug network adapters.
- **Persistent data** across firmware updates (configs, keys, etc.).
- **Fluidd UI auto‑enable** on the U1 controller.

### Extended firmware overlay

Includes everything in *Basic* plus:

- **On‑board camera support** with hardware‑accelerated streaming.
- **USB camera support** for external webcams.
- **WebRTC low‑latency video** in Fluidd for remote monitoring.
- **Custom Klipper / Moonraker includes** via Fluidd.
- Updated Fluidd with timelapse features.

See the docs in `docs/` for details and current versions.

---

## Safety, risk, and warranty

3D printer firmware is **safety‑critical**. By using this project you acknowledge:

- Prints may fail or behave unpredictably.
- Safety features (thermal runaway, toolchanging, etc.) can be impacted.
- Hardware could be damaged or destroyed.
- There is a non‑zero risk of **fire** or other property damage.

Snapmaker explicitly states that:

- Third‑party firmware may break functionality or damage the machine.
- Installing unofficial firmware **voids your warranty**.
- They accept no liability for failures caused by modified firmware.

The maintainers and contributors of this project:

- Provide the code **“as‑is” with no warranty of any kind**.
- Are **not liable** for any damage, data loss, or injury arising from its use.

**If you are not comfortable with these risks, do not install this firmware.**

---

## Installation (high‑level)

Full step‑by‑step instructions live in `docs/installation.md`,
but the rough flow is:

1. **Fetch official firmware**

   - Download the latest U1 firmware `.bin` from Snapmaker’s official support site,
     or provide a URL and let the scripts fetch it for you.
   - Place it in the `firmware/` directory, or configure the path in `vars.mk`.

2. **Build a custom image**

   ```bash
   make overlay-basic    # or overlay-extended, etc.
   ```

   This will:
   - Unpack the official firmware.
   - Apply the selected overlays.
   - Repack a custom `.bin` into `dist/` (or similar).

3. **Flash to the printer**

   - Copy the generated `.bin` to a USB drive.
   - Use the U1 touchscreen → Firmware Update menu to apply it.
   - Expect warnings about unofficial firmware and warranty.

4. **Verify**

   - Confirm the printer boots normally.
   - Test SSH access, Fluidd, camera, etc. as described in the docs.

If anything looks wrong: **stop printing immediately** and reflash the official
Snapmaker firmware.

---

## Legal / licensing

> **Note:** The following is a high-level summary and is **not legal advice**.
> If you need certainty about your rights or obligations, talk to a lawyer.

### Project license (this repo)

All original code, scripts, overlays, and documentation in this repository are
licensed under the **GNU General Public License, version 3.0 only (GPL‑3.0‑only)**,
unless a file or subdirectory explicitly states otherwise.

See `LICENSE` for details.

### Upstream open‑source components

This project interacts with, or may build against:

- **Klipper** firmware — GPL‑3.0
- **Moonraker** API server — GPL‑3.0
- **Fluidd** web UI — GPL‑3.0

Those projects remain under their respective licenses and copyrights.
Nothing here changes their terms. Where this project distributes modified versions
of those components (e.g. patched configs, additional modules, rebuilt binaries),
it does so under GPL‑3.0 and will provide the source or build scripts needed to
reproduce them.

### Snapmaker firmware and proprietary components

- The official U1 firmware image you download from Snapmaker combines GPL components
  and proprietary Snapmaker software (GUI, services, cloud integration, etc.).
- Snapmaker’s terms generally grant you a personal, non‑transferable license to
  use those proprietary parts on Snapmaker devices and may restrict copying,
  modification, and redistribution.

This project:

- Does **not** include any Snapmaker proprietary files in the repo.
- Treats the official U1 firmware as an **external input** you obtain under
  Snapmaker’s terms.
- Licenses only this project’s own code and assets under GPL‑3.0‑only.

By default, this project expects users to **build firmware locally** from an
official Snapmaker U1 firmware image they download under Snapmaker’s terms.

If pre‑built firmware images produced by this project are distributed, they may
embed Snapmaker proprietary components. Those parts remain governed by Snapmaker’s
terms; this project’s GPL applies only to the portions derived from this repo and
other GPL sources. For questions on redistribution of such images, consult Snapmaker
or a qualified lawyer.

---

## Contributing

Contributions are welcome!

By submitting a pull request, you agree that:

- Your contribution is your original work (or you have the right to contribute it).
- You license your contribution under **GPL‑3.0‑only**, the same as this project.
- The project may redistribute your contribution as part of GPL‑licensed releases,
  including pre‑built firmware images.

See `CONTRIBUTING.md` for the full contributor terms and coding guidelines.

---

## Acknowledgements

- **Snapmaker** — for the U1 hardware and firmware.
- **Klipper, Moonraker, Fluidd** — for the open-source stack this project builds upon.
- Everyone in the community who tests, reports issues, and sends patches.

## Support

If you find this project useful and would like to support its development, you can:

[![Buy Me A Coffee](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://buymeacoffee.com/paxx12)

## License

See `LICENSE` for the full terms.

Snapmaker® is a trademark of Snapmaker. Any use of the name here is for
identification and compatibility purposes only.
