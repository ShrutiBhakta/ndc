---------------------------------------------------------------------

STEP 1: Download pfSense ISO

1. Download pfSense CE ISO image.
2. Select:
   - Architecture: AMD64
   - Installer Type: ISO Installer
   - Latest Stable Version

Screenshot:
(Insert screenshot of pfSense download page)

---------------------------------------------------------------------

STEP 2: Create Virtual Machine

1. Open Oracle VirtualBox.
2. Click New.
3. Enter:
   - Name: pfSense
   - Type: BSD
   - Version: FreeBSD (64-bit)
4. Allocate:
   - RAM: 2048 MB
   - CPU: 2 Cores
   - Hard Disk: 20 GB

Screenshot:
<img width="1232" height="682" alt="image" src="https://github.com/user-attachments/assets/d7925102-0937-4c82-b362-706f20023287" />
<img width="1226" height="687" alt="image" src="https://github.com/user-attachments/assets/47967c39-c934-4192-b302-085b8a417fdd" />
<img width="1222" height="685" alt="image" src="https://github.com/user-attachments/assets/e1a81c8c-ea72-4238-a505-7bbc7ef0c43f" />

---------------------------------------------------------------------

STEP 3: Configure Network Adapters

Adapter 1:
1. Open Settings → Network.
2. Select Adapter 1.
3. Enable Network Adapter.
4. Attached To: NAT

Adapter 2:
1. Select Adapter 2.
2. Enable Network Adapter.
3. Attached To: Host-Only Adapter
4. Select VirtualBox Host-Only Ethernet Adapter.

Screenshot:
<img width="974" height="638" alt="Screenshot 2026-06-23 011538" src="https://github.com/user-attachments/assets/56aaa756-799e-4abe-bac5-fe3c1bb79d54" />


Screenshot:
<img width="972" height="642" alt="image" src="https://github.com/user-attachments/assets/d01c64c5-1588-4f5f-8b0c-43fb2732e11a" />

---------------------------------------------------------------------

STEP 4: Attach pfSense ISO

1. Open Settings → Storage.
2. Select Empty Optical Drive.
3. Click Choose Disk File.
4. Select downloaded pfSense ISO.

Screenshot:
<img width="962" height="632" alt="image" src="https://github.com/user-attachments/assets/b8335efb-38f1-4734-8d5f-6453965dcb2d" />
<img width="961" height="841" alt="image" src="https://github.com/user-attachments/assets/72c54300-ff46-4718-b454-0dfd4c4ae544" />
<img width="970" height="641" alt="image" src="https://github.com/user-attachments/assets/52028ede-19ed-4685-8e19-1406ed927b36" />


---------------------------------------------------------------------

STEP 5: Start Installation

1. Start the Virtual Machine.
2. Select Install pfSense CE.
3. Select Current Stable Version.
4. Continue with default keymap.

Screenshot:
(Insert screenshot of installation menu)

---------------------------------------------------------------------

STEP 6: Disk Partitioning

1. Select Auto (UFS) or Auto (ZFS).
2. Select the virtual disk.
3. Start installation.

Screenshot:
(Insert screenshot of partition selection)

---------------------------------------------------------------------

STEP 7: Complete Installation

1. Wait for installation to complete.
2. Select Reboot.
3. Remove ISO before rebooting:
   Devices → Optical Drives → Remove Disk from Virtual Drive.

Screenshot:
(Insert screenshot showing installation completed)

---------------------------------------------------------------------

STEP 8: First Boot

After reboot, pfSense console menu appears.

Example:

WAN (wan) -> em0
LAN (lan) -> em1

Screenshot:
<img width="717" height="399" alt="Screenshot 2026-06-22 213727" src="https://github.com/user-attachments/assets/94f8911c-dc17-4172-90aa-5eb44c77eb7d" />


---------------------------------------------------------------------

STEP 9: Configure LAN IP Address

1. Select option 2:
   Set Interface(s) IP Address

2. Select interface:
   2 (LAN)

3. Configure IPv4 via DHCP?
   n

4. Enter LAN IP:
   192.168.56.2

5. Enter subnet:
   24

6. Gateway:
   Press ENTER

7. Configure IPv6?
   n

8. Enable DHCP Server?
   n

9. Revert to HTTP?
   n

LAN configured as:

192.168.56.2/24

Screenshot:


---------------------------------------------------------------------

STEP 10: Verify Connectivity

On Windows host:
<img width="1919" height="1079" alt="Screenshot 2026-06-22 212153" src="https://github.com/user-attachments/assets/49b4b141-7629-47fa-936f-5983006245e1" />


---------------------------------------------------------------------

STEP 11: Access Web Interface

