# Languages

Set up programming languages SmartLogic uses.

## Install to requirements.yml

```
- src: git+git@github.com:smartlogic/ansible-role-languages
  name: languages
  version: 0.1.0
```

## Requirements

None

## Role Variables

- `asdf_version` - Which version of asdf to download
  - Default: `0.3.0`
- `asdf_user` - The user to install asdf to
  - Default: `deploy`
- `asdf_erlang_version` - Which version of erlang to download
  - Default: `20.0`
- `asdf_elixir_version` - Which version of elixir to download
  - Default: `1.5.1`
- `asdf_nodejs_version` - Which version of nodejs to download
  - Default: `6.11.2`

## Dependencies

None

## Example Configuration

```yaml
asdf_version: '0.3.0'
asdf_user: 'deploy'

asdf_erlang_version: '20.0'
asdf_elixir_version: '1.5.1'
asdf_nodejs_version: '6.11.2'
```

## Example Playbook

```yaml
- hosts: servers
  environment:
    PATH: /home/{{ asdf_user }}/.asdf/bin:/home/{{ asdf_user }}/.asdf/shims:{{ ansible_env.PATH }}
  roles:
    - { role: languages, tags: ['elixir'], actions: ["elixir", "node"] }
```

## License

MIT

## Author Information

SmartLogic. https://smartlogic.io
