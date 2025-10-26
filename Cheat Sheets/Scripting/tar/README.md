# tar cheatsheet

Compress:

```
$ tar -zcvf my-archive.tar.gz ~/path/to/compress
```

Extract:

```
$ tar -xvf my-archive.tar.gz
```

Exclude and Compress:

```
$ tar -zcvf backup-$(date +%F).tar.gz --exclude "~/personal/project/*/*.dat" --exclude "*.ldb" --exclude "*/.git/*" --exclude "*/.terraform/*" --exclude "*/site-packages/*" --exclude "*/node_modules/*" ~/workspace ~/Documents
```

Archive and follow symlinks:

```
$ tar -cvhf archive.tar.gz /opt/app/current
```

Tar combined with wget:

```bash
$ wget -q -O - https://github.com/sibprogrammer/xq/releases/download/v1.1.4/xq_1.1.4_linux_amd64.tar.gz | tar zxv
```
