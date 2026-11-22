# cinevibe

CineVibe – A Mood-Based Movie Discovery App

Final Term Project Proposal – Phase 1

Course: React Native App Development
Application Name: CineVibe
Team Name: CineVibe Developers
Student 1: Raschit Singh Bhangu
Student 2: Khushank Sardana
GitHub Repository: https://github.com/sardanakhushank7-debug/cinevibe

⸻

1. Project Overview

CineVibe is a React Native mobile application designed to help users discover movies based on their mood or the type of experience they are looking for.

Sometimes people want to watch a movie but are unsure what to choose. They might want something relaxing, mysterious, romantic, funny, or exciting without having a specific movie in mind.

CineVibe aims to make this process easier by allowing users to describe their current vibe or select from a list of predefined moods. The application will then suggest movies that match their preferences.

The app will use The Movie Database (TMDB) API to retrieve real movie information, including titles, posters, ratings, genres, release dates, and descriptions.

The application will not require a database or locally stored movie information. Movie data will be retrieved through API requests.

2. Project Objectives

The main objective of CineVibe is to create a simple and interactive movie discovery experience that helps users find something to watch based on their interests and mood.

The specific objectives are:

* Allow users to enter their mood or vibe using a text input.
* Provide predefined mood options for users who prefer quick selections.
* Recommend movies based on the selected or entered vibe.
* Display movie information retrieved from a live third-party API.
* Allow users to browse recommendations and view detailed information about individual movies.
* Create a clean and responsive interface that works on different mobile screen sizes.
* Apply React Native concepts such as React Hooks, navigation, reusable components, FlatList, and Flexbox.

3. Target Users

CineVibe is intended for people who enjoy watching movies but sometimes struggle to decide what to watch.

The target users include students, casual movie watchers, and anyone interested in discovering movies based on their current mood.

The application is especially useful for users who do not have a specific movie title in mind and would rather explore recommendations based on how they feel.

4. Main Application Features

4.1 Mood-Based Movie Discovery

Users will be able to describe the type of movie they want to watch by entering a short phrase.

For example:

* Something dark and mysterious
* A relaxing movie for a rainy evening
* Something funny and lighthearted
* An exciting adventure
* A romantic movie

The application will analyze keywords in the entered text and connect them to relevant movie genres.

For example, words such as “mysterious” or “suspenseful” may be associated with mystery and thriller movies.

The app will then request matching movies from the TMDB API.

4.2 Predefined Vibe Selection

Along with the text input, the application will provide predefined mood options.

Some planned options include:

* Happy & Fun
* Dark & Mysterious
* Romantic
* Action & Adventure
* Scary
* Relaxing
* Emotional
* Mind-Bending

Users can select one of these options instead of typing their own description.

Each option will be connected to one or more movie genres to retrieve relevant recommendations.

4.3 Movie Recommendations

After entering or selecting a vibe, users will be taken to a recommendations screen.

This screen will display a list of movies retrieved from the TMDB API.

Each movie will include its poster, title, release year, and rating.

The recommendations will be displayed using React Native’s FlatList component.

4.4 Movie Details

Users will be able to select a movie from the recommendations list to view more information.

The details screen will display the movie poster, title, overview, genres, release date, and rating.

This will help users decide whether the recommended movie matches what they want to watch.

5. Third-Party API

Selected API: The Movie Database (TMDB)

Website: https://www.themoviedb.org/

API Documentation: https://developer.themoviedb.org/

CineVibe will use the TMDB API to retrieve live movie information.

The application will use Axios to send HTTP requests and async/await to handle asynchronous operations.

The main API functionality will include:

* Discovering movies based on selected genres.
* Retrieving movie recommendations using genre filters.
* Fetching detailed information about a selected movie.
* Displaying movie posters and other information returned by the API.

TMDB does not directly interpret natural-language moods. To handle this, the application will use a simple keyword-matching approach.

For example, if a user enters “something scary,” the application will recognize the word “scary” and connect it to the horror genre.

If the text does not contain a recognized keyword, the application will display a message asking the user to try another description or choose a predefined vibe.

