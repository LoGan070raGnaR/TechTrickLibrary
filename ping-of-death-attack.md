# Ping of Death Attack - CMD and Notepad Method

## Introduction

In this guide, we will explore the Ping of Death attack, a type of Denial of Service (DoS) attack that takes advantage of vulnerabilities in computer systems. It involves sending oversized and malformed ping packets to the target system, which can cause system crashes and potential security breaches. Please note that this guide is for educational purposes only, and performing such attacks without proper authorization is illegal.

## What is a Ping of Death Attack?

A ping packet is typically a small data packet used to check the connectivity between devices on a network. However, in a Ping of Death attack, the ping packet is deliberately crafted to exceed the normal size limit. By sending an oversized and malformed ping packet to a target system, the attacker aims to exploit vulnerabilities in the system's handling of such packets.

## How Ping of Death Attack Works?

Not all computers can handle data larger than a fixed size. When a ping packet of unusually large size is sent from a source computer to a target machine, it gets fragmented into smaller groups of packets during transmission. Each fragment is typically 8 octets in size. However, when these packets reach the target computer, they arrive in pieces.

The target computer attempts to reassemble the malformed packets received in chunks. However, the process of reassembly can cause buffer overflow at the target computer. Buffer overflow occurs when the data exceeds the memory allocated for it, potentially leading to system crashes or instability.

Once the target system becomes more vulnerable to attack due to the buffer overflow, it may allow further attacks, such as injecting a trojan horse or executing arbitrary code on the target machine.

## Performing the Ping of Death Attack using CMD

1. Open the Command Prompt on your Windows system.


2. Execute the following command in the Command Prompt:

```cmd
ping <target-IP-address> -t -l 65500
``` 

Replace `<target-IP-address>` with the actual IP address of the target system.

3. The `-t` option ensures that the system continuously sends ping packets until you manually stop it.

4. By using the `-l 65500` parameter, the data load size is set to 65,500 bytes, which triggers the Ping of Death attack.

**Note:** Please exercise caution and consider the legal implications before using this command.

## Performing the Ping of Death Attack using Notepad

1. Open the Notepad application on your Windows system.

2. Copy and paste the following commands into Notepad:

```cmd
:loop
ping <target-IP-address> -l 65500 -w 1 -n 1
goto :loop
```


Replace `<target-IP-address>` with the actual IP address of the target system.

3. Save the Notepad file with any desired name, for example, `ping_attack.bat`.

4. Right-click on the saved file, select "Rename," and change the file extension from `.txt` to `.bat`. The file name should now be `ping_attack.bat`.

5. Double-click on the `.bat` file to execute the command. A Command Prompt window will open, continuously sending ping packets to the specified IP address.

**Note:** Keep in mind that this command may not work on all systems, and it's crucial to understand the legal and ethical implications before using it.

## Preventing Ping of Death Attacks and DoS Attacks

To prevent Ping of Death attacks or any form of DoS attacks, consider implementing the following measures:

- Utilize a firewall that can detect and block excessive data floods originating from potential attackers.
- Configure network devices, such as routers, to control traffic flow and limit unauthorized access.
- Employ intrusion detection systems from reputable cybersecurity companies to identify and mitigate DoS attacks.

---

Remember to exercise responsible use of your knowledge and skills, adhering to legal and ethical guidelines at all times.
