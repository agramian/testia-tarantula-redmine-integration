Testia Tarantual Redmine Integration
====================================


Overview
--------
Modification and addition of files to provide interface between Testia Tarantula and Redmine.
It seems to provide the same full functionality of the Bugzilla integration except for the direct bug creation from Tarantula. The Redmine REST Api to create bugs requires the issue data to be sent in JSON or XML format. I'm not familiar enough with Tarantula or Ruby to know how to make a JSON or XML post request. For now I set it up to simply redirect you to the new issue creation page for the Redmine project which the Tarantula Project's Bug Product is associated with. If no product is specified before clicking "Add defect to bug tracker" it will redirect to the Redmine projects page.
Hopefully someone who is more familiar with Tarantula and Ruby will eventually modify bug_post_url() to actually create the bugs.

Instructions
------------
1. Merge the files from this repository with your local copy of Tarantula
2. Recompile Tarantula's rails assets
..1. Delete the /rails/public/assets/ directory
..2. Execute rake assets:precompile in the /rails directory
3. Reload your browser
..<i>Note: If you don't see the changes reflected try these additional steps</i>
..* Execute touch /rails/tmp/restart.txt
..* Execute service httpd restart or restart the server of whatever Ruby deployment method you used
..* Clear your web browser's history and cache
