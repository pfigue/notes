tags: iptables, cheatsheet

# Save current iptables

    $ iptables-save > some.file

# Restore iptables

FIXME

# Show rules 

    $ iptables -vL --line-numbers

Flags:

  * `-v` is useful to see the number of packets that matched a rule
  * `--line-numbers` is useful to delete a specific rule
    
# Delete rules from a chain

    $ iptables -D <CHAIN> <number>