# The paths /usr/lib/systemd/system/app.service and /etc/systemd/system/app.service
## /usr/lib/systemd/system/app.service

# 1 Purpose:
◦ This directory is typically used for unit files provided by the distribution's packages. These files are considered the default service files that come with the software installed from the package manager.

# 2 Managed By:
◦ These unit files are usually managed by the package management system. When a package is installed, updated, or removed, the unit files in this directory are affected accordingly.

# 3 Modifications:
◦ Users generally should not modify these files directly. Instead, they should create overrides or custom configurations in the /etc/systemd/system directory to avoid losing changes during package updates.

## /etc/systemd/system/app.service

# 1 Purpose:
◦ This directory is intended for user customization. It can contain service unit files created or modified by the system administrator. These unit files can override the default ones found in /usr/lib/systemd/system.

# 2 Managed By:
◦ These unit files are managed by the system administrator. They can be used to customize, override, or extend the behavior of the default service unit files provided by the distribution.

# 3 Modifications:
◦ Changes made to unit files in this directory are persistent and won't be overwritten by package updates. This is the recommended location for administrators to place custom unit files or to override existing ones.

## How systemd Handles These Directories
systemd looks for unit files in a specific order. Here’s how it prioritizes the directories:
1 User configuration (/etc/systemd/system):
◦ Unit files in this directory have the highest priority. If there is a unit file with the same name in both /etc/systemd/system and /usr/lib/systemd/system, the one in /etc/systemd/system will take precedence.
2 Package default (/usr/lib/systemd/system):
◦ If no override exists in /etc/systemd/system, systemd will use the unit file from this directory.

## Creating Overrides
Instead of modifying the unit files directly in /usr/lib/systemd/system, it's best practice to create an override file or directory. For example, to customize a service:
1. Override File:
systemctl edit app.service
This command opens an editor to create an override file in /etc/systemd/system/app.service.d/override.conf.

2. Custom Unit File:
◦ Copy the original unit file to /etc/systemd/system and edit it:
cp /usr/lib/systemd/system/app.service /etc/systemd/system/nano /etc/systemd/system/app.service

◦After making changes, reload the systemd daemon to apply the changes:
systemctl daemon-reload

Summary
• /usr/lib/systemd/system: Contains default unit files provided by software packages. Managed by the package manager.
• /etc/systemd/system: Contains custom or overridden unit files. Managed by the system administrator. These files take precedence over the ones in /usr/lib/systemd/system.
Understanding the distinction between these directories is crucial for proper service management and ensuring that custom configurations are persistent and correctly prioritized.
