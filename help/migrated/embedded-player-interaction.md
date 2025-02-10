---
jcr-language: en_us
title: Embedded Player interaction API documentation
description: Learn about various APIs to listen to events and trigger actions in the embedded player
contentowner: chandrum
---

# Embedded Player interaction API documentation

Adobe Learning Manager provides a library, which can be integrated into an app. This library provides various APIs to listen to events and trigger actions in the embedded player.

Using the APIs provided, you can play, pause, and perform other actions on the player.

## Load the library

The library is available at this [location](https://cpcontents.adobe.com/public/publiccdn/playerInteractionLib.min.js).

To load the library, follow the steps below:

1. Load the js file in the consumer application. 
2. On loading the library, window.cpPlayerLib will be populated. 

>[!NOTE]
>
>If you are not using prod US, set the params cpPlayerLib.env and cpPlayerLib.sourceOrigin based on your env.

The default values are: 

* window.cpPlayerLib.env = [https://learningmanager.adobe.com/app/player](https://learningmanager.adobe.com/app/player);
* window.cpPlayerLib.sourceOrigin = "[https://cpcontents.adobe.com](https://cpcontents.adobe.com/)";

### Methods available

The cpPlayerLib library consists of the following functions:

**startPlayer**

<table>
<tbody>
<tr>
<td>Method Name</td>
<td>startPlayer</td>
</tr>
<tr>
<td>Description</td>
<td>Loads a player in the app.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>loId : The Learning Object ID.</li><li>accountId : The Account ID of the ALM account.</li><li>userId : The User ID.</li><li>accessToken : The access token.</li><li>domRefId: The ID of the div container in which the player must be rendered.</li><li>onModuleLoaded: This function will be invoked when the modules with the below details are loaded.</li><br><li>contentType</li><li>loId</li><li>moduleId</li><li>completed</li><li>currentLanguage</li><li>availableLanguages</li><li>isCCAvailable</li><li>ccEnabled</li></br></td>
</tr>
<tr>
<td>Returns</td>
<td>Returns a promise. On resolution of the promise, a playerObj will be passed.</td>
</tr>
<tr>
<td>Exception</td>
<td>The promise will result in an exception.</td>
</tr>
<tr>
<td>Sample code</td>
<td>cpPlayerLib.startPlayer(loId, accountId, userId, accessToken, domRefId, onModuleLoaded).then((playerObj) => {//playerObj has the apis to interact with the player}) ></td>
</tr>
</tbody>
</table>

**getAllPlayers**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>getAllPlayers</td>
</tr>
<tr>
<td>Description</td>
<td>Returns all player objects on the current page.</td>
</tr>
<tr>
<td>Parameters</td>
<td>None</td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>cpPlayerLib.getAllPlayers()</td>
</tr>
</tbody>
</table>

**getPlayer**


<table>
<tbody>
<tr>
<td>Method name</td>
<td>getPlayer</td>
</tr>
<tr>
<td>Description</td>
<td>Returns a player object with the specified Learning Object id.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>loId : The Learning Object ID.</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>cpPlayerLib.getPlayer(loId)</td>
</tr>
</tbody>
</table>

**navigateToModule**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>navigateToModule</td>
</tr>
<tr>
<td>Description</td>
<td>Navigate to the next module.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>moduleId: The module ID.</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.navigateToModule(moduleID)</td>
</tr>
</tbody>
</table>

**next**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>next</td>
</tr>
<tr>
<td>Description</td>
<td>Navigate to the next module.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.next()</td>
</tr>
</tbody>
</table>

**previous**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>previous</td>
</tr>
<tr>
<td>Description</td>
<td>Navigate to the previous module.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.previous()</td>
</tr>
</tbody>
</table>

**toggleTOC**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>toggleTOC</td>
</tr>
<tr>
<td>Description</td>
<td>Toggle the TOC panel on the player.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.toggleTOC()</td>
</tr>
</tbody>
</table>

**toggleNotes**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>toggleNotes</td>
</tr>
<tr>
<td>Description</td>
<td>Toggle the notes panel on the player.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.toggleNotes()</td>
</tr>
</tbody>
</table>

**toggleClosedCaption**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>toggleClosedCaption</td>
</tr>
<tr>
<td>Description</td>
<td>Toggle the display of closed captions on the player.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.toggleClosedCaption()</td>
</tr>
</tbody>
</table>

**changeLanguage**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>changeLanguage</td>
</tr>
<tr>
<td>Description</td>
<td>Change the content language on the player.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>language: The language code to be specified.</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.changeLanguage("es")</td>
</tr>
</tbody>
</table>

**closePlayer**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>closePlayer</td>
</tr>
<tr>
<td>Description</td>
<td>Close the player and remove the player from the page. </td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.closePlayer()</td>
</tr>
</tbody>
</table>

**togglePlayPause**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>togglePlayPause</td>
</tr>
<tr>
<td>Description</td>
<td>Toggle between playing and pausing the content on the player.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.togglePlayPause()</td>
</tr>
</tbody>
</table>

**setVolume**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>setVolume</td>
</tr>
<tr>
<td>Description</td>
<td>Set the volume of the player. The value must be between 0 to 1.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>volume: The value of the volume. The valid range is 0-1. </li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.setVolume(0.5)</td>
</tr>
</tbody>
</table>

**setPlayBackSpeed**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>setPlayBackSpeed</td>
</tr>
<tr>
<td>Description</td>
<td>Set the speed of the playback in the player.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>speed: The value of the speed to be specified. Valid values are .25, .5, .75, 1, 1.25, 1.5, 1.75, 2.</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.setPlayBackSpeed(1.25)</td>
</tr>
</tbody>
</table>

**seek**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>seek</td>
</tr>
<tr>
<td>Description</td>
<td>Jump to any time on the video.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>time: The time to jump to. The time is in seconds.</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.seek(50)</td>
</tr>
</tbody>
</table>

**forward**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>forward</td>
</tr>
<tr>
<td>Description</td>
<td>Jump forward in the video by 10 seconds.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.forward()</td>
</tr>
</tbody>
</table>

**backward**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>backward</td>
</tr>
<tr>
<td>Description</td>
<td>Jump backward in the video by 10 seconds.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.backward()</td>
</tr>
</tbody>
</table>

**navigateToPage**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>navigateToPage</td>
</tr>
<tr>
<td>Description</td>
<td>Jump to the specified page on the PPT/PDF.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>pageNumber: The page number to jump to.</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.navigateToPage (5)</td>
</tr>
</tbody>
</table>

**nextPage**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>nextPage</td>
</tr>
<tr>
<td>Description</td>
<td>Jump to the next page on the PPT/PDF.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.nextPage()</td>
</tr>
</tbody>
</table>

**previousPage**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>previousPage</td>
</tr>
<tr>
<td>Description</td>
<td>Jump to the previous page on the PPT/PDF.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.previousPage()</td>
</tr>
</tbody>
</table>

**zoomIn**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>zoomIn</td>
</tr>
<tr>
<td>Description</td>
<td>Zoom in on the content on a PPT/PDF.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.zoomIn()</td>
</tr>
</tbody>
</table>

**zoomOut**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>zoomOut</td>
</tr>
<tr>
<td>Description</td>
<td>Zoom out on the content on a PPT/PDF.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.zoomOut()</td>
</tr>
</tbody>
</table>

**downloadJobAid** 

<table>
<tbody>
<tr>
<td>Method name</td>
<td>downloadJobAid</td>
</tr>
<tr>
<td>Description</td>
<td>Download a Job Aid from a course.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.downloadJobAid()</td>
</tr>
</tbody>
</table>

**toggleJobAidPullout** 

<table>
<tbody>
<tr>
<td>Method name</td>
<td>toggleJobAidPullout</td>
</tr>
<tr>
<td>Description</td>
<td>Whether or not you want to download a job aid.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.toggleJobAidPullout()</td>
</tr>
</tbody>
</table>

**fullScreen**

<table>
<tbody>
<tr>
<td>Method name</td>
<td>fullScreen</td>
</tr>
<tr>
<td>Description</td>
<td>Set player to full screen Mode.</td>
</tr>
<tr>
<td>Parameters</td>
<td><li>None</li></td>
</tr>
</tr>
<tr>
<td>Sample Code</td>
<td>playerObj.fullScreen()</td>
</tr>
</tbody>
</table>

## List of events

**onPlayerEvents(callBack)**

On registering the callback function will be invoked on all player events. The event names are as follows:

* PLAY (Video/ Audio/ CP)
* PAUSE (Video/ Audio/ CP)
* TIMEUPDATE (Video/ Audio/ CP)
* PAGECHANGE (PPT/ PDF)
* NOTEADDED (All contents)
* LAUNCHED (All contents)
* STARTED (All contents)
* COMPLETED (All contents)
* PASSED (All contents)
* FAILED (All contents)

**onStreamingEvents(callBack)**

On registering the callback function will be invoked on all player statements that are sent for tracking user activity.