This approach allows the application to provide mood-based recommendations without requiring an additional AI service.

6. Planned Application Screens

The application will contain three main screens.

Screen 1: Home / Vibe Selection

The Home screen will be the starting point of the application.

It will display the CineVibe title, a short welcome message, a text input for entering a vibe, and predefined mood options.

A button labelled “Find My Movies” will allow users to request recommendations.

Main components:

* Application header
* TextInput for entering a vibe
* Predefined mood buttons
* Find My Movies button

Navigation: When the user submits a vibe, the application will navigate to the Recommendations screen.

Screen 2: Movie Recommendations

The Recommendations screen will display movies matching the user’s selected or entered vibe.

Movie information will be retrieved from the TMDB API using Axios.

The movies will appear in a scrollable list using FlatList.

Each movie card will display a poster, title, release year, and rating.

Main components:

* Screen header
* Selected vibe display
* FlatList
* Reusable MovieCard component
* Movie posters and ratings

Navigation: Selecting a movie will open the Movie Details screen.

Screen 3: Movie Details

The Movie Details screen will provide additional information about the selected movie.

The application will request detailed movie information from the TMDB API using the selected movie’s ID.

Main components:

* Movie poster
* Movie title
* Release date
* Genres
* Rating
* Movie overview
* Back navigation

Navigation: Users can return to the Recommendations screen to explore other movies.

7. Technical Implementation Plan

7.1 React Native and Expo

The application will be developed using React Native with Expo.

React Native will be used to create the mobile interface, while Expo will help with development and testing.

7.2 React Hooks

The application will use React Hooks to manage data and user interactions.

useState will be used to store the entered vibe, selected mood, movie recommendations, and other information required by the screens.

useEffect will be used to trigger API requests when appropriate, such as when the Recommendations or Movie Details screen loads.

7.3 Axios and Async/Await

Axios will be used to communicate with the TMDB API.

Async/await will help manage asynchronous requests and retrieve movie information without blocking the interface.

7.4 React Navigation

React Navigation will be used to move between the three main screens.

A Stack Navigator will manage navigation between the Home, Recommendations, and Movie Details screens.

7.5 FlatList

FlatList will be used on the Recommendations screen to display movie results efficiently.

Each movie will be rendered using a reusable MovieCard component.

7.6 Reusable Components

The application will use reusable components to keep the code organized and avoid repeating the same UI elements.

Planned components include:

* Header – Displays the application title or screen heading.
* VibeButton – Displays a predefined mood option.
* MovieCard – Displays a movie poster and basic information.
* SearchInput – Allows users to enter their vibe.

7.7 Flexbox and Responsive Design

The application will use StyleSheet and Flexbox for layout and styling.

Properties such as flex, flexDirection, justifyContent, alignItems, padding, margin, and positioning will be used where appropriate.

The interface will be designed to adjust to different mobile screen sizes.

7.8 Icons and Images

Expo Vector Icons will be used for navigation and interface elements.

Movie posters and images will be loaded from the TMDB image service.

8. Proposed Project Structure

The application will be organized into separate folders for screens, components, hooks, and API-related code.

CineVibe/
│
├── App.js
│
├── screens/
│   ├── HomeScreen.js
│   ├── RecommendationsScreen.js
│   └── MovieDetailsScreen.js
│
├── components/
│   ├── Header.js
│   ├── VibeButton.js
│   ├── MovieCard.js
│   └── SearchInput.js
│
├── hooks/
│   └── useApiData.js
│
├── services/
│   └── tmdbApi.js
│
├── utils/
│   └── vibeMapping.js
│
├── assets/
│
├── README.md
└── package.json

This structure may be adjusted during development if necessary.

9. User Stories

US1: As a user, I want to enter my current mood so that I can discover movies that match how I feel.

US2: As a user, I want to choose from predefined vibe options so that I can quickly find movies without typing.

US3: As a user, I want to browse recommended movies so that I can compare different options.

US4: As a user, I want to view a movie’s poster, rating, and release year so that I can get a quick idea of the movie.

