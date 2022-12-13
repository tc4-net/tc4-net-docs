# Running tailscale as a client

Tailscale allows you to join a tailnet (i.e., a VPN) and provide services within that VPN.  This can be a concern if you have open ports on your client machine (i.e., your workstation) that you don't want exposed within the VPN.  Tailscale has a switch that will block others from connecting to those ports, called "shields-up", that you can use when connecting to the tailnet.  Example:
```
tailscale up --shields-up
```
By default, the switch is true.  If you need to state it, the syntax is:
```
tailscale up --shields-up=true
```
You only need to run the command once.  Tailscale will write the option to its config file so that you don't need to declare the option the next time you run "tailscale up".

To disable the feature, you need to explicitly state that the options is false.  Example:
```
tailscale down
tailscale up --shields-up=false
```
As with setting the option to "true", you only need to declare the change to "shields-up" once.  The setting will be stored in the config file.

## Sources
* https://forum.tailscale.com/t/run-tailscaled-by-systemd-with-tailscale-shield-up-feature/1605
* https://tailscale.com/kb/1072/client-preferences/
