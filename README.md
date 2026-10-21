# ND Football Manager — Android starter

## Included in this version
- Multiple tournaments saved locally on the phone
- League and cup/group-stage tournaments
- Single or home-and-away round-robin league fixtures
- Group-stage fixtures generated automatically
- Manual custom fixture creation
- Team registration and optional badge selection from the phone gallery
- Match score entry and editing
- Automatically calculated league/group standings
- Player registration with positions
- Golden Boot top-five table calculated from goal scorers attributed to each match
- Goalkeeper clean-sheet top-five table derived from completed match scores and registered goalkeeper team affiliation
- Man of the Match top-five table based on player selected for each completed match
- Cup knockout bracket generation for 2, 4, 8 or 16 qualifiers; automatic round progression through final; third-place match generated after semifinals; penalty shoot-out scores decide tied knockout matches

- App icon: the ND Football Manager crest (assets/icon.png)
- Team badges are resized and stored inside the app data, so they survive restarts, and are shown in team lists, standings and the champion card
- Export any section (Teams, Fixtures, Standings, Players, Knockout) or a full report as a PDF with team badges, then share/save it from the phone
- Delete a tournament from its main page: enter the random 3-digit code shown on screen to confirm

## Run the project
1. Install Node.js LTS and Expo Go on an Android phone.
2. Extract the ZIP on a computer with Node.js installed.
3. In a terminal, open the extracted project folder and run `npm install`.
4. Run `npx expo start`.
5. Scan the QR code using Expo Go.

## Build an Android APK (no Expo account needed)
1. Create a free GitHub account and a new repository.
2. Upload ALL files of this project, including the hidden `.github` folder, to the repository.
3. Open the repository's **Actions** tab, choose **Build Android APK**, press **Run workflow**.
4. After about 10-20 minutes, open the finished run and download **ND-Football-Manager-APK** (a zip containing the .apk).
5. Unzip it, copy the .apk to your phone and install it (allow "install unknown apps" when asked).

The APK is signed with a debug key: fine for installing and testing, but not for Google Play. Alternative: `eas build -p android --profile preview` with an Expo account.

## Important notes
- Golden Boot goals are calculated from the scorers selected when entering each match. The scorer count must match the final score to save full scorer attribution; the user can choose “Save score only” when scorer details are unavailable.
- Clean sheets are attributed to the specific registered goalkeeper selected for each match, provided their team concedes zero goals. Select the actual goalkeeper during match result entry for accurate stats.
- Man of the Match is selected for each match during score entry.
- Top-five tables are ranked dynamically and show no more than five players per category.
- Knockout progression supports 2, 4, 8 or 16 qualifiers, advances round winners, generates a third-place match after semifinals, and supports penalty scores for tied knockout matches. Please test the tournament flow carefully before production use.
- Team badges are saved inside the app's own data (small 200px copies). Clearing the app's data removes them along with the tournaments.
- This is source code, not a compiled APK. The current environment does not have the Android SDK/Gradle toolchain or an authenticated Expo EAS build account, so an APK cannot be compiled from this workspace directly. Build it using EAS as described above, then install and test the generated APK.
