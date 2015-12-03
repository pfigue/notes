tags: lxc, lxc memory

memory controller: The memory controller isolates the memory behaviour of a group of tasks from the rest of the system. [2]

files under .../docker/<container-name>/... [2]:

    tasks: PIDs of the processes belonging to that cgroup
    memory.usage_in_bytes: current usage
    memory.limit_in_bytes		 # set/show limit of memory usage
    memory.failcnt			 # show the number of memory usage hits limits
    memory.max_usage_in_bytes	 # show max memory usage recorded
    memory.soft_limit_in_bytes	 # set/show soft limit of memory usage
    memory.stat			 # show various statistics
    memory.swappiness		 # set/show swappiness parameter of vmscan
				 (See sysctl's vm.swappiness)
	memory.mesw.* are about total memory, RAM + swap, not only RAM

Refs:

    1. [https://www.kernel.org/doc/Documentation/cgroups/](https://www.kernel.org/doc/Documentation/cgroups/)
    2. https://www.kernel.org/doc/Documentation/cgroups/memory.txt
    3. [Limiting LXC memory usage](http://www.mattfischer.com/blog/?p=399)