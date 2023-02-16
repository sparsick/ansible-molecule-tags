# ansible-molecule-tags

Playground to find out how to configure molecule to test roles that include tags.

Default Scenario runs sucessfull without tags.

```shell
molecule test
```

`tag1` Scenario should call the role with tags.

```shell
molecule test -s tag1
```

molecule fails with the following error:

```shell
INFO     Running tag1 > converge

PLAY [Converge] ****************************************************************

TASK [Gathering Facts] *********************************************************
fatal: [instance]: UNREACHABLE! => {"changed": false, "msg": "Failed to create temporary directory. In some cases, you may have been able to authenticate and did not have permissions on the target directory. Consider changing the remote tmp path in ansible.cfg to a path rooted in \"/tmp\", for more error information use -vvv. Failed command was: ( umask 77 && mkdir -p \"` echo ~/.ansible/tmp `\"&& mkdir \"` echo ~/.ansible/tmp/ansible-tmp-1676533208.7835898-20945-71609450033956 `\" && echo ansible-tmp-1676533208.7835898-20945-71609450033956=\"` echo ~/.ansible/tmp/ansible-tmp-1676533208.7835898-20945-71609450033956 `\" ), exited with result 1", "unreachable": true}

PLAY RECAP *********************************************************************
instance                   : ok=0    changed=0    unreachable=1    failed=0    skipped=0    rescued=0    ignored=0

```

## Used tool version

```shell
➜ molecule --version   
molecule 4.0.4 using python 3.10 
    ansible:2.14.2
    delegated:4.0.4 from molecule
    docker:2.0.0 from molecule_docker requiring collections: community.docker>=3.0.0-a2

```
