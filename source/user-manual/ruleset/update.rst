.. _ruleset_update:

Update ruleset
===============

Run ``update_ruleset.py`` script to update Wazuh Ruleset with no need to manually change OSSEC internal files.


Usage examples
----------------

Update Decoders, Rules and Rootchecks: ::

   $ /var/ossec/bin/update_ruleset.py

All script options: ::

  Restart:
    -r, --restart       Restart OSSEC when required.
    -R, --no-restart    Do not restart OSSEC when required.

  Backups:
    -b, --backups       Restore last backup.

  Additional Params:
    -f, --force-update  Force to update the ruleset. By default, only it is updated the new/changed decoders/rules/rootchecks.
    -o, --ossec-path    Set OSSEC path. Default: '/var/ossec'
    -s, --source        Select ruleset source path (instead of download it).
    -j, --json          JSON output. It should be used with '-s' or '-S' argument.
    -d, --debug         Debug mode.


Configure weekly updates
-------------------------

Run ``update_ruleset.py`` weekly and keep your Wazuh Ruleset installation up to date by adding a crontab job to your system.

Run ``sudo crontab -e`` and, at the end of the file, add the following line ::

  @weekly root cd /var/ossec/bin && ./update_ruleset.py -r