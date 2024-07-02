# Sudo User

Create new user with specified name (replace `dartt0n` with your username)

```bash
sudo adduser dartt0n
```

Add user to the sudo group

```bash
sudo usermod -aG sudo dartt0n
```

Validate, that user has `sudo` group by running the following command:

```bash
groups dartt0n
```

```
dartt0n : dartt0n sudo users
```

