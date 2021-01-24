# Create a new sidechain 

> I did this task from scratch in a virtual machine, so I needed to install all the dependencies including git.
```
Task: create a new sidechain
OS: UBUNTU V20.04.1
Zend_oo: v2.1.0-beta4
Sidechains SDK: v0.2.6
```

## Installing requeriments
### Install git 
```
$ sudo apt install git-all
```
### Install VSC for doc editing 
```
$ sudo snap install --classic code
```
### Install zend_oo dependencies 
```
$ sudo apt-get update
$ sudo apt-get -y upgrade
$ sudo apt-get -y install build-essential pkg-config libc6-dev m4 g++-multilib autoconf libtool ncurses-dev unzip git python zlib1g-dev bsdmainutils automake curl wget
```
### Install sidechains-sdk dependencies
```
$ sudo apt-get update
$ sudo apt-get install -y software-properties-common
$ wget -qO - https://adoptopenjdk.jfrog.io/adoptopenjdk/api/gpg/key/public | sudo apt-key add -
$ sudo add-apt-repository --yes https://adoptopenjdk.jfrog.io/adoptopenjdk/deb/
$ sudo apt-get update
$ sudo apt-get install adoptopenjdk-8-hotspot
$ sudo apt-get install maven 
$ echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
$ curl -sL "https://keyserver.ubuntu.com/pks/lookup?op=get&search=0x2EE0EA64E40A89B84B2DF73499E82A75642AC823" | sudo apt-key add
$ sudo apt-get update
$ sudo apt-get install sbt
$ sudo apt install scala
```
## Build Zend_oo 
```
$ git clone https://github.com/HorizenOfficial/zend_oo/
$ cd zend_oo
$ ./zcutil/build.sh -j$(nproc)
$ ./zcutil/fetch-params.sh
$ ./src/zend -regtest -websocket
```

## Build Sidechains-SDK
```
$ git clone https://github.com/HorizenOfficial/Sidechains-SDK.git
$ cd Sidechains-SDK
$ export JAVA_HOME=/usr/lib/jvm/adoptopenjdk-8-hotspot-amd64/
$ mvn clean package
```

Response
```
[INFO] 
[INFO] -----------------------< com.horizen:Sidechains >-----------------------
[INFO] Building Sidechains 0.2.6                                          [4/4]
[INFO] --------------------------------[ pom ]---------------------------------
[INFO] 
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ Sidechains ---
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for Sidechains 0.2.6:
[INFO] 
[INFO] io.horizen:sidechains-sdk .......................... SUCCESS [05:44 min]
[INFO] sidechains-sdk-simpleapp ........................... SUCCESS [01:02 min]
[INFO] sidechains-sdk-scbootstrappingtools ................ SUCCESS [ 22.021 s]
[INFO] Sidechains ......................................... SUCCESS [  0.035 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  07:11 min
[INFO] Finished at: 2021-01-24T11:11:34-06:00
[INFO] ------------------------------------------------------------------------
```
## Run Bootstraping tool
```
$ java -jar tools/sctool/target/sidechains-sdk-scbootstrappingtools-0.2.6.jar
```
