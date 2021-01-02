# Backup role for Ansible

## Variables

```yaml
backup:
  schedule:
    minute: "0"
    hour: "5"
    day: "*"
    weekday: "*"
    month: "*"

  target:
    type: b2
    prefix: bucketname/
    args:
      b2-account: 123account0id12345678
      b2-key: anI3eu8yJRJzOVCf2fzOVhDwn0cXPtL
      b2-hard-delete: "true"

  dirs:
    - src: "{{ services_path }}/app/data/"
      dest: app
      max_age: 10d

    - src: "{{ services_path }}/service/db/"
      dest: service
      max_age: 3d
      compress: yes
```
