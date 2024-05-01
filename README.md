# mesibo_sample_app

## Problem
the sending of message is not working. you can verify that by following steps
1. login from 1st device as user 1
2. login from 2nd device as user 2
3. send messsage form user 1 to user 2
4. you wont receive the message and also the listener `Mesibo_onMessageStatus` is not called which further verifies that message is not sent

## more info
1. platform and api version that we encountered this issue on : we tested using `mesibo_flutter_sdk v2.2.17` on android api level 34, 33 , 29 , we tested on real device as well as emulator
2. mesibo app id: `366532`
3. mesibo app token:  `tvjt0pdj4xd67rgknpc9mi0z1nifrom667iubjobeeajkq8ofaz58cnyt8khkogy`
4. Mesibo connection status: as you can see from the logs, it is `Mesibo.MESIBO_STATUS_ONLINE`
5. logs:
   user 1 logs:
```
   I/MesiboCore ( 5259): E0105-111948-128(5259)(start): mesibo android api: 2.4.5 protocol: 2.4.2 os: 29 app: com.yoliday.experience
   I/MesiboCore ( 5259): E0105-111948-129(5259)(start): starting mesibo
   I/MesiboCoreJava( 5259): E0105-111948-151(5259)(log_jni): MesiboCall Version: 2.4.5
   I/flutter ( 5259): Mesibo_onConnectionStatus: Mesibo.MESIBO_STATUS_CONNECTING
   I/flutter ( 5259): Mesibo_onConnectionStatus: Mesibo.MESIBO_STATUS_ONLINE
   I/AssistStructure( 5259): Flattened final assist data: 508 bytes, containing 1 windows, 3 views
   I/flutter ( 5259): send button clicked
   I/TextInputPlugin( 5259): Composing region changed by the framework. Restarting the input method.
   W/IInputConnectionWrapper( 5259): getTextBeforeCursor on inactive InputConnection
   W/IInputConnectionWrapper( 5259): getSelectedText on inactive InputConnection
   W/IInputConnectionWrapper( 5259): getTextAfterCursor on inactive InputConnection
   W/IInputConnectionWrapper( 5259): getCursorCapsMode on inactive InputConnection
```
   user 2 logs:
```
   I/MesiboCore ( 5542): E0105-112114-536(5542)(start): mesibo android api: 2.4.5 protocol: 2.4.2 os: 29 app: com.yoliday.experience
   I/MesiboCore ( 5542): E0105-112114-536(5542)(start): starting mesibo
   I/MesiboCoreJava( 5542): E0105-112114-552(5542)(log_jni): MesiboCall Version: 2.4.5
   I/flutter ( 5542): Mesibo_onConnectionStatus: Mesibo.MESIBO_STATUS_CONNECTING
   I/flutter ( 5542): Mesibo_onConnectionStatus: Mesibo.MESIBO_STATUS_ONLINE
   I/AssistStructure( 5542): Flattened final assist data: 508 bytes, containing 1 windows, 3 views
   I/flutter ( 5542): send button clicked
   I/TextInputPlugin( 5542): Composing region changed by the framework. Restarting the input method.
   W/IInputConnectionWrapper( 5542): getTextBeforeCursor on inactive InputConnection
   W/IInputConnectionWrapper( 5542): getSelectedText on inactive InputConnection
   W/IInputConnectionWrapper( 5542): getTextAfterCursor on inactive InputConnection
   W/IInputConnectionWrapper( 5542): getCursorCapsMode on inactive InputConnection
```