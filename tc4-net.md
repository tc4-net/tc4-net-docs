# tc4-net

This document attempts to explain the background of (and how to connect to) the club's Tailscale network.  Any of the following prefaced with "(proposed)" must be ratified by Cyber Club membership.

## How Tailscale works

For details on how Tailscale works, how to install, etc., see [Tailscale's documentation](https://tailscale.com/kb/) site.  In the following, "tc4-net" and/or "tailnet" refers to the Wireguard network made available by use of Tailscale technologies and services.

## Tailscale's limits

Use of the Community plan requires use of Github for authentication.  More specifically, a Github Orgranization is required. Tim has created one, called "tc4-net".  Club users can join the tailnet by having their Github account added to the Github Organization "tc4-net".

As described by Tailscale, With the new Community on GitHub plan, the tailnet is can have:
* Up to 25 users
* 5 devices per user
* 1 subnet router (for now, the club's firewall)
* 2 admin users (project owners in Github)
* 2 unique users in ACL policy
* Community support

Note: Some of the above have specific exceptions (e.g., what happens to your device count when you "share" a device with others).  It's worthwhile to read the docs.

Because we're employing the free, community version of Tailscale, use of the tc4-net tailnet requires membership in the Github Organization.  In other words, a user must have a Github account and the Cyber Club admin(s) must add that account to the Github Organization named "tc4-net", so that the Tailscale controller can use the Github information to manage authentication to the club VPN.

Additional requirements by Tailscale require use of an Open Source license for code/docs placed in the Github Organization's repositories.  For this reason, anything deemed private or proprietary must be hosted elsewhere.

Any departures from the above Tailscale limitations will require implementation/use of the [headscale controller](https://github.com/juanfont/headscale), vice Tailscale's controller.  Headscale is the open source version of the Tailscale controller and doesn't have all of the features provided by Tailscale.  On the flip side, headscale doesn't have the above limitations for use.  Use of headscale is probably an eventuality, depending on how many use the club VPN or services.  Such will likely be a project for the club to design/implement.

## The Club's limitations

* (proposed) The user must be an member of the TC4 Cyber Club.  In other words, the user must attend either the in-person or virtual meetings.
* (proposed) If a user doesn't participate in (i.e., attend) Cyber Club meetings for six months, they will be placed on a tentative list.  If the number of users reaches 25, and a new member wants to join, the inactiive user's account may be removed from the tc4-net roster to allow the new user to join the tailnet.  As of 1 Dec 2022, active participation in the weekly meetings averages around half of the Tailscale limit (somewhere around 10-12 people).  The limit of 25 users is Tailscale-imposed.  As stated earlier, headscale may become a replacement for the Tailscale controller if there are more than 25 active users.
* (proposed) Other than users' client, adding service nodes to the club archicture must be approved by the Cyber Club membership AND the Cyber Club's Faculty Advisor. Information about each of the architecture nodes (including ownership and admin info) will be documented on the Github page or on a page within the (proposed) internal Gitea service.
* (proposed) To avoid achitecture "rot" experienced in the past, each server/service within the tailnet will have more than one user with admin rights.  These admins will be documened on the (proposed) internal Gitea service.

## Tentative services within the tc4-net tailnet

The current list of tailnet nodes/services:

* (proposed) [Gitea](https://gitea.io/en-us/) - This is a Github-like service that can be used to develop internal code and/or documentation, which may later be posed to the club's Github pages.
* (proposed) Tailscale's [MagicDNS](https://tailscale.com/blog/magicdns/) - This is a service offered by Tailscale which allows for automatic assignment of hostnames to nodes participating in the tc4-net tailnet.  An alternative would be to set up an actual DNS service.
* (proposed) [Golink](https://tailscale.com/blog/golink/) - This is a third party add-on for tailnets which allow for internal URL shortening.
* (proposed) ??? - A RSS-capable forum or wiki, to allow for publishing/promulgating internal club announcements.
* (proposed) [Keycloak](https://www.keycloak.org/) - This provides authentication/authorization/SSO services via various protocols.

## Some background

* The "tc4-net" name was chosen for the tailnet because most of the variants of "TC4" were unavailable.  "tc4-net" was the shortest, most applicable name available.
* The firewall for the Club's architecture has been added to the tc4-net tailnet.  The firewall module was recently created by [Christopher McDonald](https://www.netgate.com/blog/tailscale-on-pfsense-software).  As of 4 Dec 2022, the version number for this package is v0.1.0.  This may require modification of the firewall as new versions are released.  The Cyber Club's firewall counts as a tailnet device, but servers residing behind that firewall (apparently) do not.

## Joining TC4-Net

* If you don't already have one, or don't want to have your existing one associated with use of the VPN, create a new Github account and provide the account name to one of the Github team admins (ask on Discord if you don't know who they are).  They will add you to the Team listing.  
* While logged into that Github account, [install the Tailscale software](https://tailscale.com/kb/installation/).
* You can then run "tailscale up" to join the VPN (the software checks your Github account against the Team list and joins you to the tailnet).  If this is your first time connecting, the software will provide you with an URL to open in your browser, to join the tailnet.
* When you want to disconnect from the VPN, run "tailscale down".
* If you want to check VPN status, run "tailscale status".

## Being safe

* Before you log into the VPN with a workstation, you may want to review what services are listening on the workstation.  For Linux machines, it is quite easy to review and disable the services which shouldn't be accessed by third parties.

## Sources

* https://tailscale.com/kb/
* https://tailscale.com/blog/community-github-pricing/
* https://www.netgate.com/blog/tailscale-on-pfsense-software
* https://github.com/juanfont/headscale
* https://tailscale.com/blog/golink/
* https://tailscale.com/blog/magicdns/
* https://gitea.io/en-us/
* https://www.keycloak.org/

## Revisions to this document

* Added how to join section and software install link - 9 Dec 2022 - Tim K (joatd)
* Initial version and miscellaneous revisions - 4 Dec 2022 - Tim K. (joatd)

