# <h1>Syslog Generator</h1>

This code is forked from https://github.com/seth-paxton/syslog-generator.

I have modified the script to remove randomly generated parts to the message. This script is intended to be used with exported line delimited syslog messages from any source with only the date stripped.

Please see datestrip.sh which will strip the dates from any line delimted syslog messages which can then be used with this script.

Please see examplelinux.log for supported format and strippedlinux.log for the stripped output from the script.

This script is intended to forward syslog messages to a SIEM for testing purposes.

<h2> Please see the Authors original readme below:</h2>

<h3> Generates syslog messages from a user defined file and sends them to a remote host.</h3>

<h4>Functionality</h4>
This script generates random hostnames, syslog levels, and tags to be used in a message. The variables and data structures can be modified to fit your needs by changing them towards the top of the script. The script also randomly pulls messages from a user defined file to provide variety to log data.

<h4>Usage</h4>
This script is written for Python 3+ and is meant to be run from the command line.

<h4>Required Arguments</h4>
--host: IP or hostname to send syslog messages.
--port: UDP port to send syslog messages.
--file: Filename to read syslog messasges from. This file should contain ONLY the text of the message. Syslog format is handled by the script.
--count: Number of messages to send at one time.
<h4>Optional Arguments</h4>
--sleep: Number of seconds to sleep until the next batch of messages is sent. Using this argument continues the script indefinitely or until the CTRL-C combination is invoked.
<h4>Example</h4>
Send 10 messages at once:

syslog_gen.py --host 192.168.1.100 --port 514 --file sample_logs --count 10 
Send 10 messages every 30 seconds:

syslog_gen.py --host 192.168.1.100 --port 514 --file sample_logs --count 10 --sleep 30 
