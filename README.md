
go setup your google drive api stuff first, you need CLIENT_ID CLIENT_SECRET CLIENT_SECRET ACCESS_TOKEN
(obtained from here: https://console.developers.google.com/)

run the upload.sh manually first, and it will prompt you through verifying your API access.

install to an unprivileges directory so that that user accounts can execute wp-cli
run:
ansible-galaxy install -p ./roles/ -r requirements.yml
ansible-playbook ansible_wp_update.yml -e "MYSQLDBPASS=yourpassword FOLDERNAME=yourfoldername ADMIN_EMAIL=your@email"
(or, if you're on debian/ubuntu, or otherwise have a different path for apache)
ansible-playbook ansible_wp_update.yml -e "MYSQLDBPASS=yourpassword FOLDERNAME=yourfoldername ADMIN_EMAIL=your@email ApacheConfDir=/etc/httpd/sites-enabled/*"
TODO:
if a theme update is requires, check to see if the ACTIVE theme has an update.  if it doesn't, then automatically update it.
only e-mail and skip theme update if active needs updated. (because updating an active theme often fails miseriably)

check for centos/debian,and adjust apache username & apache configs dir accordingly. 