US5: As a user, I want to select a movie and view its detailed information so that I can decide whether I want to watch it.

US6: As a user, I want to navigate between screens easily so that I can explore different movies without confusion.

US7: As a user, I want the application to work on different mobile screen sizes so that I can use it comfortably on my device.

10. UI Design and Wireframes

The application will follow a modern, movie-inspired visual style.

The planned design will use a dark background, contrasting text, clear buttons, and movie posters to create a cinematic appearance.

Three initial wireframes will be prepared to illustrate the planned layouts:

Wireframe 1 – Home Screen: Shows the application title, vibe text input, predefined mood options, and recommendation button.

Wireframe 2 – Recommendations Screen: Shows the selected vibe and a scrollable list of recommended movies.

Wireframe 3 – Movie Details Screen: Shows the selected movie’s poster, title, rating, genres, release date, and description.

These wireframes will guide the development of the final interface.


11. Team Members and Responsibilities

Team Name: CineVibe Developers

Student 1: Raschit Singh Bhangu
Student 2: Khushank

Both team members will contribute equally to the planning, development, testing, and final presentation of CineVibe.

Student 1 – Raschit Singh Bhangu (50%)

* Project planning and proposal preparation.
* Development of the Home / Vibe Selection screen.
* Implementation of free-text input and predefined mood selection.
* Development of the mood-to-genre matching functionality.
* Implementation of React Hooks for managing user input and selected moods.
* Development of reusable components for the Home screen.
* Testing and debugging assigned features.
* Contribution to GitHub documentation and final presentation.

Student 2 – Khushank (50%)

* UI wireframe design and project planning.
* Development of the Movie Recommendations screen.
* Development of the Movie Details screen.
* Integration of the TMDB API using Axios and async/await.
* Implementation of React Navigation and FlatList.
* Development of reusable movie cards and detail components.
* Testing and debugging assigned features.
* Contribution to GitHub documentation and final presentation.

Shared Responsibilities

Both team members will work together on:

* Maintaining the GitHub repository with meaningful commits.
* Ensuring consistent UI design across all screens.
* Integrating and testing the completed application.
* Resolving technical issues during development.
* Preparing the final project documentation.
* Recording the final video presentation.

Overall Team Contribution:

* Student 1: 50%
* Student 2: 50%

Both students will be responsible for completing their assigned tasks and ensuring the final application meets the project requirements.
12. Development Timeline

Stage 1 – Project Planning

Finalize the project concept, prepare the proposal, create the three UI wireframes, and set up the GitHub repository.

Stage 2 – Project Setup and UI Development

Create the React Native project using Expo and develop the basic layout of the Home, Recommendations, and Movie Details screens.

Stage 3 – API Integration

Connect the application to the TMDB API using Axios and implement the mood-to-genre matching functionality.

Stage 4 – Navigation and Components

Implement React Navigation, FlatList, React Hooks, and reusable components.

Stage 5 – Testing and Improvements

Test the application on mobile devices, verify API requests and navigation, and fix any identified issues.

Stage 6 – Final Submission

Complete the README.md file, update the GitHub repository, prepare the final project ZIP, and record the application demonstration video.

13. GitHub Repository

Repository Name: CineVibe

Repository Link: https://github.com/sardanakhushank7-debug/cinevibe

The GitHub repository will contain the project proposal, UI wireframes, preliminary README.md, and application source code as development progresses.

Meaningful commits will be made throughout the development process.

The README.md file will include the project overview, installation instructions, API information, screenshots, and team contributions.

14. Expected Outcome

By the end of the project, CineVibe is expected to be a functional React Native application that helps users discover movies based on their mood.

Users will be able to enter or select a vibe, browse movie recommendations retrieved from the TMDB API, and view detailed information about individual movies.

The project will demonstrate the use of React Native components, React Hooks, Axios, async/await, React Navigation, FlatList, reusable components, and responsive layouts.

The goal is to create an application that is simple to use, visually appealing, and useful for people who want to discover movies without having to search for a specific title.

⸻

End of Project Proposal

