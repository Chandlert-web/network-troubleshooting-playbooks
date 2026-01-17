# Playbook: VLAN Misconfiguration Causing Connectivity Issues

## Issue Description
Users experience partial or complete loss of network connectivity due to incorrect VLAN configuration on switch ports.

This issue often occurs after network changes, device moves, or switch reconfigurations.

---

## Initial Symptoms
- Users cannot reach default gateway
- Devices receive incorrect IP addresses
- Connectivity issues affect specific ports or areas
- Some VLANs function normally while others do not

---

## OSI Layer Focus
- **Layer 2:** VLAN assignment, switching
- **Layer 3:** IP addressing and gateway reachability

---

## Step-by-Step Troubleshooting

### Step 1: Identify Impacted Devices
- Determine which users or devices are affected
- Identify the switch ports in use
- Confirm the expected VLAN for affected devices

---

### Step 2: Verify VLAN Assignment (Layer 2)
On the access switch:
- Check the VLAN assigned to the affected port
- Confirm the VLAN exists on the switch
- Verify the port mode (access vs trunk)

---

### Step 3: Validate IP Addressing (Layer 3)
On the affected device:
- Confirm IP address matches expected subnet
- Verify correct default gateway is assigned
- Identify potential DHCP scope mismatches

---

### Step 4: Check Trunking and VLAN Propagation
If multiple switches are involved:
- Confirm VLAN is allowed on trunk links
- Verify trunk encapsulation and configuration
- Check for pruning or restrictions

---

### Step 5: Review Recent Changes
- Review recent switch configuration changes
- Identify recent port moves or VLAN updates
- Roll back changes if necessary

---

## Resolution
Common resolutions include:
- Correcting switch port VLAN assignment
- Updating trunk VLAN allowances
- Restoring proper access/trunk configuration
- Releasing and renewing DHCP leases

---

## Validation
- Confirm devices receive correct IP addresses
- Verify successful gateway reachability
- Test access to required network resources

---

## Post-Incident Notes
- Document configuration changes
- Update change records if applicable
- Communicate resolution and root cause

---

## Key Takeaways
- VLAN misconfigurations are a frequent cause of connectivity issues
- Layer 2 validation is critical before escalating
- Structured troubleshooting reduces downtime
