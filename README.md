# Fcron

### Fcron is the best of both cron and anacron. It doesn’t require your computer to be running 24×7, and it can work with tasks on an hourly or minute basis.

#### The only way to install Fcron is to download the source file and compile it yourself.

1. Download the source file here.

2. Extract the archive. Open a terminal and change the filepath to the extracted archive folder.

3. Run the following commands:

Configre;

```code 

  ./configure --prefix=/usr --sysconfdir=/etc

```
(default is prefix=/usr/local and sysconfdir=${prefix}/etc).

  - To disable the use of PAM, SE Linux or fcrondyn, use configure's option --with-pam=no, --with-selinux=no and/or --with-fcrondyn=no.

  - The command make install asks you by default some questions you have to answer. To avoid that (which can be useful for automatic installers), you can use the ./configure's option --with-answer-all and/or --with-boot-install (see "./configure --help" for more details).

  - To debug fcron, you should use configure 's option --with-debug.

  - You can get info on the others configure 's options by running "./configure --help".


#### (optional) check the file config.h, and change it if necessary (the configurable part is on the top of the file and clearly delimited).

compile:

```code
  make  
```

then install binaries:

```code 
  make install
```

### It will ask you a few questions during the installation and you can safely answer “y” (yes) for all of them.


~ Conguratualtion fcron installed successfully

##### You can now run `fcron` and `fcrontab`.

```code
  # Set fcron jobs
  
  fcrontab -e 
  
  or 
  
  fcron -e
```

commands should be in ''. for example;

```code 
  * * * * * 'echo "Hello!"'
```

- The syntax for fcron is similar to cron:

```bash
  minute  hour  day-of-month  month  day-of-week  'command-to-be-executed'
```

Save file and restart fcron service

To check jobs logs 

```code 

  tail -f /var/log/cron

```

Thank you!
