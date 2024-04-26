# graphhopper_notes

## Build from source

### Prerequisites

JAVA and Maven are prerequisites

```bash
sudo apt install openjdk-19-jdk-headless
sudo apt install maven
```

```bash
nano ~/.bashrc
```

Add the following two lines in `.bashrc`:

```bash
export JAVA_HOME=$(dirname $(dirname $(readlink -f $(which java))))
export PATH=$PATH:$JAVA_HOME/bin
```

After editing the `.bashrc` source the file:

```bash
source ~/.bashrc
```


[Detailed guide](https://github.com/graphhopper/graphhopper/blob/master/docs/core/quickstart-from-source.md)

```bash
git clone git://github.com/graphhopper/graphhopper.git
cd graphhopper
git checkout master # if you prefer a less moving branch you can use e.g. 7.x
mvn clean install -DskipTests
```

After successful compiling there are jar files in the following locations:

```
./client-hc/target/directions-api-client-hc-10.0-SNAPSHOT.jar
./web-api/target/graphhopper-web-api-10.0-SNAPSHOT.jar
./map-matching/target/graphhopper-map-matching-10.0-SNAPSHOT.jar
./core/target/graphhopper-core-10.0-SNAPSHOT.jar
./core/target/graphhopper-core-10.0-SNAPSHOT-tests.jar
./example/target/graphhopper-example-10.0-SNAPSHOT.jar
./web-bundle/target/graphhopper-web-bundle-10.0-SNAPSHOT.jar
./tools/target/graphhopper-tools-10.0-SNAPSHOT.jar
./tools/target/graphhopper-tools-10.0-SNAPSHOT-jar-with-dependencies.jar
./web/target/original-graphhopper-web-10.0-SNAPSHOT.jar
./web/target/graphhopper-web-10.0-SNAPSHOT.jar
./navigation/target/graphhopper-nav-10.0-SNAPSHOT.jar
./reader-gtfs/target/graphhopper-reader-gtfs-10.0-SNAPSHOT.jar
```

We need the one below:
```
./web/target/graphhopper-web-10.0-SNAPSHOT.jar
```

## Osmium tool

Download the tool:

```bash
sudo apt install osmium-tool
```

And then merge pfb files using the following syntax:
```bash
osmium file1.pbf file2.pbf file3.pbf -o out.pbf
```
