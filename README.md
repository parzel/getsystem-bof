# getsystem-bof

This is a BOF that can be used within Sliver (and probably Cobaltstrike) to execute shellcode as SYSTEM when you have administrator rights.

```
getsystem-bof notepad.exe PATH_TO_SHELLCODE
```

Nothing about this is new, this uses the boku7 shellcode injector but aquires the SeDebugPrivilege before and finds a system process (here winlogon.exe) to use as parent when creating a new process. As the child process of a SYSTEM process inherits the parents rights, it will be running as SYSTEM as well.

Credits:
* https://github.com/boku7/spawn (for shellcode injection)
* https://gist.github.com/G0ldenGunSec/8ca0e853dd5637af2881697f8de6aecc (for process iteration)
* https://github.com/trustedsec/CS-Situational-Awareness-BOF (for headers)
