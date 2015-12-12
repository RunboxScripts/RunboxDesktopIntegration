#!/usr/bin/env bash
#/ Runbox mailto url handler
#/ Usage: runbox-mailto [MAILTO_URL]

# set -u
set -o nounset
# set -e
set -o errexit
set -o pipefail

# set runbox compose url
http_url="https://runbox.com/mail/compose"

# check for args, if none open runbox
if [[ ! -n "$*" ]] ; then
  xdg-open $http_url &
  exit 0
fi

# get the mailto url, prefix with ?
mailto_url="?$1"

# to= <- mailto:
mailto_url=$(sed "s/mailto:/to=/g" <<< "$mailto_url")

# &cc= <- ?cc=, &cc=
mailto_url=$(sed "s/?cc=\|&cc=/\&cc=/g" <<< "$mailto_url")

# &bcc= <- ?bcc=, &bcc=
mailto_url=$(sed "s/?bcc=\|&bcc=/\&bcc=/g" <<< "$mailto_url")

# &subject= <- ?subject=, &subject=
mailto_url=$(sed "s/?subject=\|&subject=/\&subject=/g" <<< "$mailto_url")

# \&msg_body= <- ?body=, &body=, &amp;body=
mailto_url=$(sed "s/?body=\|&body=\|&amp;body=/\&msg_body=/g" <<< "$mailto_url")

# send URL to system clipboard (optional)
# xclip -se c <<< $http_url$mailto_url

# open URL in browser
xdg-open $http_url$mailto_url &
