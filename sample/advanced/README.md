
# PallyCon NCG SDK Sample : Sample implemented with swift.

This sample demonstrates how to use the `iOSNcgSDK` framework to play .mp4(NCG content) or HTTP Live Streams(HLS-AES) hosted on remote servers as `Swift` language.



## Using the Sample

- Build and run the sample on an actual device running iOS 9.0 or later using Xcode.
- This sample shows licensing and streaming/downloading(mp4) playback of NCG DRM-encrypted mp4 files and HLS streaming (HLS-AES).
  
  > Note: Encrypted HLS content is not supported for playback on the simulator. 





### Adding `iOSNcgSDK.framework` to the Sample

- Add `iOSNcgSDK.framework` to Xcode project target in `General` -> `Linked Frameworks and Librarys`.
- Add `iOSNcgSDK.framework` to the `Build Settings` -> `Search Paths` -> `Framework Search Paths` path.
- Import the SDK header to `Bridging Header` file.

	~~~objectivec
		// Bridging Header file : SDKSample-Swift-Bridging-Header.h
		#import <iOSNcgSDK/iOSNcgSDK.h>
	~~~



### Adding Streams to the Sample

- Prepare to acquire a license by entering the NCG content URL and Token in `Contents.plist` in the `Resources` folder.

	~~~xml
		// Contents.plist
    <plist>
    <dict>
      <key>IsHLS</key><false/>
      <key>Token</key><string>Token String</string>
      <key>ContentName</key><string>Content Name</string>
      <key>ContentURL</key><string>Content URL</string>
    </dict>
    </plist>
	~~~



### Application Transport Security

- If any of the streams you add are not hosted securely, you will need to add an Application Transport Security(ATS) exception in the Info.plist.
- More information on ATS and the relevant plist keys can be found in the following article:
- Information Property List Key Reference - NSAppTransportSecurity: <https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW33>



### Bitcode not support

- `PallyConFPSSDK` does not support `Bitcode`.
- In the Xcode project target `Build Settings` -> `Build Options` -> `Enable Bitcode` to `NO`.



## Main Files

__NCGContentManager.swift__: 

- Reads content information from the `Contents.plist` file and displays it in the Table View in `TableViewController.swift`.

__NCGPallyConSDKManager.swift__: 

- This class wraps the API of the `iOSNcgSDK` framework.

__NCGDownloadManager.swift__: 

- This class has an example of implementing NCG content download and an example of implementing `NcgHttpRequestDelegate`.

__NCGPlaybackManager.swift__: 

- This class has an example implementation for NCG content playback in the `setNcgContentForPlayback()` function and an example implementation of `WebServerDelegate`.



## Requirements

### Build

- Built in the latest Xcode build and minimum target is iOS 9 

### Runtime

- iOS 9.0 or later



## PallyCon Multi-DRM Service

PallyCon Multi-DRM Service description and inquiries are available at the address below.
- [PallyCon Homepage](https://www.pallycon.com)
- [PallyCon Multi-DRM Document](https://pallycon.com/docs/)


---



# PallyCon NCG SDK ??????

??? ????????? `iOSNcgSDK`?????????????????? ???????????? ?????? ???????????? ??????????????? .mp4 (NCG ?????????) ?????? HTTP ????????? ????????? (HLS-AES)??? `swift` ????????? ???????????? ???????????? ????????? ???????????????.



## Using the Sample

- Xcode??? ???????????? iOS 9.0 ????????? ?????? ?????????????????? ????????? ???????????? ??????????????????.

- `iOSNcgSDK` ????????????????????? NCG .mp4 ??????????????? ??????????????? HLS ????????? ????????? ?????? ??? ??? ????????????. 

  > Note: ???????????? HLS ???????????? ????????????????????? ????????? ???????????? ????????????.

  

  

### Adding `iOSNcgSDK.framework` to the Sample

- Xcode ???????????? ????????? `General` -> `Embedded Binaries`??? `iOSNcgSDK.framework`??? ???????????????.
- ????????? `iOSNcgSDK.framework` ????????? `Build Settings` -> `Search Paths` -> `Framework Search Paths`??? ???????????????.
- `Bridging Header`??? ???????????? SDK ????????? `import` ?????????.

	~~~objectivec
		// Bridging Header file : SDKSample-Swift-Bridging-Header.h
		#import <iOSNcgSDK/iOSNcgSDK.h>
	~~~



### Adding Streams to the Sample

- Resources ????????? Contents.plist ??? NCG ????????? URL??? Token??? ???????????? ??????????????? ?????? ????????? ?????????.

	~~~xml
		// Contents.plist
    <plist>
    <dict>
      <key>IsHLS</key><false/>
      <key>Token</key><string>Token String</string>
      <key>ContentName</key><string>Content Name</string>
      <key>ContentURL</key><string>Content URL</string>
    </dict>
    </plist>
	~~~



### Application Transport Security

- HLS ??????????????? ?????????????????? ???????????? Application Transport Security (ATS) ????????? Info.plist??? ???????????? ?????????. ATS ??? plist ?????? ?????? ????????? ?????? ???????????? ?????? ??? ??? ????????????.  
- Information Property List Key Reference - NSAppTransportSecurity: <https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW33>



### Bitcode not support

- `PallyConFPSSDK` ??? `Bitcode`??? ???????????? ????????????.
- Xcode ???????????? ????????? `Build Settings` -> `Build Options` -> `Enable Bitcode`??? `NO`??? ???????????????.



## Main Files

__NCGContentManager.swift__: 

- `Contents.plist` ???????????? ????????? ????????? ?????? `TableViewController.swift`?????? Table View??? ???????????????. 

__NCGPallyConSDKManager.swift__: 

- `iOSNcgSDK` ?????????????????? API??? ????????? ??????????????????.

__NCGDownloadManager.swift__: 

- NCG ????????? ???????????? ?????? ????????? `NcgHttpRequestDelegate` ?????? ????????? ?????? ??????????????????.

__NCGPlaybackManager.swift__: 

- `setNcgContentForPlayback()` ???????????? NCG ????????? ????????? ?????? ?????? ????????? `WebServerDelegate` ?????? ????????? ?????? ??????????????????.



## Requirements

### Build

- ?????? Xcode?????? ???????????? ?????? ????????? iOS 9 ?????????.

### Runtime

- iOS 9.0 or later



## PallyCon ?????? DRM ?????????

PallyCon ?????? DRM ????????? ????????? ?????? ????????? ?????? ????????? ???????????????.
- [PallyCon Homepage](https://www.pallycon.com)
- [PallyCon Multi-DRM Document](https://pallycon.com/docs/)


Copyright (C) 2019 INKA Entworks. All rights reserved.

