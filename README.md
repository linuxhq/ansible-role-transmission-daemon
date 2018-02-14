# ansible-role-transmission-daemon

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-transmission-daemon.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-transmission-daemon)

RHEL/CentOS - A fast, easy, and free bittorrent client 

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    td_alt_speed_down: 50
    td_alt_speed_enabled: false
    td_alt_speed_time_begin: 540
    td_alt_speed_time_day: 127
    td_alt_speed_time_enabled: false
    td_alt_speed_time_end: 1020
    td_alt_speed_up: 50
    td_bind_address_ipv4: '0.0.0.0'
    td_bind_address_ipv6: '::'
    td_blocklist_enabled: false
    td_blocklist_url: 'http://www.example.com/blocklist'
    td_cache_size_mb: 4
    td_dht_enabled: true
    td_download_dir: '/var/lib/transmission/Downloads'
    td_download_queue_enabled: true
    td_download_queue_size: 5
    td_encryption: 1
    td_idle_seeding_limit: 30
    td_idle_seeding_limit_enabled: false
    td_incomplete_dir: '/var/lib/transmission/Downloads'
    td_incomplete_dir_enabled: false
    td_lpd_enabled: false
    td_message_level: 1
    td_peer_congestion_algorithm: ''
    td_peer_id_ttl_hours: 6
    td_peer_limit_global: 200
    td_peer_limit_per_torrent: 50
    td_peer_port: 51413
    td_peer_port_random_high: 65535
    td_port_random_low: 49152
    td_peer_port_random_on_start: false
    td_peer_socket_tos: 'default'
    td_pex_enabled: true
    td_port_forwarding_enabled: true
    td_preallocation: 1
    td_prefetch_enabled: true
    td_queue_stalled_enabled: true
    td_queue_stalled_minutes: 30
    td_ratio_limit: 2
    td_ratio_limit_enabled: false
    td_rename_partial_files: true
    td_rpc_authentication_required: false
    td_rpc_bind_address: '0.0.0.0'
    td_rpc_enabled: true
    td_rpc_host_whitelist: []
    td_rpc_host_whitelist_enabled: true
    td_rpc_password: '{81c0bf5837de960f693ce3df337bc5f30dce6ebezuTWtlG8'
    td_rpc_port: 9091
    td_rpc_url: '/transmission/'
    td_rpc_username:
    td_rpc_whitelist: [ '127.0.0.1' ]
    td_rpc_whitelist_enabled: true
    td_scrape_paused_torrents_enabled: true
    td_script_torrent_done_enabled: false
    td_script_torrent_done_filename:
    td_seed_queue_enabled: false
    td_seed_queue_size: 10
    td_speed_limit_down: 100
    td_speed_limit_down_enabled: false
    td_speed_limit_up: 100
    td_speed_limit_up_enabled: false
    td_start_added_torrents: true
    td_trash_original_torrent_files: false
    td_umask: 18
    td_upload_slots_per_torrent: 14
    td_utp_enabled: true

By default, the transmission rpc password is 'transmission'

## Dependencies

 * https://galaxy.ansible.com/linuxhq/epel/

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.transmission-daemon
          td_blocklist_enabled: true
          td_blocklist_url: 'http://john.bitsurge.net/public/biglist.p2p.gz'
          td_dht_enabled: false
          td_pex_enabled: false
          td_ratio_limit: 1
          td_ratio_limit_enabled: true
          td_rpc_whitelist: [ '127.0.0.1', '192.168.0.*' ]
          td_umask: 0

## License

GPLv3

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
