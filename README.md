# docker-openvpn-gateway
The script runs an openvpn client in a docker container and manages iptables rules such that the host machine acts as a VPN network gateway. The host machine routes network traffic from the primary network interface to the established VPN tunnel.

NOTE: No filtering based on the source IP is performed.
Adjust the script if the host machine can receive and route packets from unauthorized devices (e.g. by whitelisting a source IP range using iptables).

## Usage
- Modify the openvpn configuration file path if required.
- Run `docker-vpn-gateway start` to start the service.
- Run `docker-vpn-gateway stop` to stop the service.
- Adjust the default gateway of the devices whose network traffic needs to be tunneled via the gateway using DHCP or manual configuration.

The script is intended to be launched as a systemd service.
