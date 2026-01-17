# Playbook: DNS Resolution Failure

## Issue Description
Users are unable to access resources by hostname, though connectivity by IP address remains functional.

This issue indicates a DNS resolution problem rather than a general network outage.

---

## Initial Symptoms
- Websites or services fail to load by name
- Access by IP address succeeds
- Ping to domain names fails
- Users report “server not found” errors

---

## OSI Layer Focus
- **Layer 3:** IP connectivity verification
- **Layer 7:** DNS name resolution

---

## Step-by-Step Troubleshooting

### Step 1: Verify Basic Connectivity
- Confirm the client can reach its default gateway
- Test connectivity to known IP addresses

**Commands:**
- `ping <default-gateway>`
- `ping 8.8.8.8`

---

### Step 2: Test DNS Resolution
Attempt name resolution:
- `nslookup example.com`
- `ping example.com`

Identify whether DNS queries are failing or timing out.

---

### Step 3: Verify DNS Server Configuration
On the client device:
- Check configured DNS server addresses
- Ensure DNS servers are reachable

**Commands:**
- Windows: `ipconfig /all`
- Linux/macOS: `cat /etc/resolv.conf`

---

### Step 4: Test DNS Server Reachability
- Ping configured DNS servers
- Verify DNS service availability
- Check for recent DNS server changes or outages

---

### Step 5: Review Network Changes
- Identify recent DHCP or DNS changes
- Check for firewall rules affecting DNS (UDP/TCP 53)
- Confirm no policy changes are blocking DNS traffic

---

## Resolution
Common resolutions include:
- Correcting DNS server configuration
- Restoring DNS service availability
- Updating DHCP options for DNS
- Allowing DNS traffic through firewalls

---

## Validation
- Confirm successful hostname resolution
- Test access to internal and external resources
- Monitor for recurring DNS failures

---

## Post-Incident Notes
- Document root cause and resolution
- Review DNS redundancy and resilience
- Communicate impact and fix to stakeholders

---

## Key Takeaways
- DNS failures often mimic connectivity issues
- Testing by IP vs hostname isolates DNS quickly
- Layered troubleshooting speeds diagnosis
