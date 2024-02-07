For this assessment, you will complete the following task set:

Create a data flow diagram for the bash script below
Port the below basic bash script to the Python 3.x equivalent
Code an API client to get data from REST API's
 

Bash Script to convert to Python:

#!/bin/bash

read -p 'What is your first name? ' STUDENTNAME
curl -L https://api.agify.io/?name=$STUDENTNAME > my_agify_info.json
LATEST_TF_URL=`curl -L https://releases.hashicorp.com/terraform/index.json | jq -r '.versions[].builds[].url' | egrep -v 'rc|beta' | egrep 'linux.*amd64' |tail -1`
FILENAME=`echo $LATEST_TF_URL | awk -F/ '{print $6}'`

if [[ ! -e $FILENAME ]]; then
 curl -#L $LATEST_TF_URL > $FILENAME
fi

clear
echo "That's all folks!"
