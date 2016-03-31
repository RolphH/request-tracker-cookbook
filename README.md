request\_tracker Cookbook
=========================
Install Request Tracker using the system package configure

Requirements
------------
Platforms:
 - Debian
 - Ubuntu

Attributes
----------
#### request\_tracker::default
| Attribute                                         | Description                                                                                                                             | Default                                     |
|---------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| `node[:request_tracker][:install_from]`           | Choose a custom place to install from in one of: \`debian\_testing\`                                                                    | `'system'`                                  |
| `node[:request_tracker][:server]`                 | Support ‘apache’ and ‘nginx’                                                                                                            | `nginx`                                     |
| `node[:request_tracker][:server_name]`            |                                                                                                                                         | `node[:fqdn]`                               |
| `node[:request_tracker][:service_name]`           | The filename of the service to be installed                                                                                             | `request_tracker`                           |
| `node[:request_tracker][:fcgi_workers]`           | The number of fcgi workers (nginx server)                                                                                               | `1`                                         |
| `node[:request_tracker][:name]`                   | Site name                                                                                                                               | `Request Tracker`                           |
| `node[:request_tracker][:organization]`           | Organization name                                                                                                                       | `Request Tracker`                           |
| `node[:request_tracker][:force_language]`         | Force a specifig language                                                                                                               | `nil`                                       |
| `node[:request_tracker][:correspond_addess]`      | Correspond email                                                                                                                        | `''`                                        |
| `node[:request_tracker][:comment_addess]`         | Comment email                                                                                                                           | `''`                                        |
| `node[:request_tracker][:web_path]`               | Web path                                                                                                                                | `'/rt'`                                     |
| `node[:request_tracker][:web_url]`                | Web URL                                                                                                                                 | `http://#{node[:request_tracker][:domain]}` |
| `node[:request_tracker][:config]['VariableName']` | Extra configuration keys. All the keys in it will generate a config value on RT\_SiteConfig.pm, (e.g. \`Set($VariableName, “value”);\`) | `value`                                     |
| `node[:request_tracker][:db_type]`                | What DB (mysql, Pg, SQLite, …)                                                                                                          | `mysql`                                     |
| `node[:request_tracker][:db_host]`                | DB host                                                                                                                                 | `localhost`                                 |
| `node[:request_tracker][:db_port]`                | DB port                                                                                                                                 | `''`                                        |
| `node[:request_tracker][:db_name]`                | DB name                                                                                                                                 | `'rt'`                                      |
| `node[:request_tracker][:db_user]`                | DB user                                                                                                                                 | `'rtuser'`                                  |
| `node[:request_tracker][:db_password]`            | DB password                                                                                                                             | `''`                                        |

Usage
-----
#### request\_tracker::default
Just include `request\_tracker` in your node's `run_list`:

```json
{
  "name":"my_node",
  "run_list": [
    "recipe[request\_tracker]"
  ]
}
```

TODO
----
Install from git/code

Contributing
------------
1. Fork the repository on Github
2. Create a named feature branch (like `add_component_x`)
3. Write your change
4. Write tests for your change (if applicable)
5. Run the tests, ensuring they all pass
6. Submit a Pull Request using Github

After 3 consistent patches you become a committer :)
