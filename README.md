# Private Settings for Fedora Remix for WSL

## 1. Download Fedora Remix for WSL

- [WhitewaterFoundry/Fedora-Remix-for-WSL: Fedora Remix for Windows Subsystem for Linux.](https://github.com/WhitewaterFoundry/Fedora-Remix-for-WSL)

## 2. Prepare

```bash
sudo dnf install git ansible
git clone https://github.com/yasu0796/private-settings-Fedora-Remix-for-WSL.git
```

## 3. Run

```bash
cd private-settings-Fedora-Remix-for-WSL/ansible
sudo ansible-playbook -i hosts.yaml playbook-private-settings.yaml -v
```

## 4. Start sshd

```bash
sudo /usr/sbin/sshd
```

## Troubleshooting

```
Transaction test succeeded.
Running transaction
RPM: error: db5 error(-30969) from dbenv->open: BDB0091 DB_VERSION_MISMATCH: Database environment version mismatch
RPM: error: cannot open Packages index using db5 -  (-30969)
RPM: error: cannot open Packages database in /var/lib/rpm
The downloaded packages were saved in cache until the next successful transaction.
You can remove cached packages by executing 'dnf clean packages'.
Error: Could not run transaction.
```

```bash
sudo rm /var/lib/rpm/.rpm.lock
```

## Limitations

This playbook doesn't cointain ssh keys.

WSL can't use these packages

- nmap
- tcpdump

## Information

- [dnf – Manages packages with the dnf package manager — Ansible Documentation](https://docs.ansible.com/ansible/latest/modules/dnf_module.html)
- [file – Manage files and file properties — Ansible Documentation](
https://docs.ansible.com/ansible/latest/modules/file_module.html)