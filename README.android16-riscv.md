# A16_RISCV/vendor/spacemit/apps/ExoPlayer: android16-riscv

Changes made for the Android 16 (AOSP, riscv64) bring-up of the BananaPi BPI-F3 (SpacemiT K1) and the BananaPi BPI-SM10 (SpacemiT K3), on branch `android16-riscv`.

ExoPlayer demo app (`ExoPlayerDemo`, com.google.android.exoplayer2.demo 2.19.1) as a prebuilt APK.

## Changes

- **ExoPlayer: add the ExoPlayer 2.19.1 demo app as a prebuilt**: android_app_import of the Gradle-built demo APK (noDecoderExtensions release, pure Java, decodes through MediaCodec, i.e. the VPU) for the BananaPi F3 Android 16 build. Only the APK is kept here, not the ExoPlayer sources.

## Notes

- Enabled by `SPACEMIT_EXOPLAYER` in device/spacemit/common/spacemit-features.mk.
- Rebuilding the APK, from a clone of google/ExoPlayer at release-v2 dd430f7053 (r2.19.1-13), outside the AOSP tree:
  `JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64 ./gradlew :demo:assembleNoDecoderExtensionsRelease`,
  then copy `demos/main/buildout/outputs/apk/noDecoderExtensions/release/demo-noDecoderExtensions-release.apk`
  to `prebuilt/ExoPlayerDemo.apk`.

## Build

```
./build.sh k1   # or: lunch <product> && m ExoPlayerDemo
```
