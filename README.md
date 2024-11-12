# ZFS

```
root@zfs:~# zfs list
NAME     USED  AVAIL     REFER  MOUNTPOINT
zfspl1  43.3M   789M     43.2M  /zfspl1
zfspl2  35.3M   797M     35.2M  /zfspl2
zfspl3  21.6M   810M     21.4M  /zfspl3
zfspl4  39.4M   793M     39.2M  /zfspl4

root@mdadm:~# zfs get all | grep compressratio | grep -v ref
zfspl1  compressratio         1.82x                  -
zfspl2  compressratio         2.23x                  -
zfspl3  compressratio         3.66x                  -
zfspl4  compressratio         1.00x                  -

root@zfs:~# find /otus/test -name "secret_message"
/otus/test/task1/file_mess/secret_message
root@mdadm:~# cat /otus/test/task1/file_mess/secret_message
https://otus.ru/lessons/linux-hl/

root@zfs:~# history
    1  apt update
    2  apt install zfsutils-linux
    3  zpool create zfspl1 mirror /dev/sd{b,c} && zpool create zfspl2 mirror /dev/sd{d,e} && zpool create zfspl3 mirror /dev/sd{f,g} && zpool create zfspl4 mirror /dev/sd{h,i}
    4  zpool list
    5  zfs set compression=lzjb zfspl1
    6  zfs set compression=lzjb zfspl2
    7  zfs set compression=lz4 zfspl2
    8  zfs set compression=gzip-9 zfspl3
    9  zfs set compression=zle zfspl4
   10  zfs get all | grep compression
   11  for i in {1..4}; do wget -P /zfspl$i https://gutenberg.org/cache/epub/2600/pg2600.converter.log; done
   12  ▒
   13  exit
   14  for i in {1..4}; do wget -P /zfspl$i https://gutenberg.org/cache/epub/2600/pg2600.converter.log; done
   15  ls -la
   16  ls -la / | zfsp
   17  ls -la / | grep zfsp
   18  zfs list
   19  zfs get all | grep compressratio | grep -v ref
   20  wget -O archive.tar.gz --no-check-certificate
   21  wget -O archive.tar.gz --no-check-certificate 'https://drive.usercontent.google.com/download?id=1MvrcEp-WgAQe57aDEzxSRalPAwbNN1Bb&export=download'
   22  ls -la
   23  tar -xf archive.tar.gz
   24  zpool import -d zpoolexport/
   25  zpool import -d zpoolexport/ otus
   26  zpool status
   27  get -O otus_task2.file --no-check-certificate https://drive.usercontent.google.com/download?id=1wgxjih8YZ-cqLqaZVa0lA3h3Y029c3oI&export=download
   28  wget -O otus_task2.file --no-check-certificate https://drive.usercontent.google.com/download?id=1wgxjih8YZ-cqLqaZVa0lA3h3Y029c3oI&export=download
   29  ll
   30  zfs receive otus/test@today < otus_task2.file
   31  find /otus/test -name "secret_message"
   32  cat /otus/test/task1/file_mess/secret_message
   33  history


```
