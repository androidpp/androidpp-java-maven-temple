# androidpp-java-maven-temple

for android temple of project write as java

repo: [https://github.com/androidpp/androidpp-java-maven-temple](https://github.com/androidpp/androidpp-java-maven-temple)

## env

| item           | version |
| :------------- | :------ |
| jdk            | 1.8+    |
| gradle         | 6.5+    |
| android studio | 4.1.0+  |
| android compile sdk | 30 |
| android build tools | 30.0.5 |
| android min sdk | 21 |
| android target sdk | 26 |

- library version

| item                           | version |
| :----------------------------- | :------ |
| com.android.tools.build:gradle | 4.1.2   |
| org.robolectric:robolectric    | 4.4     |
| androidx.annotation:annotation | 1.0.0   |
| androidx.multidex:multidex     | 2.0.0   |
| com.google.dagger:dagger       | 2.3.2   |
| com.google.dagger:hilt-android | 2.32-alpha   |


## warning

application use [view binding](https://developer.android.com/topic/libraries/view-binding)

if can not found databinding class, just use `File -> Invalidate Caches / Just Restart`

## publish

must add `gradle.properties`

```properties
## gpg info
signing.keyId=[your_pubkey_id]
signing.password=[your_signing_password]
## gpg version 2.1+
signing.secretKeyRingFile=/Users/[your_username]/.gnupg/secring.gpg
## nexus info
NEXUS_USERNAME=[your_sonatype_account]
NEXUS_PASSWORD=[your_sonatype_password]
```

### new-gpg

```bash
# new key
$ gpg --gen-key
# publich id
$ gpg --list-key --keyid-format short
# such as pub rsa2048/F7D94EDD 2019-11-08...
# rsa2048 F7D94EDD is public Id

# upload public
$ gpg --keyserver hkp://pgp.mit.edu --send-keys  [your_pubkey_id]
# new ring File
$ gpg --export-secret-keys  -o ~/.gnupg/secring.gpg
# if has more than one
$ gpg --export-secret-keys  -o ~/.gnupg/secring.gpg  [your_email@your_domain.com]
```