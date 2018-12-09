
go setup your google drive api stuff first, you need CLIENT_ID CLIENT_SECRET CLIENT_SECRET ACCESS_TOKEN
(obtained from here: https://console.developers.google.com/)
after that, run this, and nuke it after it installed all the dependencies. 
Then, go to utilities/google-drive-upload and execute (any random file)  ./upload.sh -r _folder_key_ _random_file_ {your folder}
you can get that google folder key on google drive - click link - extract the key from that link. AFter that, you're asked for 
the Client ID and Client Secret - and it will walk you through the process.

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
