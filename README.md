# Overthewire-bandit-learning

# 15-5-2026
# level 1
- read a file named '-' using relative paths (./-) or the double-dash (--) separator.

# level 4
- use "file ./*" to find file type of each file

# level 5 
- use "find", -type", "-size", "! -excutable" to find the target path of flag 
- "-size 1033c", c = bytes
- flag: find . -type f -size 1033c ! -excutable

# level 6 
- base on level 5, use "/", "user", "group" to find the target path of flag
- "/" != ".", one is **root** directory, one is **current** directory
- flag: find / -user bandit7 -group bandit6 -size 33c

# level 7
- use "grep" to show the target word in the file
- flag: cat data.txt | grep "millionth"

#16-5-2026
# level 8
- use "sort" and "uniq -u"
- "sort": in ascending order, uniq -u: unique row only
- flag: cat data.txt | sort | uniq -u

# level 9
- strings: binery
- flag: strings data.txt | grep "="

# level 12
- "xxd -r data.txt new": change hexdump to binery

# level 13
- "scp": copy(safe) files between local and sever
- "chmod": change files premission, e.g. chmod 600 sshkey.private.
- 600 means user only

  
