# Kernel Tuning
## Ubuntu 12.04, on Rackspace VM ~ 2GB+
My personal kernal tuning setting, don't use if you son't konw what the fuck you are doing.


###tcp_max_syn_backlog
    /proc/sys/net/ipv4/tcp_max_syn_backlog

double this value, eg. 512 to 1024


###tcp_rmem
    /proc/sys/net/ipv4/tcp_rmem

    echo "4096  87380   16777216" > /proc/sys/net/ipv4/tcp_rmem

from: 4096    87380   1029760
to:   4096  87380   16777216


###tcp_wmem
    /proc/sys/net/ipv4/tcp_wmem

    echo "4096    65536   16777216" > /proc/sys/net/ipv4/tcp_wmem

from: 4096    16384   1029760
to:   4096    65536   16777216


###netdev_max_backlog
    /proc/sys/net/core/netdev_max_backlog

    echo "2500" > /proc/sys/net/core/netdev_max_backlog

from: 1000 to 2500


###rmem_max
    /proc/sys/net/core/rmem_max

    echo "16777216" > /proc/sys/net/core/rmem_max

from: 131071 to 16777216


###wmem_max
    /proc/sys/net/core/wmem_max

    echo "16777216" > /proc/sys/net/core/wmem_max

from: 131071 to 16777216



###min_free_kbytes
    /proc/sys/vm/min_free_kbytes

    echo "65536" > /proc/sys/vm/min_free_kbytes


###overcommit_memory
    /proc/sys/vm/overcommit_memory

    echo "1" > /proc/sys/vm/overcommit_memory

Change from 0 to 1.


Reboot, proffit.

