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
            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
            A1gTTlpi7A==
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
          openvpn_client_password: Shuy6thuwief
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
            e4b001042477502a4126ebfa34eddb3f
            1f5db00f60360a736341f4bccc7eb68d
            4e578b5b9d36c258ab68507d65b8860d
            223eeec7c23b7784f3ddb09f495a788e
            b7855adfb4455e6fd177c2f0bb332b75
            6265c7128ba755113c344258f2d7f5ac
            ee2b0fca5119722c34d01f506d3f0327
            f21cc71d5ef52fa1a109f24fa80e011c
            e3f4cd56b087d7fbcc75aa4e5ace984f
            fe80007fa474d9e0352e158bd4941211
            8d68a1fed6963ac0f70cac73a4a15e35
            170bbb67f1becb866e867ca48898bb9e
            ba9a396e5a993665b0f27eadd7832400
            142a1a6fc40fffab82c466a6f3cff8f2
            4736060066da920b937ef02bb1b57983
            826d027bb59f18822c2fcae4cc10dabe
            -----END OpenVPN Static key V1-----
          openvpn_client_username: Aphohc0AhpuN

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
