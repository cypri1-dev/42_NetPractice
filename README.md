##
<h1><img src="https://raw.githubusercontent.com/ayogun/42-project-badges/main/covers/cover-net_practice-bonus.png"</h1>

## Descrition
42 Net Practice is a project that develops skills in computer networking. It covers the basics of IP addresses, routing, subnetting, and protocols through practical exercises. Students configure and troubleshoot networks, thereby strengthening their understanding of modern networks.

## Logic
In the 42 Net Practice project, you will encounter a series of practical exercises where you will need to extract four essential pieces of information from an IP address and its subnet mask:
- `Network IP` : This is the address that identifies the subnet.
- `Range start` : This is the first usable IP address in the subnet.
- `Range end` : This is the last usable IP address in the subnet.
- `Broadcast IP` : This is the address used to send a message to all devices in the subnet.

## Calculations
In the following sections, we will use the host address `192.168.1.15/27` as an example.

## Finding the Network IP
To find the Network IP associated with our host address, we first focus on the last part of our host address: the `suffix` (192.168.1.15/`27`). This means that the first 27 bits of the address are used to identify the network, and the remaining bits are used to identify hosts within this subnet.

In binary, we can replace the first 27 bits with 1s, which gives us: `11111111.11111111.11111111.11100000`. This is called the `mask`.

Now, let's convert our host address to binary: `11000000.10101000.00000001.00001111`.

The Network IP is obtained by performing the binary operation `&` with the previous results as operands. The resulting value is: `11000000.10101000.00000001.00000000`.Once converted, the IP address is `192.186.1.0`

## Finding Range Start
This is the first usable IP address in the subnet. It immediately follows the Network IP and identifies the first device on this network. So our range start is `192.168.1.1`.

## Finding the Broadcast IP
Now let's take our `mask` and derive its inverse using the binary operation `~`: `00000000.00000000.00000000.00011111`.

The Broadcast IP is obtained by performing the binary operation `|` with the inverse of the mask and the Network IP as operands: `11000000.10101000.00000001.00011111`. Once converted: `192.168.1.31`.

## Finding Range End
This is the last usable IP address in the subnet. It precedes the Broadcast IP and identifies the last device on this network. So our range end is `192.168.1.30`.

## Conclusion
By following the above process, we obtain the following values:
- Network IP: `192.186.1.0`
- Range start: `192.168.1.1`
- Range end: `192.168.1.30`
- Broadcast IP: `192.168.1.31`
