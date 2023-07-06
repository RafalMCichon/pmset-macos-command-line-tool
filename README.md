# PMSET Command

`pmset` is a powerful command-line tool on macOS that allows users to manipulate power management settings. The command is very versatile and can be used to modify many aspects of power management including sleep timing, wake settings, restart options after power loss, and more. 

## Requirements

- MacOS system
- Command Line Tools (Terminal)
- Administrative access for modifying settings

## Examples

This guide contains several usage examples of `pmset`.

Please note that most of these commands may require root permissions to modify the settings. Therefore, you may need to prepend `sudo` before these commands depending on your user permissions.

```bash
# Get all current settings
pmset -g

# Set the system sleep timer to 30 minutes on battery power
pmset -b sleep 30

# Disable system sleep when on AC power
pmset -c sleep 0

# Set the display to sleep after 15 minutes on battery power
pmset -b displaysleep 15

# Disable the disk sleep timer entirely
pmset -a disksleep 0

# Enable wake on ethernet magic packet
pmset -a womp 1

# Set your Mac to automatically restart after a power failure
pmset -a autorestart 1

# Display the log of power source (battery and UPS) state
pmset -g pslog

# Schedule your Mac to wake up at a specific time
pmset schedule wake "07/07/23 08:00:00"

# Cancel all scheduled events
pmset schedule cancelall
```

Additional Examples:

```bash
# To enable wake on modem ring
pmset -a ring 1

# To enable Power Nap feature on supported machines
pmset -a powernap 1

# To enable system wake from sleep based on proximity of devices with the same iCloud id
pmset -a proximitywake 1

# To enable wake when the laptop lid (or clamshell) is opened
pmset -a lidwake 1

# To enable wake when power source (AC/battery) is changed
pmset -a acwake 1

# To turn down display brightness slightly when switching to a certain power source
pmset -a lessbright 1

# To enable display sleep to use an intermediate half-brightness state between full brightness and fully off
pmset -a halfdim 1

# To use Sudden Motion Sensor to park disk heads on sudden changes in G force
pmset -a sms 1

# Change hibernation mode (use with caution)
pmset -a hibernatemode 3

# Change hibernation image file location (use with caution)
pmset -a hibernatefile /var/vm/sleepimage

# Prevent system idle sleep when any tty (e.g., remote login session) is 'active'
pmset -a ttyskeepawake 1

# Destroy File Vault Key when going to standby mode
pmset -a destroyfvkeyonstandby 1

# Show system-wide power settings and a list of software that prevents sleep
pmset -g assertions

# Show system's thermal conditions
pmset -g therm

# Show AC power adapter details
pmset -g adapter
```

## Caution

Please use `pmset` with care. Improper usage may lead to unexpected power management behaviour. It is highly recommended to always check current settings (`pmset -g`) before making any changes.
