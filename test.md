
![Top](https://user-images.githubusercontent.com/83889926/168683154-f1f93b7d-20de-4d39-9081-2799619d216d.JPG)

[student@localhost ~]$ su
Password: 
[root@localhost student]# asterisk -rv
Asterisk 14.6.0, Copyright (C) 1999 - 2016, Digium, Inc. and others.
Created by Mark Spencer <markster@digium.com>
Asterisk comes with ABSOLUTELY NO WARRANTY; type 'core show warranty' for details.
This is free software, with components licensed under the GNU General Public
License version 2 and other licenses; you are welcome to redistribute it under
certain conditions. Type 'core show license' for details.
=========================================================================
Connected to Asterisk 14.6.0 currently running on localhost (pid = 1304)
localhost*CLI> reload
 Asterisk Queue Logger restarted
[May 16 21:26:02] WARNING[5899]: res_phoneprov.c:1231 get_defaults: Unable to find a valid server address or name.
[May 16 21:26:02] ERROR[5899]: ari/config.c:314 process_config: No configured users for ARI
 Reloading SIP
 Reloading MGCP
[May 16 21:26:02] NOTICE[5899]: chan_skinny.c:8447 config_load: Configuring skinny from skinny.conf
[May 16 21:26:02] NOTICE[5899]: cel_custom.c:97 load_config: No mappings found in cel_custom.conf. Not logging CEL to custom CSVs.
 Added CEL CSV mapping for 0 files.
[May 16 21:26:02] NOTICE[5899]: app_queue.c:8851 reload_queue_rules: queuerules.conf has not changed since it was last loaded. Not taking any action.
 Reloading unistim.conf...
[May 16 21:26:02] NOTICE[1700]: chan_sip.c:28455 handle_request_subscribe: Received SIP subscribe for peer without mailbox: 2101
[May 16 21:26:42] NOTICE[1700][C-0000000f]: chan_sip.c:26449 handle_request_invite: Call from '1204' (100.72.112.50:54062) to extension '2101' rejected because extension not found in context 'SWS_MASTER'.
[May 16 21:26:44] NOTICE[1700]: chan_sip.c:28455 handle_request_subscribe: Received SIP subscribe for peer without mailbox: 1204
[May 16 21:27:09] NOTICE[1700][C-00000010]: chan_sip.c:26449 handle_request_invite: Call from '2101' (100.72.112.61:38556) to extension '1204' rejected because extension not found in context 'ML_MASTER'.
[May 16 21:27:13] NOTICE[1700]: chan_sip.c:28455 handle_request_subscribe: Received SIP subscribe for peer without mailbox: 4101
[May 16 21:28:52] NOTICE[1700]: chan_sip.c:28455 handle_request_subscribe: Received SIP subscribe for peer without mailbox: 1204
[May 16 21:29:03] NOTICE[1700]: chan_sip.c:28455 handle_request_subscribe: Received SIP subscribe for peer without mailbox: 2101
[May 16 21:30:14] NOTICE[1700]: chan_sip.c:28455 handle_request_subscribe: Received SIP subscribe for peer without mailbox: 4101
