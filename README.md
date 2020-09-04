# michaelsasser.authorized_keys

Download and install authorized keys from url (e.g. a gist).

## Role Variables

| Varibale              | Description                                                 |
|-----------------------|-------------------------------------------------------------|
| authorized_keys_users | A list of users, where authorized keys should be registered |
| authorized_keys_url   | The url where to pull the keys from.                        |

Make sure the url is only writable by yourself. If someone gets wirte access 
to that location, ansibel will deploy that malicious keys.

## Example Playbook

```yaml
- hosts: all
  become: true
  roles:
    - michaelsasser.authorized_keys
  vars:
    - authorized_keys_users:
        - michael
    - authorized_keys_url: https://gist.githubusercontent.com/foo
```

Make sure you change the `authorized_keys_url`. The default url points to
my public keys.

## License

Copyright &copy; 2020 Michael Sasser <Info@MichaelSasser.org>. Released under
the GPLv3 license.
