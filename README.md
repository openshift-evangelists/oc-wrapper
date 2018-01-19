# oc Wrapper to manage contexts in a proper way
Script to wrap oc that manages login to different clusters and context switching.

NOTE: You'll need to either set the variable OC_BINARY to your real oc command, or place the binary in this directory and rename it to oc-origin.


## List of commands
This script helps you login, logout, re-login and see available oc contexts in an easy and meaningful way

## Login to a cluster
Validates that the user is logged in with the current context, and if not, it logs it in. Using the user and cluster in the current context.

```
$ oc login
oc login https://192.168.64.35:8443 -u developer --request-timeout=2s
Authentication required for https://192.168.64.35:8443 (openshift)
Username: developer
Password:
Login successful.

You have one project on this server: "myproject"

Using project "myproject".
User has succesfully logged back to 3_7
```

## Logout of a cluster
Logs the user out, by de-selecting the context in use.

```
$ oc logout
```

## Status of the current context
Status of the current context

```
$ oc context-status
You're using profile: 3_7
[INFO] You're currently connected. Token is still valid

Cluster: https://192.168.64.35:8443
User: developer
Project: myproject
```

## List contexts
Lists existing contexts. It shows current context with a line of *

```
$ oc list
 - 3_7  ***********************
 - minishift
 - 3_6
 - istio
```

## Change to a known context
Changes to the specified context

```
$ oc use 3_7
```

## Raname current context
Changes the name of the current context to something more meaningful.

```
$ oc rename-context 3_7
```
