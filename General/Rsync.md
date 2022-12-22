# Useful rsync invocations

## Reference for --info options:
```bash
rsync --info=help
Use OPT or OPT1 for level 1 output, OPT2 for level 2, etc.; OPT0 silences.

BACKUP     Mention files backed up
COPY       Mention files copied locally on the receiving side
DEL        Mention deletions on the receiving side
FLIST      Mention file-list receiving/sending (levels 1-2)
MISC       Mention miscellaneous information (levels 1-2)
MOUNT      Mention mounts that were found or skipped
NAME       Mention 1) updated file/dir names, 2) unchanged names
PROGRESS   Mention 1) per-file progress or 2) total transfer progress
REMOVE     Mention files removed on the sending side
SKIP       Mention files that are skipped due to options used
STATS      Mention statistics at end of run (levels 1-3)
SYMSAFE    Mention symlinks that are unsafe

ALL        Set all --info options (e.g. all4)
NONE       Silence all --info options (same as all0)
HELP       Output this help message

Options added for each increase in verbose level:
1) COPY,DEL,FLIST,MISC,NAME,STATS,SYMSAFE
2) BACKUP,MISC2,MOUNT,NAME2,REMOVE,SKIP
```


## Typical: Archive mode
```bash
export R_LOPTS="--info=backup --info=name --info=name2 --stats"
rsync $R_LOPTS -avh <source>/ <target>/
```

## For destinations like exFAT
```bash
rsync $L_OPTS -rtvh <source>/ <target>/
```

## Useful aliases
```bash
alias _rsync='rsync --info=backup --info=name1 --info=name2 --info=progress2 --stats'
alias bkpa='_rsync -avh'
alias bkpb='_rsync -rtvh'
```