1. Open browser.
2. Visit:

https://192.168.56.2

3. Click Advanced then continuwe. Accept security warning.

Screenshot:
<img width="1919" height="1079" alt="Screenshot 2026-06-22 212153" src="https://github.com/user-attachments/assets/09395407-0b5f-447a-8fec-7ce13d4f64ac" />


---------------------------------------------------------------------

STEP 12: Login to pfSense

Default Credentials:

Username: admin
Password: pfsense

Click Sign In.

1. Then click next 

2.
Field	          Value
Hostname	      pfsense
Domain	         home.arpa
Primary DNS	    8.8.8.8
Secondary DNS	  1.1.1.1
Override DNS	  Uncheck it
<img width="1919" height="1079" alt="Screenshot 2026-06-22 212259" src="https://github.com/user-attachments/assets/d9d128c8-0854-4a09-b3f1-03465181d419" />

4. Then next
<img width="1919" height="1032" alt="Screenshot 2026-06-22 214119" src="https://github.com/user-attachments/assets/c8436255-c8db-45d2-a17c-7f868f143322" />


<img width="1919" height="1079" alt="Screenshot 2026-06-22 212259" src="https://github.com/user-attachments/assets/2876ece3-f951-4dae-abca-ad2c9187c128" />
<img width="1919" height="1026" alt="Screenshot 2026-06-22 222814" src="https://github.com/user-attachments/assets/0f4ceedd-5f8a-4ad5-8cd5-67ede8613039" />


---------------------------------------------------------------------

STEP 13: Open Package Manager

Navigate to:

System
→ Package Manager

Screenshot:
<img width="1919" height="1032" alt="Screenshot 2026-06-22 223320" src="https://github.com/user-attachments/assets/47da0099-8d96-4050-a3f5-3b30d0fd0ff1" />

---------------------------------------------------------------------

STEP 14: Install Squid Package

1. Open Available Packages.
2. Search:
   squid
   squidGuard
3. Click Install.
4. Click Confirm.

<img width="1916" height="1025" alt="Screenshot 2026-06-22 223535" src="https://github.com/user-attachments/assets/f8d377e4-a0c6-4a5d-8569-5c54db18d6ae" />
<img width="1919" height="1030" alt="Screenshot 2026-06-22 223707" src="https://github.com/user-attachments/assets/b4914bee-8710-4b32-9b94-7d4155dce028" />
<img width="1919" height="1029" alt="Screenshot 2026-06-22 223811" src="https://github.com/user-attachments/assets/b1bfa1b3-5145-4aeb-93a1-ed3b9e43fb3c" />

---------------------------------------------------------------------
STEP 16: Configure Squid Local Cache

Navigate to:

Services → Squid Proxy Server → Local Cache
Configure the following values:
Setting	Value
Hard Disk Cache Size	100 MB
Memory Cache Size	64 MB
Cache Replacement Policy	Default
Maximum Object Size	Default
Minimum Object Size	Default
Click Save.

---------------------------------------------------------------------

STEP 17: Enable Squid Proxy

Navigate to:

Services → Squid Proxy Server → General
Configure:
Setting	Value
Enable Squid Proxy	Enabled
Proxy Interface	LAN
Proxy Port	3128
Click Save.
Screenshot:

Squid General Configuration

---------------------------------------------------------------------

STEP 18: Create User Account - shruti1 and shruti2

Navigate to:

System → User Manager → Users
Click Add User.
Configure:
Field	Value
Username	shruti1
Password	shruti123
Confirm Password	shruti123
Full Name	Shruti User 1
Click Save.
similar for shruti2
<img width="1919" height="1028" alt="Screenshot 2026-06-22 224742" src="https://github.com/user-attachments/assets/597c5853-ad83-4fc6-b3c1-2a88e04d2b37" />
<img width="1919" height="1028" alt="Screenshot 2026-06-22 230059" src="https://github.com/user-attachments/assets/3c32a4f9-2c2b-4a13-90a3-a8e52da96a95" />
<img width="1919" height="1030" alt="Screenshot 2026-06-22 230113" src="https://github.com/user-attachments/assets/5037673a-72c3-47ea-ab93-bd319d041a63" />
<img width="1919" height="1032" alt="Screenshot 2026-06-22 224920" src="https://github.com/user-attachments/assets/14a96cda-913b-409a-b2d5-0f283f93d631" />

---------------------------------------------------------------------

STEP 19: Configure Squid Authentication

Navigate to:

Services → Squid Proxy Server → Authentication
Configure:
Setting	Value
Authentication Method	Local Database
Authentication Realm	pfSense
Authentication Processes	5
Enable Authentication	Enabled
Click Save.

