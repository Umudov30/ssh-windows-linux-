# SSH Key Auth — Sürətli İstinad (Cheatsheet)

## Windows → Linux

```powershell
# 1. Açar yarat
ssh-keygen

# 2. Public açarı serverə göndər
scp C:\Users\<user>\.ssh\id_rsa.pub user@server:/home/user/.ssh/authorized_keys

# 3. Qoşul
ssh user@server

# Custom adlı açar ilə
ssh -i C:\Users\<user>\.ssh\mycustomkey user@server
```

## Linux → Linux

```bash
ssh-keygen
ssh-copy-id user@server
ssh user@server
```

## Permission fix (RHEL 8 və aşağı)

```bash
chmod 600 ~/.ssh/authorized_keys
```

## Yadda saxla

- `.pub` faylı → serverə göndər
- Private key → heç kimə vermə
- `authorized_keys` → həmişə bu ad olmalıdır
- Permission → 600 olmalıdır
