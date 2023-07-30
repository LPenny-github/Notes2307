# why adm is not in GroupMembership of _developer


## expectation

If `adm` is in `_developer` group, why `adm` doesn't appear in `GroupMembership` of `_developer`?

## description

`adm` is a user who has administrator privileges.

when I open Terminal as `adm`, and check what groups `adm` has joined:

```bash
id
```

I can find `_developer`(NO. 204) in the output:

```bash
...,204(_developer),...
```

but if I use this command:

```bash
dscl . read /groups/_developer | grep GroupMembership
```

I only can see:

```bash
GroupMembership: dev
```

## what & why

it's due to group design:

```text
 ___________________________________________________  groups/_developer
| GroupMembership: dev                              |
|        ____________________________ groups/admin  |
|       |                            |              |                    
|       | GroupMembership: root adm  |              |
|       |____________________________|              |
|___________________________________________________|

```

just like...

```text
 ___________________________________________________  groups/班級
| GroupMembership: 學生甲                              |
|        ____________________________ groups/班長   |
|       |                            |              |                    
|       |GroupMembership: 學生乙 學生丙              |
|       |____________________________|              |
|___________________________________________________|

```

open Terminal as `adm` and observe `GeneratedUID` and `NestedGroups` in output1 and output2.

(unimportant information in this topic will be covered with  `☆`)

input1:

```bash
adm@pylsu ~ % dscl . read /groups/_developer
```

output1:

```bash
dsAttrTypeNative:record_daemon_version: ☆
AppleMetaNodeLocation: ☆
Comment:
 ☆
GeneratedUID: ☆0CC
GroupMembership: dev
NestedGroups: ☆050
Password: ☆
PrimaryGroupID: 204
RealName:
 ☆
RecordName: ☆
RecordType: ☆
```

input2:

```bash
adm@pylsu ~ % dscl . read /groups/admin 
```

output2:

```bash
AppleMetaNodeLocation: ☆
GeneratedUID: ☆050
GroupMembers: ☆
GroupMembership: root adm
Password: ☆
PrimaryGroupID: 80
RealName: ☆
RecordName: ☆
RecordType: ☆
SMBSID: ☆
```

## how

none

## test 

none

## reference

none