# Linux Ops Notes

## User & access
Created non-root user to avoid running services as root.
Using sudo allows privilege escalation with audit trail.

sudo adduser devopsing
sudo usermode -aG sudo devopsing

sudo apt update
sudo apt install openssh-server

Created servic/group user with minimum privilages
sudo useradd --system --no-create-home --shell /usr/sbin/nologin appuser

Use group to add access to spec users 
sudo usermod -aG appuser deployuser

Define ownership on logs - recursive
sudo chown -R appuser:appuser logs

Define permissons
sudo chmod 750 logs