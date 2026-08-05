# Module 2

## Inside of a computer

```mermaid
graph LR
A[Press Power Button] --> B[Firmware Starts] --> C[POST] --> D[Select Boot Device] --> E[Start bootloader]
```
- Step 1: When we press the start button, a signal is sent to the PSU(Power Supply Unit) to allow power to flow.
- Step 2: The UEFI(Unified Extensible Firmware Interface) co-ordinates with all the components initializes & starts them, this is the first software to run.
- Step 3: UEFI runs POST(Power-On Self Test) to check that required hardware is present, configured, and functioning. Errors trigger beeps or alerts.
- Step 4: UEFI follows a priority list to determine which device to boot from - typically an SSD or HDD with the OS installed.
- Step 5: The bootloader loads the OS into the RAM, the UEFI then hands over the controls to the OS, completing the sequence.