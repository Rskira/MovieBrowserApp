MovieBrowserApp

App Description:

MovieBrowserApp is an iOS application built using SwiftUI that allows users to browse movies from various categories such as Trending, Now Playing, Upcoming, and more. The app provides detailed information about each movie, including its cast, trailer, runtime, and genres. Users can also watch movie trailers directly within the app using a YouTube player integration.



Build and Run Instructions
Download from the provided link.
Open in Xcode:
Open the .xcworkspace file in Xcode (ensure you have Xcode 13 or higher installed).
Install Dependencies:
This project uses Swift Package Manager (SPM) for dependency management.
Ensure all dependencies are resolved automatically when opening the project.
Run the Project:
Select a target device or simulator (preferably iPhone 13 or later).
Press Cmd + R or click the Run button in Xcode to build and run the app.
API Key Setup:
The app uses The Movie Database (TMDB) API.
Ensure the API key is included in the APIManager file:
private let apiKey = "154ad8f9017ced85e1b45f006f50d4a0"
Replace YOUR_API_KEY with your valid TMDB API key.


Architecture Explanation
The app follows the MVVM (Model-View-ViewModel) architecture, ensuring a clean separation of concerns and scalable code:

Model:
Represents the data layer.
Contains structures for Movie, Cast, Genre, and API response models.

View:
Consists of SwiftUI views such as HomeView,  MovieDetailsView, MovieCategoryView, YoutubePlayerView and CustomImageView.


Displays data to the user and handles user interactions.
ViewModel:
Acts as a bridge between the View and Model.
Handles business logic, API calls, and state management.
Examples: HomeViewModel, MovieDetailViewModel.


Libraries and Design Rationale
Libraries Used:

SwiftUI: To leverage declarative UI design for dynamic and responsive interfaces.
Combine: For state management and reactive programming.
YouTube iOS Player Helper: For embedding YouTube trailers seamlessly.
Alamofire: For network calls and API integration.

Design Rationale:
SwiftUI: Selected for modern iOS development, ensuring clean and concise UI code.
MVVM Architecture: Enables better testability and separation of concerns.
YouTube SDK: Provides native controls and a reliable video player experience.
Combine: Simplifies state management by linking ViewModel state to SwiftUI views.


Known Issues/Limitations:

Package not found:
When trying to build project if you encounter error: package not found , then in Xcode click on file -> packages -> reset package Caches and resolve package versions
if issue still not fixed, you can manually add packages from file -> Add package dependencies -> search for “https://github.com/youtube/youtube-ios-player-helper” & “https://github.com/Alamofire/Alamofire”
then select and download.

TabBar Behavior:
When playing video inLine when we hold and swipeUP, we get white tabBar.

API Limitations:
The app does not handle rate-limiting errors from TMDB API gracefully.
Ensure the API key is valid and has sufficient request quotas.

Portrait Lock:
The app is locked to portrait mode except during video playback. Some devices with unusual aspect ratios may experience slight UI misalignment.

Offline Mode:
The app does not support offline usage. It requires an active internet connection for API calls.

Genre and Runtime Data:
Some movies may not have complete genre or runtime data due to limitations in the TMDB API responses.


