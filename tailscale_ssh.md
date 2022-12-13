# Tailscale SSH

***Note:*** Feel free to add extra content to this article.

## Using "tailscale ssh"

To connect to a target within the VPN, run:
```
tailscale ssh USER@TARGET
```
In the above, change "USER" and "TARGET" to suit your needs.  "TARGET" can be just the name of the box, doesn't require it to be the FQDN, as regular SSH does.  Example:
```
tailscale ssh tim@cf1
```
If this is the first time that you've run "tailscale ssh" from your client, you will be asked to open a link to the Tailscale controller so that it can validate your authentication/authorization to use the service, as well as installing keys in appropriate locations (i.e. "tailscale ssh" is key-based authentication and you won't be asked for a password).

## SSH vs Tailscale SSH

To provide access within the VPN, you can run SSH as a normal service or access the target with Tailscale's SSH service (or both).  Tailscale's implementation listens on the target's IP address provided by the VPN (100.x.x.x).  If you're also running a normal SSH implementation, that service will listen on the other interfaces.

## Sources
* https://tailscale.com/kb/1193/tailscale-ssh/?q=systemd#key-management-and-distribution
