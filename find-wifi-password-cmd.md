# How To Find Wi-Fi Password Using CMD Of All Connected Networks?

Run these CMD commands below to find saved WiFi passwords.

## How to find WiFi password on Windows 10 using CMD?

Open the command prompt and run it as administrator.

In the next step, we want to know about all the profiles that are stored on our computer. So, type the following command in the cmd:

```cmd
netsh wlan show profile
```
This command will list out all the WiFi profiles that you have ever connected to.

Type the following command to see the password of any WiFi network:

```cmd
netsh wlan show profile WiFi-name key=clear
```

Under the security settings, in the ‘key content’, you see the WiFi password of that particular network.

Besides knowing the Windows 10 WiFi password, you can also use this result to optimize your WiFi further. For example, Under the profile information, you can see mac randomization is disabled. You can turn on the MAC randomization feature to avoid your location tracking based on the device’s MAC address.

## Enable MAC Randomization on Windows 10

Each device has a unique MAC address, which can be used to identify it on a network. MAC randomization helps protect your privacy by hiding the original MAC address and preventing hackers from tracking your device on public networks. Here's how to enable MAC randomization on Windows 10:

1. Open the **Settings** menu and select **Network & Internet**.
2. Click on **Wi-Fi** in the left pane, and then choose the **Advanced options**.
3. Look for the **Random Hardware Address** setting and turn it on. Note that this feature may not be available if your wireless hardware does not support it.
4. Once enabled, your device will use a random MAC address when connecting to Wi-Fi networks, ensuring better privacy and security.

By enabling MAC randomization, you can protect your identity and make it harder for unauthorized parties to track your device while using public Wi-Fi networks.


## How To Find Wi-Fi Password Through LAN Using CMD

Here’s how you can find the Wi-Fi password through LAN using the Windows command line.

1. Fire up the Command Prompt.
2. Copy and paste the following command and hit enter.

```cmd
mode con lines=60
netsh wlan show profile name="LAN Name" key=clear
```

Rename “LAN Name” to your LAN’s name and hit enter. This works for both Wi-Fi and LAN.

3. You can find the password in the “Security settings” section.

## How to Check Wi-Fi Passwords of all devices at once

To check the Wi-Fi passwords of all the devices that you ever connected to your computer, copy and paste the following command in the terminal and hit enter.

```cmd
for /f "skip=9 tokens=1,2 delims=:" %i in ('netsh wlan show profiles') do @echo %j | findstr -i -v echo | netsh wlan show profiles %j key=clear
```

