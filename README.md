# sshprep

For an introduction to using ssh keys and sshprep, please see https://www.youtube.com/watch?v=62hps0XZkN8

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
- -h for command line help
- --authpath allows you to specify the directory holding authorized_keys (useful for VMWare ESXi)
- Will operate on an intermediate host with no local keys if one ssh's there with -A (forward agent) mode

# Additional notes
- Only standard Linux/posix utilities needed
- No sudo or root requirements
- Tested on: 
1. openssh on Linux under bash
2. openssh on Windows 10 with Cygwin under cygwin shell
3. openssh on MacOS under bash
4. should work with openssh on any OS with bash


#Quickstart:
`curl -fsSL https://raw.githubusercontent.com/william-stearns/sshprep/main/sshprep -O
chmod 755 sshprep
mv sshprep *some_directory_in_path*
sshprep *ssh_hostname*`
- You should now be able to `ssh ssh_hostname` without needing a password.
- You can customise the stanza for ssh_hostname in ~/.ssh/config

