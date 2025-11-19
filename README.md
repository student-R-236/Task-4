# Task-4 : Setup and Use a Firewall on Windows/Linux

##  Objective

Configure and test basic firewall rules on Windows to allow or block traffic.

##  Tools Used

* Windows Defender Firewall with Advanced Security
* PowerShell (`Test-NetConnection`)

---

##  Steps Performed

### **1. Open Windows Firewall (Advanced Security)**

Opened:

```
Windows Defender Firewall with Advanced Security
```

---

### **2. View Existing Inbound Rules**

Navigated to:

```
Inbound Rules → list of default and application rules
```

---

### **3. Create a Rule to BLOCK Port 23 (Telnet)**

**Steps:**

1. Inbound Rules → New Rule
2. Select **Port**
3. Protocol: **TCP**
4. Specific port: **23**
5. Action: **Block the connection**
6. Profiles: Domain, Private, Public
7. Name: **Block Telnet Port 23**
8. (Screenshot added)

---

### **4. Test the Block Rule**

Used PowerShell:

```
Test-NetConnection -Port 23 localhost
```

Result: TCP Test returned **False**, confirming port 23 is blocked.

---

### **5. Create a Rule to ALLOW Port 22 (SSH)**

**Steps:**

1. Inbound Rules → New Rule
2. Select **Port**
3. Protocol: **TCP**
4. Port: **22**
5. Action: **Allow the connection**
6. Profiles: Domain, Private, Public
7. Name: **Allow SSH Port 22**
8. (Screenshot added)
---

### **6. Remove the Test Block Rule**

* Deleted **Block Telnet Port 23** to restore the original state.

---

##  Summary: How a Firewall Filters Traffic

A firewall filters packets based on rules (allow/block). Rules evaluate:

* Protocol (TCP/UDP)
* Port number
* Source & destination IP
* Network profile (Domain/Private/Public)

This ensures only authorized traffic reaches the system.

---

