## Set Up Oculus Quest
1. Download and install the Oculus mobile app from the [Google Play Store](https://www.oculus.com/lynx/?u=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.oculus.twilight&e=AT05dCA9hhnMFLzrnWmqZFOXQFxaxqVy-hIq4yLjTMys94ARevhylVc8sGYtEk8_CSqly8QGJ_PcrGsCSLBMAvNxud_c2MdbeTtPO0TD8O7mLiKrCrRryY0YTGmFUeoppYVctvIMkt3uNDbJwJZ5Zw) or [Apple App Store](https://www.oculus.com/lynx/?u=https%3A%2F%2Fapps.apple.com%2Fus%2Fapp%2Foculus-vr%2Fid1366478176&e=AT05dCA9hhnMFLzrnWmqZFOXQFxaxqVy-hIq4yLjTMys94ARevhylVc8sGYtEk8_CSqly8QGJ_PcrGsCSLBMAvNxud_c2MdbeTtPO0TD8O7mLiKrCrRryY0YTGmFUeoppYVctvIMkt3uNDbJwJZ5Zw).
2. [Sign up for a developer account](https://developer.oculus.com/sign-up/).
3. Follow the in-app instructions to sign in. 
4. Pair your headset.
5. Equip your device and follow the in-VR instructions to finish.
6. Consider [enabling multiple accounts](https://support.oculus.com/articles/accounts/multiple-accounts-and-app-sharing/add-additional-accounts-on-oculus-quest-2-or-quest) if you don't want other group members to access your account.

## Unity Setup
1. Install Unity 2020.3 or newer with Android Build support enabled

## Enable Quest for Development
1. In your headset, sign into the developer account you want to use for development.
2. Go to **Devices** in the Oculus mobile app.
3. Select your headset from the device list and wait for it to connect.
4. Select **Developer Mode**.
5. Connect your headset to the computer using a USB-C cable and wear the headset.
6. Accept **Allow USB Debugging** and **Always allow from this computer** when prompted on the headset.

## Developer Tools \[OPTIONAL\]

###### Quest as a PC VR headset (Oculus Link)
1. Install the [Oculus Desktop Application](https://www.oculus.com/download_app/?id=1582076955407037).
2. Make sure your Quest is running the latest software update (settings > about).
3. Open the Oculus Desktop Application
4. Connect your Quest to the PC and follow the instructions.

###### Additional Wireless PC VR (Oculus Air Link)
1. Make sure your Quest and your PC is on the same network.
2. Go to Settings > Beta and enable Air Link in the Oculus Desktop Application (N.B.: Automatically turns off if it isn't in use for 24 hours).
3. Enable Oculus Air Link in the Quick Settings of the headset.

###### Additional Tools
1. Install [Oculus Developer Hub](https://developer.oculus.com/documentation/unity/ts-odh/).
2. Connet your Quest to the PC.
3. Open Oculus Developer Hub, click Set Up New Device and follow the instructions.
4. You can have easy access to common development features such as ADB over WiFi to install builds without the Quest attached to the PC, casting and recording from the Quest to the PC, diagnostics, disabling proximity sensor, etc.

## Project Setup
1. Start a new Unity Project using the 3D template (Don't use the VR Template).
2. In the menu, go to **File** > **Build Settings**.
3. Under **Platform**, select **Android**.
4. Set Texture Compression to ASTC.
5. Click **Switch Platform**.
6. Go to **Edit** > **Project Settings** > **XR Plugin Management**
	1.  Click **Install XR Plugin Management**. Then enable the Oculus Plugin under both the PC tab and the Android tab.

###### XR Interaction Toolkit \[RECOMMENDED\]
If you want to use XR Interaction Toolkit for cross platform VR interaction patterns (grab, teleport, etc):
1. "Enable Preview Packages" in **Edit** > **Project Settings** > **Package Manager**.
2. Go to **Window** > **Package Manager**
	1. Filter for packages in Unity Registry.
	2. Install XR Interaction Toolkit.
	3. Click Accept. Unity will restart.
	4. Locate the XR Interaction Toolkit in the Package Manager again and import the Default Input Actions sample.
3.  Locate the imported Default Input Actions in your Assets folder.
4.  Select each preset asset individually and click "add to X default" in the top of the inspector.
5.  Go to **Edit** > **Project Settings** > **Preset Manager**.
	1.  Type in "left" under the Filter for XRI Default Left Controller.
	2.  Type in "right" under the Filter for XRI Default Right Controller.
6. Remove the main camera from the scene
7. Right click in the Hierachy view and select **XR** > **XR-Rig (Action based)**
8. Attach the **Input Action Manager** script to your **XR Rig** and drag your **XRI Default Actions** from your assets to the Action Assets in the **Input Action Manager** component.
9. Run the project in the editor with Quest connected with either Oculus Link or Oculus Air Link, or build directly to the Quest to to verify that everything is set up correctly. You should be able to move your body and controllers around freely, with the controllers rendering red lines from their origin.
10. You are now ready to begin your VR journey! To get started, take a look at [this tutorial](https://www.youtube.com/watch?v=furfe8E7SOA&ab_channel=JustinPBarnett-VRGameDev) to learn about Interactables in the XR Interaction Toolkit (Notice that he uses the experimental OpenXR plugin instead of the Oculus plugin. You can safely ignore that part of the video).

######  Oculus Integration \[OPTIONAL\]
If you want to use specific features from the Oculus platform (handtracking, avatars, social, passthrough, etc), or you just don't want to use XR Interaction Toolkit, you can use the [Oculus Integration](https://assetstore.unity.com/packages/tools/integration/oculus-integration-82022). It comes with prefabs for e.g. native looking controllers, as well as sample scenes for you to explore. You can use the XR Interaction Toolkit and Oculus Integrations in the same project, if you wish.
