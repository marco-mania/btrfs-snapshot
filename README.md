# btrfs-snapshot

Take and rotate snapshots on a btrfs file system.

Usage:

    btrfs-snapshot $source $target $count

| | |
|-|-|
| source: | path to make snapshot of |
| target: | snapshot directory |
| count: | Number of snapshots in the `@$snap_name-$unix_timestamp-$iso8601_date` format to keep at one time for a given snapshot |

Example for crontab:

    # Every first day in month at 01:00, keep 4 snapshots
    0 1 1 * * /usr/bin/chronic /usr/local/bin/btrfs-snapshot /mnt/ROOT/share1 /mnt/ROOT/snapshots 4

    # Every sunday at 02:00, keep 2 snapshots
    0 2 * * 0 /usr/bin/chronic /usr/local/bin/btrfs-snapshot /mnt/ROOT/share1 /mnt/ROOT/snapshots 2
