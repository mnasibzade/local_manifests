![alt text][logo]

[logo]:https://crdroid.net/img/logo.png "crDroid Android"

## 1. Grabbing the source ##

[Repo](http://source.android.com/source/developing.html) is a tool provided by Google that
simplifies using [Git](http://git-scm.com/book) in the context of the Android source.

### 1.1 Installing dependencies and Repo ###

Several packages are needed in order to build crDroid
```
sudo apt install bc bison build-essential ccache curl flex g++-multilib gcc-multilib git git-lfs gnupg gperf imagemagick lib32ncurses-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses6 libncurses-dev libsdl1.2-dev libssl-dev libwxgtk3.2-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev
```

Install Repo tool
```bash
# Make a directory where Repo will be stored and add it to the path
$ mkdir ~/bin
$ PATH=~/bin:$PATH

# Download Repo itself
$ curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo

# Make Repo executable
$ chmod a+x ~/bin/repo
```

### 1.2 Initializing Repo ###

```bash
# Create a directory for the source files
# This can be located anywhere (as long as the fs is case-sensitive)
$ mkdir crDroid
$ cd crDroid

# Install Repo in the created directory
$ repo init -u https://github.com/crdroidandroid/android.git -b 15.0 --git-lfs

# Clone local manifest
$ git clone https://github.com/mnasibzade/local_manifest -b 15.0 .repo/local_manifests
```

This is what you will run each time you want to pull in upstream changes. Keep in mind that on your
first run, it is expected to take a while as it will download all the required Android source files
and their change histories.

```bash
# Let Repo take care of all the hard work
$ repo sync
```

```bash
# Run to prepare our devices list
$ . build/envsetup.sh
# ... now run
$ brunch devicecodename
```
