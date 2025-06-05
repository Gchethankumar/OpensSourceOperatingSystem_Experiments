### AIM:

To configure SElinux.

### PROCEDURE:

1.Checking SELinux ports

The first command semanage port -l | grep http checks the Security-Enhanced Linux (SELinux) policy for ports associated with the http service. SELinux is a security feature in Linux that restricts what programs can access. The semanage port -l command lists all defined SELinux ports and the grep http command filters the output to show only ports related to http.
The output shows several ports including 80 (standard web traffic), 8080, 8118, 8123 and a range from 10001 to 10010.

2.Adding a new port
The second command semanage port -a http_port_t tcp 82 adds a new port number (82) to the http_port_t port definition. This allows http traffic on port 82 in addition to the standard ports.

3.Verifying the change
The third command	again checks the http ports. The
output now shows port 82 included along with the previously listed ports.

4.Opening the firewall
The next command	opens port 82 in
the firewall. A firewall is a software program that controls traffic in and out of a computer. By default, most firewalls block all incoming traffic and this command adds an exception to allow traffic on port 82. The reboots.

5.Reloading the firewall
The command changes.

6.Installing the Apache web server

The next command
flag tells the firewall to make the change permanent across
reloads the firewall configuration to accept the
installs the Apache web server using the dnf
package manager. Apache is a popular open-source web server that can be used to host websites.
The	flag tells dnf to assume yes to all prompts, which is useful for unattended installations.

7.Starting the Apache service The command

8.Enabling Apache at boot The command whenever the system boots.

9.Restarting Apache
The command starts the Apache web server. tells the system to start Apache automatically restarts the Apache web server. This is useful if there were any configuration changes made that require the service to be restarted.

10.Testing the web server
The final command	uses the curl command to test the web server.
The	command is a utility for transferring data from or to a server. In this case, it is used to
fetch the default web page from the web server running on the local machine (localhost - 127.0.0.1).
The successful output shows that the web server is up and running and listening on port 82 as configured.

### OUTPUT:
