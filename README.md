# Lenovo Keyboard Backlight Illumination
Powershell scripts for Lenovo compatible with Lenovo laptops which use Lenovo System Interface Foundation to activate the backlight. Tested using ThinkPad E580

## Requirements
- [Lenovo System Interface Foundation](https://pcsupport.lenovo.com/es/es/downloads/ds105970-lenovo-system-interface-foundation-for-windows-10-32-bit-64-bit-thinkpad-thinkcentre-ideapad-ideacentre-thinkstation)
- [auto-keyboard-backlight.ps1](https://github.com/MundeepL/LenovoKeyboardBacklight/blob/main/auto-keyboard-backlight/auto-keyboard-backlight.ps1) (enables or disables the keyboard backlight)

## Usage:
- Run script with Powershell 32-bit (x86) located '**C:\Windows\syswow64\WindowsPowerShell\v1.0\powershell.exe**'

## Installation
If you want to schedule the script, we'll need to do this with task scheduler. This will cover:
- Boot
- Sleep & wakeup
- Hibernation & wakeup

To schedule with Task Scheduler:
1. Click '**Create Task**'.
2. Choose '**Run whether user is logged in or not**'. (ensure user that executes this script has necessary permissions)
3. Add a trigger '**At startup**'.
4. Add a trigger '**On an event**' if you want to support sleep and hibernation. You'll need to find the EventID in Windows Event Manager.
    1. Log: 'System'
    2. Source: 'Power-Troubleshooter'
    3. EventID: 1
5. Add an action with '**Program/script**' location set to '**C:\Windows\syswow64\WindowsPowerShell\v1.0\powershell.exe**' and parameters '**-File "path\to\script\auto-keyboard-backlight.ps1"**'

## Note
You may need to either adjust the Powershell execution policies or sign the Powershell script if you plan on safely deploying this in your company.

## Supprt the original creator
- [PayPal](https://www.paypal.com/pools/c/create/share/8xukwldAVK)
