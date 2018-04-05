# ansible-role-openvpn-client

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-openvpn-client.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-openvpn-client)

RHEL/CentOS - The Open Source VPN (client)

## Requirements

None

## Role Variables

Available variables are listed below, along with default values.

    openvpn_client_options: {}
    openvpn_client_scripts: []
    openvpn_client_systemd: {}

Additional variables are listed below, not defined by default.

    openvpn_client_ca: ''
    openvpn_client_key: ''
    openvpn_client_password: ''
    openvpn_client_tls_auth: ''
    openvpn_client_username: ''

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.openvpn-client
          openvpn_client_ca: |
            -----BEGIN CERTIFICATE-----
            {...}
            -----END CERTIFICATE-----
          openvpn_client_options:
            auth: SHA512
            auth_nocache: true
            auth_user_pass: /etc/openvpn/client/login.conf
            cipher: AES-256-CBC
            client: true
            comp_lzo: true
            dev: tun
            down: /etc/openvpn/scripts/client_down.bash
            fast_io: true
            group: openvpn
            key_direction: 1
            mssfix: 1450
            nobind: true
            persist_key: true
            persist_tun: true
            ping: 15
            ping_timer_rem: true
            proto: udp
            remote: vpn.torguard.org
            remote_cert_tls: server
            remote_random: true
            reneg_sec: 0
            route: '10.8.8.0 255.255.255.0'
            route_noexec: true
            route_nopull: true
            resolv_retry: infinite
            script_security: 2
            tun_mtu: 1500
            tun_mtu_extra: 32
            up: /etc/openvpn/scripts/client_up.bash
            user: openvpn
            verb: 3
          openvpn_client_password: HwZPipc9m6T6tpZnHRfd2Ihw
          openvpn_client_scripts:
            - path: /etc/openvpn/scripts/client_up.bash
              base64: |
                bG9nZ2VyIG9wZW52cG4K
          openvpn_client_systemd:
            service:
              Restart: always
              RestartSec: 30
          openvpn_client_tls_auth: |
            -----BEGIN OpenVPN Static key V1-----
            {...}
            ----END OpenVPN Static key V1-----
          openvpn_client_username: 6xLq2Upsvh5GKPTHJ9KdYmd0

## License

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
