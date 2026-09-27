# Project 3 - *BeReal*

Submitted by: **nafisa nusha**

**BeReal** is an iOS photo-sharing app that lets users capture or choose a unique photo, attach time and location information, and upload it to a Parse backend. Users must share their own recent moment before they can see other users’ photos.

Time spent: **4** hours spent in total

## Required Features

The following **required** functionality is implemented in the source code. Live backend and device verification is pending local configuration; see [SETUP.md](BeReal/SETUP.md).

- [x] User can launch the back camera to take a photo instead of using the photo library.
- Users without an iPhone can add unique photos to the simulator’s Photos app and select them in the app.
- [x] Posts have a time and location attached to them.
- [x] Users are not able to see other users’ photos until they upload their own recent photo.
- [x] Fetch the 10 most recent photos within the last 24 hours from the server.
- [x] Only reveal returned posts whose `createdAt` is within 24 hours of the logged-in user’s latest post. Other photos remain hidden behind a locked card.
- [x] Extend the Parse-Swift `User` with the persistent `lastPostedDate` property.

## Optional Features

- Posts have a comment section, which displays the commenter’s username and comment context.
- [x] User can enable a daily local notification when it is time to post (7 PM local time).

## Additional Features

- [x] Account creation, login, logout, and session restoration.
- [x] Photo captions and pull-to-refresh.
- [x] Duplicate-photo detection for the same user using the uploaded JPEG’s SHA-256 fingerprint.
- [x] Camera, photo-library, and location permission handling.
- [x] Photo GPS/capture-time metadata with a clearly labeled current-location or selection-time fallback.
- Image resizing and JPEG compression before upload.
- [x] Recovery of the latest post time if updating the user profile fails after a successful upload.
- Automatic feed locking after the user’s most recent post expires.

## Video Walkthrough

A new recording of this implementation is still required after connecting the backend. Follow the two-account recording checklist in [SETUP.md](BeReal/SETUP.md), save the recording as `BeRealApp.gif` alongside the project’s README in `BeReal/`, and uncomment the embed below.

https://www.loom.com/share/f02ccba700264975b48efbe5a9e90c34 

The supplied [reference walkthrough](BeReal/ReferenceWalkthrough.gif) illustrates the assignment’s intended behavior; it is not a recording of this new project.

## Notes

Implementation challenges addressed include extracting metadata from library photos, providing a location fallback for photos without GPS, and keeping the feed’s visibility synchronized with the user’s last successful server upload. The app uses the server’s post creation time for access rules, so selecting an old photo does not alter the posting window.

The post and user timestamp are separate server writes. If the photo post succeeds but the user update fails, refreshing recovers the latest post time from the server without requiring another upload.

Setup and verification instructions are in [SETUP.md](BeReal/SETUP.md). Validation results and remaining checks are in [VALIDATION.md](BeReal/VALIDATION.md).

## License

    Copyright 2026 nafisa nusha

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
