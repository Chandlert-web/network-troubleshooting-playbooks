# Playbook: Users Cannot Reach Default Gateway

## Issue Description
End users are unable to reach their default gateway, resulting in loss of network connectivity beyond the local subnet.

This issue commonly presents as an inability to access internal or external resources.

---

## Initial Symptoms
- Users cannot access network resources
- Ping to default gateway fails
- Local network interfaces appear up
- Issue may affect one or multiple users

---

## OSI Layer Focus
- **Layer 1:** Physical connectivity
- **Layer 2:** VLAN membership, switching
- **Layer 3:** IP addressing, gateway reachability

---

## Step-by-Step Troubleshooting

### Step 1: Verify Physical Connectivity (Layer 1)
- Confirm link lights on the client device
- Verify the switch port is operational
- Check for recent cable changes or hardware issues

---

### Step 2: Validate IP Configuration (Layer 3)
On the affected device, verify:
- IP address assignment
- Subnet mask correctness
- Default gateway configuration

**Commands:**
- Windows: `ipconfig /all`
- Linux/macOS: `ifconfig` or `ip addr`

---

### Step 3: Test Gateway Reachability
Attempt to ping the default gateway:
- `ping <default-gateway-ip>`

If the ping fails:
- Proceed to Layer 2 checks

---

### Step 4: Verify VLAN Assignment (Layer 2)
- Confirm the switch port is assigned to the correct VLAN
- Check for recent VLAN changes
- Ensure the VLAN exists and is active

---

### Step 5: Check Inter-VLAN Routing (Layer 3)
If multiple VLANs are affected:
- Verify router or Layer 3 switch interfaces
- Confirm gateway IP addresses are configured and up
- Check for interface shutdowns or errors

---

### Step 6: Review Monitoring and Logs
- Check monitoring alerts for interface or device issues
- Review logs for recent errors or configuration changes

---

## Resolution
Common resolutions include:
- Correcting VLAN assignment on the switch port
- Fixing incorrect IP configuration on the client
- Restoring gateway interface availability
- Resolving physical connectivity issues

---

## Validation
- Confirm successful ping to default gateway
- Test access to internal and external resources
- Monitor for recurrence of the issue

---

## Post-Incident Notes
- Document the root cause
- Update monitoring or alerting thresholds if needed
- Communicate resolution to stakeholders

---

## Key Takeaways
- Loss of gateway connectivity is often caused by VLAN or IP misconfiguration
- Structured OSI-based troubleshooting speeds resolution
- Validation ensures long-term stability
