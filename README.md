# Setup Wireguard with ansible

Use ansible playbook to setup server and create client automatically.

## Requirement
1. Ubuntu desktop
2. ansible

## Usage

### Setup wireguard
1. use ```ifconfig``` to find out the interface name
2. ```cd ansible_wireguard```
3. ```sudo ansible-playbook -i inventory.ini setup_server.yml```

### Create a client
1. ```sudo ansible-playbook -i inventory.ini create_client.yml```

### Show qr code of client config
1. ```sudo ansible-playbook -i inventory.ini show_client_config.yml```

## Test
### Setup a python server
1. ```python3 -m http.server --bind 10.0.0.1```
2. connect the url from client

## Wireguard Usage
### Close VPN
1. ```sudo wg-quick down wg0```
change wg0 to your vpn name

### Open VPN
1. ```sudo wg-quick up wg0```
change wg0 to your vpn name

### Show wireguard status
1. ```sudo wg show```
