<p align="center">
  <img src="https://avatars.githubusercontent.com/u/115064778?v=4&size=252" alt="MamboDMA Logo" width="128"/>
</p>

<h1 align="center">MamboDMA</h1>

<p align="center">
  Free, open-source DMA overlay engine with multi-game support.
</p>

<p align="center">
  <a href="https://github.com/DMAEngine/releases/latest">Download Latest Release</a>
  &nbsp;&middot;&nbsp;
  <a href="https://t.me/DMAEngine">Telegram</a>
</p>

---

## About

MamboDMA is a standalone DMA overlay tool built for FPGA-based DMA hardware. It ships as a single portable executable -- no installation, no .NET SDK, and no build tools required. Just extract and run.

The application provides a clean Game Hub where you select your game, and the engine handles DMA initialization, process detection, and attachment automatically.

---

## Supported Games

| Game | Status |
|---|---|
| Arena Breakout Infinite | Fully Supported |
| Counter-Strike 2 | Fully Supported |
| Delta Force | Coming Soon |

Additional games will be added over time.

---

## Features

- **Automatic Setup** -- DMA initialization, game detection, and process attachment are handled for you. No manual configuration needed on first launch.
- **ESP Overlay** -- Per-game ESP with player boxes, names, distance, health, and skeleton rendering where applicable.
- **Web Radar** -- Built-in web radar for Arena Breakout Infinite, accessible from any device on your local network.
- **Input Support** -- Makcu device integration for hardware-level input forwarding.
- **UPnP Port Mapping** -- Automatic port forwarding for radar and network features.
- **Per-Game Configs** -- Settings are saved per game in `%AppData%\MamboDMA` and persist between sessions.
- **Lightweight** -- Single-file executable with minimal resource usage. Runs on any modern Windows machine with a compatible DMA device.

---

## Requirements

- **OS** -- Windows 10 or Windows 11 (64-bit)
- **Hardware** -- FPGA-based DMA device (e.g. Squirrel, CaptainDMA, etc.)
- **Firmware** -- Device must be flashed and functional
- **GPU** -- Any GPU with DirectX 11 support

No .NET runtime installation is required. The release is fully self-contained.

---

## Getting Started

1. Download the latest release from the [Releases](https://github.com/DMAEngine/releases/latest) page.
2. Extract the `.zip` to any folder.
3. Run `DMAEngine.exe`.
4. Select your game from the Game Hub.
5. The engine will initialize your DMA device, wait for the game process, and attach automatically.

That is it. Once attached, the overlay will appear and ESP features activate based on your game's configuration.

---

## Configuration

All settings are stored in:

```
%AppData%\MamboDMA\<GameName>\config.json
```

You can modify ESP toggles, colors, distances, and keybinds through the in-app settings panel. Changes save automatically.

---

## Folder Structure

After extracting, your folder should look like this:

```
DMAEngine/
    DMAEngine.exe          Main executable
    Assets/                Fonts, icons, radar assets
    vmm.dll                VMM library
    leechcore.dll          LeechCore library
    FTD3XX.dll             FTDI driver
    (other native DLLs)
```

Do not remove any `.dll` files from the folder. They are required for DMA communication and rendering.

---

## Troubleshooting

**"DMA device not found"**
Ensure your FPGA device is connected, powered, and has working firmware. Check Device Manager for the FTDI device.

**Overlay not appearing**
Run `DMAEngine.exe` as Administrator. Some games with anti-cheat may require elevated privileges for the overlay to render.

**OBS / Discord not capturing the overlay**
Run OBS or Discord with the same elevation level as DMAEngine. Disable "fullscreen optimizations" on the game executable.

**Antivirus flagging the executable**
This is a false positive caused by the single-file publish and DMA library signatures. Add the folder to your antivirus exclusion list.

---

## Credits

- **Mambo** -- Project author
- **Lone** -- VmmSharpEx
- **Marazm** -- Maps and radar assets

---

## Disclaimer

This software is provided for educational purposes only. The authors are not responsible for how it is used. Use at your own risk and in accordance with applicable terms of service.

---

## Links

- [Telegram](https://t.me/DMAEngine)
- [GitHub](https://github.com/DMAEngine)
