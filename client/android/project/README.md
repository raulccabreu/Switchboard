### TO CONTRIBUTORS DEVS

This project has a bitray configured artifact upload to a maven repository

**Bitray upload dependencies**
- JDK 8
- Bitray account configured with a maven repo (the new signups have one configured by default)

**Using Bitray Upload**

On *build.gradle*: configure the ```bintray {}``` and ```install {}``` scopes with desirable information
Put on *local.properties*:

    bintray.user=<your user>
    bintray.apikey=<your api key>


**and the future releases info on *build.gradle* too:**

    def release_version = '1.0.0'
    def release_desc = 'Catbag/Switchboard forked from KeepSafe/Switchboard first release'
    def release_group = 'br.com.catbag.switchboard

**Using local maven repository**

To make your life easy for testing this client project modifications, 
on your test switchboard android app client (eg. switchboard repo example project),
Add on *gradle root module build.gradle*:

**mavenLocal()**

eg. 

    allprojects {
        repositories {
            jcenter()
            maven {
                url  "https://dl.bintray.com/catbag/maven"
            }
            mavenLocal()
        }
    }


**Don't forget to increment artifact version, or the client project will get the configured version from bintray cloud**

    def release_version = '1.0.1'


