## List status of all services:

```
# service --status-all
```

## Reload network config:
```
# service network restart
```

## Scroll up in terminal:
```
[Shift] + [PageUp]|[PageDown]
```

## Find process using port
```
$ sudo netstat -ltnp | grep -w ':80'
```

## Kill process using a specific port
```
$ sudo kill -9 `sudo lsof -t -i:8080`
```

## Find package name
```
$ dpkg -l | grep <part-of-package-name>
```
## Remove package
```
$ sudo apt-get purge <package-name>
```

## List all services running
```
$ systemctl --type=service --state=running
```

## Delete all files and subdir under a dir without remove the dir
```
$ sudo rm -f -r -d ./path/*
```