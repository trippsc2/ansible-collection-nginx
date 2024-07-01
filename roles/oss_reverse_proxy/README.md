<!-- BEGIN_ANSIBLE_DOCS -->

# Ansible Role: trippsc2.nginx.oss_reverse_proxy
Version: 1.0.4

This role installs and configures NGINX OSS as a reverse proxy.

## Requirements

| Platform | Versions |
| -------- | -------- |
| Debian | <ul><li>bullseye</li><li>bookworm</li></ul> |
| EL | <ul><li>8</li><li>9</li></ul> |
| Ubuntu | <ul><li>focal</li><li>jammy</li><li>noble</li></ul> |

## Dependencies
| Role |
| ---- |
| trippsc2.nginx.oss |


## Role Arguments
|Option|Description|Type|Required|Choices|Default|
|---|---|---|---|---|---|
| nginxproxy_additional_http_config_files | <p>A list of additional configuration files to include in the HTTP server block.</p><p>The files must be located in the `files` directory of the role.</p><p>See trippsc2.nginx.oss role for formatting information.</p> | list | no |  |  |
| nginxproxy_ssl_stapling | <p>Enable or disable SSL stapling.</p> | bool | no |  | true |
| nginxproxy_ssl_stapling_verify | <p>Enable or disable SSL stapling verification.</p> | bool | no |  | true |
| nginxproxy_redirect_server_name | <p>The server name to which to accept connections on HTTP port 80 and redirect to HTTPS port 443.</p><p>If set to `_`, the server name is not checked.</p> | str | no |  | _ |
| nginxproxy_redirect_return_server_name | <p>The server name to which the is redirected when connecting to the server on HTTP port 80.</p><p>If set to `$host`, the server name from the request is unchanged.</p> | str | no |  | $host |
| nginxproxy_max_body_size | <p>The maximum allowed size of the client request body.</p><p>If the size in a request exceeds the configured value, the 413 (Request Entity Too Large) error is returned to the client.</p> | str | no |  | 100K |
| nginxproxy_server_name | <p>The server name to which to accept connections on HTTPS port 443.</p><p>If set to `_`, the server name is not checked.</p> | str | yes |  |  |
| nginxproxy_server_certificate_path | <p>The path to the server certificate file.</p> | path | no |  | /etc/pki/tls/certs/nginx.crt |
| nginxproxy_server_certificate_key_path | <p>The path to the server certificate key file.</p> | path | no |  | /etc/pki/tls/private/nginx.key |
| nginxproxy_proxy_address | <p>The address of the server to which to proxy requests.</p><p>The address must include the protocol and port number.</p><p>Example: http://127.0.0.1:8080</p> | str | yes |  |  |


## License
MIT

## Author and Project Information
Jim Tarpley
<!-- END_ANSIBLE_DOCS -->
