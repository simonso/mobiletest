Introduction
=============
This serves as a release notes.

Build Instruction
-----------------
The release build instruction has been abstracted out.


1. Create $HOME/.gradle/gradle.properties

    suplean.signing=/your_home/dir/.signing/suplean-release

	Notice that is is just a property file.  No quote is necessary for the name-value pair.

2. Create a directory $HOME/.signing

3. Create a file in $HOME/.signing/suplean-release.gradle.

	`android{
		signingConfigs { 
			release {}
		} 
		buildTypes{
			release{}
		}
	}`


4. Create a keystore for release build:

    http://developer.android.com/tools/publishing/app-signing.html

5. Test out the build!

	./gradlew assembleRelease (proguard and sign)
	./gradlew assembleDebug (won't sign the apk)
