# Activity 16: DNS

Working with forward and reverse lookup zones in DNS Manager, creating host records, and testing name resolution.

## Steps

### Confirm DNS is installed
- [ ] Boot the domain controller and log in
- [ ] Boot the client PC
- [ ] On the DC, check Server Manager dashboard to confirm the DNS role is installed (install via Add Roles and Features if not)
- [ ] Tools → DNS

### Explore the forward lookup zone
- [ ] Expand the DNS server → Forward Lookup Zones → `xyz.local`
- [ ] Note that default records use the `PC.xyz.local` naming pattern
- [ ] Right-click inside the `xyz.local` zone → New Host (A or AAAA)
- [ ] Create a host record: name `client`, type A, IP `192.168.10.6`
- [ ] Capture a screenshot

### Test resolution
- [ ] Ping the client by IP: `ping 192.168.10.6`
- [ ] Ping the client by name: `ping client`
- [ ] Capture a screenshot
- [ ] Run `nslookup client` to confirm its IP and aliases
- [ ] Run `nslookup 192.168.10.6` to test reverse lookup (name for a given IP)

### Set up a reverse lookup zone
- [ ] Right-click Reverse Lookup Zones → New Zone → Primary
- [ ] Set network ID to `192.168.10`
- [ ] Inside the new zone, right-click → New Pointer (PTR)
- [ ] Create a pointer record: host `client`, IP `192.168.10.6`
- [ ] Run `nslookup 192.168.10.6` again to confirm the reverse lookup now resolves
- [ ] Capture a screenshot

### AAAA record and zone settings
- [ ] Under the forward lookup zone, create an AAAA record: `Client2`, IPv6 `2001:8db:acad:1::2`
- [ ] Explore the available tabs on an existing NS record
- [ ] Right-click `xyz.local` → Properties → Zone Transfer tab (usually greyed out, since Microsoft handles this automatically)
- [ ] Note: checking "Allow transfer to any server" is possible but a serious security risk in a real environment
- [ ] Capture a screenshot

## Screenshots to capture
- [ ] New A record for `client`
- [ ] Successful ping by hostname
- [ ] Reverse lookup confirmation via nslookup
- [ ] Zone Transfer tab

<img width="973" height="1094" alt="image" src="https://github.com/user-attachments/assets/b0efb924-ee4c-4bbb-9427-96bc75dc84a9" />

<img width="973" height="1100" alt="image" src="https://github.com/user-attachments/assets/cdd3a557-88c1-4105-8841-909a402b6508" />

<img width="973" height="1098" alt="image" src="https://github.com/user-attachments/assets/daae7a78-39fb-4325-b56d-785cc8399c9a" />

<img width="973" height="1100" alt="image" src="https://github.com/user-attachments/assets/d5a1e191-6b77-43d3-8e59-a3de41704057" />

<img width="975" height="1098" alt="image" src="https://github.com/user-attachments/assets/0f18ba0d-5203-40c3-b42f-e0723c34d908" />






