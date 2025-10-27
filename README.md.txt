# Task 4: Setup and Use a Firewall on Windows

## Objective
Configure and test basic firewall rules to allow or block traffic.

## Tool Used
- Windows Defender Firewall

---

## Step 1: Open Firewall
- Press **Windows + R**, type `wf.msc`, press Enter.  
- This opens **Windows Defender Firewall with Advanced Security**.

---

## Step 2: List Current Rules
- Go to **Inbound Rules** in the left panel.  
- Scroll to see existing rules.  
- **Screenshot:** ![Current Rules](screenshots/windows_rules_before.png)

---

## Step 3: Block Port 23 (Telnet)
1. In **Inbound Rules**, click **New Rule…** on the right panel.  
2. Select **Port**, click **Next**.  
3. Choose **TCP**, specify **Specific local port: 23**, click **Next**.  
4. Select **Block the connection**, click **Next**.  
5. Apply to **Domain, Private, Public**, click **Next**.  
6. Name the rule `"Block Telnet"`, click **Finish**.  
- **Screenshot:** ![Block Telnet Rule](screenshots/windows_block_telnet.png)

---

## Step 4: Test Block
- Open **Command Prompt** (ensure Telnet client is enabled):
```cmd
telnet 127.0.0.1 23

Connection should fail, showing the firewall rule works.

Screenshot:

Step 5: Remove Rule

Go back to Inbound Rules → find "Block Telnet" → right-click → Delete.

Screenshot: