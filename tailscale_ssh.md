# Tailscale SSH

***Note:*** Feel free to add extra content to this article.

## SSH vs Tailscale SSH

To provide access within the VPN, you can run SSH as a normal service or access the target with Tailscale's SSH service (or both).  Tailscale's implementation listens on the target's IP address provided by the VPN (100.x.x.x).  If you're also running a normal SSH implementation, that service will listen on the other interfaces.

## Sources
* https://tailscale.com/kb/1193/tailscale-ssh/?q=systemd#key-management-and-distribution
