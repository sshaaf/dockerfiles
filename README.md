# dockerfiles

## Mailcatcher

**NOTE**: Just only for local testing purposes

MailCatcher runs a super simple SMTP server which catches any message sent to it to display in a web interface.

[MailCatcher](https://mailcatcher.me/) runs a super simple SMTP server which catches
any message sent to it to display in a web interface.  By running mailcatcher we can get all the emails within our setup for testing and we wont need to use our personal or corporate emails for this. Its a great utility for testing without sending to actual email servers. 

To run locally you use the following command

```shell
podman run -d --name mailcatcher -p 8080:8080 -p 1025:1025 quay.io/sshaaf/mailcatcher
```

This command will expose locally the following ports:

* `http://127.0.0.1:8080` for see the emails
* `smtp://127.0.0.1:1025` for server SMTP endpoint


To run in Openshift use the following commands
```shell
oc new-app quay.io/sshaaf/mailcatcher --name=mailcatcher

oc expose svc/mailcatcher --port 8080
```





