# sshprep

# Sets up all the layers needed to log in over ssh with ssh keys
- Uses existing ssh-agent or agent forwarding, or suggests how to enable it in .bashrc
- Uses keys already loaded into the agent
- Creates and loads the keypair if no keys in the agent
- Command line can have a list of potential target hosts, which can be "host" or "user@host"
- For each target, creates a new stanza in ~/.ssh/config
- Sets up ipv4 and/or ipv6 connections if host resolves to both.
- Uses entry in /etc/hosts if available.
- Asks the user for a hostname or IP if no resolvable hostname
- Confirms that passwordless login works at the end.
- -v for verbose mode
- -s for single-step mode; user is asked before each potential system change.

# Additional notes
- Only standard Linux/posix utilities needed
- No sudo or root requirements
- Tested on openssh on Linux under bash, should work with openssh on any OS with bash