<img width="1143" height="927" alt="Screenshot 2026-06-22 225208" src="https://github.com/user-attachments/assets/618aa8bd-24f3-4d68-b881-b3fd28ac641d" />

---------------------------------------------------------------------

STEP 20: Enable SquidGuard

Navigate to:

Services → SquidGuard Proxy Filter → General Settings

Check:

Enable
Click Save.
Click Apply.
<img width="1919" height="1031" alt="Screenshot 2026-06-22 224013" src="https://github.com/user-attachments/assets/63bb2b92-6319-4206-929b-3eba35c126d1" />

---------------------------------------------------------------------

STEP 21: Configure Common ACL

Navigate to:

Services → SquidGuard Proxy Filter → Common ACL
Leave default settings.
Click Save.

---------------------------------------------------------------------

STEP 22: Create Group ACL for shruti1

Navigate to:

Services → SquidGuard Proxy Filter → Groups ACL
Click Add.
Configure:
Field	Value
Group Name	shruti1
Client Source	Authenticated Users
User	shruti1
Click Save.
<img width="1919" height="1028" alt="Screenshot 2026-06-22 230059" src="https://github.com/user-attachments/assets/304394cc-b689-4135-a44e-de34083204af" />
<img width="1919" height="1030" alt="Screenshot 2026-06-22 230113" src="https://github.com/user-attachments/assets/c857a525-47ed-4c97-877a-bc6beab6451c" />

---------------------------------------------------------------------
STEP 23: Apply SquidGuard Configuration

Navigate to:

Services → SquidGuard Proxy Filter

Click:

Apply
Wait for configuration reload.

---------------------------------------------------------------------

STEP 24: Configure Firefox Proxy Settings
Open Firefox.

Navigate to:

Menu → Settings → Network Settings

Click:

Settings

Select:

Manual Proxy Configuration
Configure:
Field	Value
HTTP Proxy	192.168.56.2
Port	3128

Enable:

Use this proxy server for all protocols
Click OK.
<img width="1919" height="1079" alt="Screenshot 2026-06-23 005025" src="https://github.com/user-attachments/assets/4ce24d88-e69a-48b2-a2aa-9c4599989112" />

---------------------------------------------------------------------

STEP 25: Create Target Category for Social, shruti1, shruti2 websites

Navigate to:

Services → SquidGuard Proxy Filter → Target Categories
Click Add.
Configure:
Field	Value
Name	social_media
Description	Social Networking Websites

Under Domain List, add:

facebook.com
instagram.com
whatsapp.com
Click Save.
<img width="1919" height="1026" alt="Screenshot 2026-06-23 001727" src="https://github.com/user-attachments/assets/d5741611-cc4a-4133-91c1-c0f82e0258e3" />

<img width="1916" height="1032" alt="Screenshot 2026-06-23 002100" src="https://github.com/user-attachments/assets/1bfdd95f-107e-42b8-86d1-c071c85c6576" />

---------------------------------------------------------------------

STEP 33: Configure Access Policy for shruti1

Navigate to:

Services → SquidGuard Proxy Filter → Groups ACL

Edit:

shruti1
Configure Access Rules:
Category	Action
social_media	Allow
educational_sites	Deny
common_sites	Allow
Click Save.
<img width="1919" height="1036" alt="Screenshot 2026-06-23 002314" src="https://github.com/user-attachments/assets/4856341b-e25e-4217-b398-28180f383e36" />

---------------------------------------------------------------------
STEP 38: Apply SquidGuard Configuration

Navigate to:

Services → SquidGuard Proxy Filter

Click:
<img width="1411" height="830" alt="Screenshot 2026-06-22 234430" src="https://github.com/user-attachments/assets/702011b7-cf23-42c8-ad46-54c79090e300" />

---------------------------------------------------------------------

STEP 39: Test Access Using all Users 

<img width="1919" height="1077" alt="Screenshot 2026-06-23 003437" src="https://github.com/user-attachments/assets/864c1d9e-5cef-4d9a-abbe-8c0cfdd1d042" />
<img width="1919" height="1079" alt="Screenshot 2026-06-23 005201" src="https://github.com/user-attachments/assets/1a1baee2-06f2-4ffa-b16d-a13c0c299b36" />
<img width="1919" height="1079" alt="Screenshot 2026-06-23 005247" src="https://github.com/user-attachments/assets/b47263dd-0913-4e93-a763-e51774974e2f" />
<img width="1919" height="1079" alt="Screenshot 2026-06-23 005421" src="https://github.com/user-attachments/assets/a92dce8e-3b88-4ab4-80c7-2679eb31efc0" />
