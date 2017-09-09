These are the files that will tell what to download along with the PAC-ROM source code  to make it compile for Kylessopen devices.
Files from this repo need to go to (Your PAC direcotry)/.repo/local_manifests/
Please take note that you need to change branches on few projects before you sync sources to make this ROM compile and work for either S7560 or S7562.

Lines that need changing in local_manifest.xml :

<project path="device/samsung/kylessopen" name="KylessPAC/android_device_samsung_kylessopen" revision="pac-4.4" /> change revision to s7562 for dual sim,if you dont compile for dual sim leave it as is.

<project path="vendor/samsung/kylessopen" name="KylessPAC/android_vendor_samsung_kylessopen" revision="master"/> change revision to s7562 for dual sim,if you dont compile for dual sim leave it as is.

<project path="frameworks/base" name="KylessPAC/android_frameworks_base" revision="pac-4.4"/> change revision to s7562 for dual sim,if you dont compile for dual sim change it to s7560.

<project path="frameworks/opt/telephony" name="pavlepiramida/android_frameworks_opt_telephony" revision="cm-11.0" />change revision to s7562 for dual sim,if you dont compile for dual sim change it to s7560.

If compiling for S7562 add these lines:
<remove-project path="frameworks/opt/telephony-msim" name="android_frameworks_opt_telephony-msim" groups="pdk" remote="cm" />
<project path="frameworks/opt/telephony-msim" name="kengnatural/android_frameworks_opt_telephony-msim" revision="stable/cm-11.0" />


After you made all the changes you needed just do 'repo sync' and all you need will be setup and ready for you to build.
