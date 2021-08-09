#!/bin/bash
echo "Please enter the full log file path: (eg /var/log/messages/test.log)"
read -e word1
echo "Please enter the full log path and name you want to save the new file to: (eg /var/log/messages/testnew.log)"
read -e word2
echo $word1 > $word2
sed 's/^................//' "$word1" > "$word2"
