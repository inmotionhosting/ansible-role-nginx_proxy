[![Build Status](https://travis-ci.org/inmotionhosting/ansible-role-nginx_proxy.png?branch=master)](https://travis-ci.org/inmotionhosting/ansible-role-nginx_proxy) [![GPL-3.0 License](https://img.shields.io/github/license/inmotionhosting/ansible-role-nginx_proxy.svg?color=blue)](https://github.com/inmotionhosting/ansible-role-nginx_proxy/blob/master/LICENSE) [![GitHub stars](https://img.shields.io/github/stars/inmotionhosting/ansible-role-nginx_proxy.svg)](https://github.com/inmotionhosting/ansible-role-nginx_proxy/stargazers)

# Ansible Role: Nginx Proxy

Modular Ansible Role for deploying and configuring Nginx as a reverse-proxy

## Requirements

* CentOS 7.x or later
* Debian 9 or later
* Ubuntu 16.04 LTS or later

## Dependencies

None.

## Role Variables

Available variables are listed below with their default values (you can also see `defaults/main.yml`)

| Variable | Description |
| -------- | ----------- |
| nginx_daemon | Default: `nginx`
| nginx_group | Default: `nobody`
| nginx_name | Default: `nginx`
| nginx_user | Default: `nginx`
| nginx_packages | Default: `[nginx]`
| nginx_pid | Default: `/var/run/nginx.pid`
| nginx_mime_includes | Default: `/etc/nginx/mime.types`
| nginx_module_includes | Default: `/usr/share/nginx/modules/*.conf`
| nginx_proxy_includes | Default: `/etc/nginx/proxy.conf`
| nginx_site_includes | Default: `/etc/nginx/conf.d/*.conf`

### Caching
| Variable | Description |
| -------- | ----------- |
| nginx_cache_enable | Default: `true`
| nginx_cache_inactive | Default: `1h`
| nginx_cache_name | Default: `sitecache`
| nginx_cache_time_default | Default: `5`
| nginx_cache_time_404 | Default: `10`
| nginx_etag | Default: `true`
| nginx_ssi | Default: `false`
| nginx_open_file_cache_errors | Default: `false`
| nginx_open_file_cache_inactive | Default: `8m`
| nginx_open_file_cache_max | Default: `16536`
| nginx_open_file_cache_min_uses | Default: `1`
| nginx_open_file_cache_valid | Default: `5m`

### Compression
| Variable | Description |
| -------- | ----------- |
| nginx_gzip_enabled | Default: `true`
| nginx_gzip_comp_level | Default: `9`
| nginx_gzip_min_length | Default: `256`

### Connection
| Variable | Description |
| -------- | ----------- |
| nginx_hsts_enable | Default: `false`
| nginx_http2_enable | Default: `true`
| nginx_keepalive_requests | Default: `100`
| nginx_keepalive_timeout | Default: `30`
| nginx_multi_accept | Default: `true`
| nginx_reset_timedout_connection | Default: `true`
| nginx_sendfile | Default: `true`
| nginx_tcp_nodelay | Default: `true`
| nginx_tcp_nopush | Default: `true`

### Logging
| Variable | Description |
| -------- | ----------- |
| nginx_access_log | Default: `/var/log/nginx/access.l`
| nginx_error_log | Default: `/var/log/nginx/error.l`
| nginx_log_format_main | Default: `$remote_addr - $remote_user [$time_local] "$request" $status $body_bytes_sent "$http_referer" "$http_user_agent" "$http_x_forwarded_for"`

### Proxy
| Variable | Description |
| -------- | ----------- |
| nginx_proxy_buffers | Default: `[4, 32k]`
| nginx_proxy_buffer_size | Default: `32k`
| nginx_proxy_busy_buffers_size | Default: `64k`
| nginx_proxy_cache_key | Default: `"$scheme$request_method$host$request_uri"`
| nginx_proxy_connect_timeout | Default: `90`
| nginx_proxy_read_timeout | Default: `90`
| nginx_proxy_redirect | Default: `false`
| nginx_proxy_send_timeout | Default: `90`

### Ratelimit
| Variable | Description |
| -------- | ----------- |
| nginx_ratelimit | Default: `8`
| nginx_ratelimit_burst | Default: `8`
| nginx_ratelimit_nodelay | Default: `true`
| nginx_ratelimit_zone | Default: `rlzone`
| nginx_ratelimit_paths | Default: `[".*login\\.php", ".*xmlrpc\\.php", ".*wp-cron\\.php"]`

### SSL
| Variable | Description |
| -------- | ----------- |
| nginx_ssl_enable | Default: `true`
| nginx_ssl_ciphers | Default: `["EECDH+AESGCM", "EDH+AESGCM"]`
| nginx_ssl_protocols | Default: `["TLSv1.2", "TLSv1.3"]`
| nginx_ssl_session_cache | Default: `"shared:SSL:32m"`

### Static
| Variable | Description |
| -------- | ----------- |
| nginx_static_content_accel | Default: `true`
| nginx_static_content_paths | Default: `[]`

### Workers
| Variable | Description |
| -------- | ----------- |
| nginx_worker_connections | Default: `4096`
| nginx_worker_processes | Default: `auto`
| nginx_worker_rlimit_nofile | Default: `8192`
| nginx_worker_shutdown_timeout | Default: `4`

## Example Playbook

```yaml
- hosts: www
  roles:
     - role: inmotionhosting.nginx_proxy
```

## License

GPLv3

## Author Information

[InMotion Hosting](https://inmotionhosting.com)
