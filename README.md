le
--

le is a Docker image for logging to [Logentries](http://logentries.com) using
their Linux agent.

Setup
-----
1. Get your Logentries account key - go to the user profile and get
the account key from right under "Notifications".

2. Get a host key - create a new logging host and choose Linux agent,
then cancel the dialog, enter the newly created host and copy it's id from
the browser's URL.

3. Follow some logs by running
`docker run --rm -v /path/to/logs:/log gbenhaim/le --account-key=<account key> --host-key=<host key> follow /log/log_to_follow.log`
for each one of the log files you want to follow.

4. Monitor the followed logs by running
`docker run --rm -d -v /path/to/logs:/log gbenhaim/le --account-key=<account key> --host-key=<host key> monitor`
