# HTTP / AJAX II React Module Project: Movie CRUD

This module explored HTTP methods, REST interfaces, CRUD apps and using put and delete to allow editing and deleting functionality. We also dug into how to pass props to Route connected components and using URL params to get values from an api. In this project, you will practice each of these skills by implement various pieces of functionality in a movie database CRUD app.

## Objectives

- Understand how to use the post, put and delete HTTP methods to interact with server data.
- Understand how to sync server data with an applications internal state.
- Understand how to pass values into a Route component to allow for the updating of state.

## Introduction

CRUD applications are the foundation of most web applications. Being able to manage creating, edit and deleting data from an external source is as key a skill as it gets. In this project, you will complete the code necessary to allow all of these fundamental actions.

![Movie DB Example](project-goals.gif)

***Make sure to complete your tasks one at a time and complete test each task before proceeding forward.***

## Instructions

### Task 1: Project Set Up

This project includes frontend and backend pieces that run locally on your computer.

Follow these steps to set up the app:

- [x] Create a forked copy of this project
- [x] Clone your own fork of the repository
- [x] Download dependencies by executing `npm install`
- [x] Run the app by executing `npm start`

You should now have your app running in Chrome on `http://localhost:3000`

### Task 2: Project Requirements

#### Editing a Movie
>
> *Let's start by walking through the process of adding the routing, component and service calls need for resource updating*

- [x] First, we need to be able to navigate to the edit movie component. In App.js, add in the `<EditMovieForm>`component to the supplied edit route.

- [x] Next, we need to grab the id being passed into the component through the url. Use the `useParams` hook to get the id value.

- [x] We need to be able to load in the current movie's attributes into our local form state. When `EditMovieForm` mount, retrieve our current id's movie from the api and save the data returned to local state.

- [x] At this point, nothing happens when the edit form is submitted. Add in the api call needed to update the server with our updated movie data.

- [x] Don't forget to make sure that your server data and your local state are in sync! Make any changes needed to the edit route to give the edit form access to App's `setMovies` method.

- [x] Now that we have access to `setMovies`, made sure the updated list of movies is saved to our global state.

- [x] Redirect the user to the currently edited movie's individual info page.

#### Deleting a Movie
>
> *You added in a CRUD feature! Good job! Now let's get deleted squared away...*

- [x] Identify the component that holds the "button" needed for deletion. Add an event handler to that button.

- [x] Build an event handler that makes a request to delete the currently viewed movie. Observe what is returned from the request.

- [x] You will once again need to keep the server and state data in sync. In `App.js`, complete the `deleteMovie` method so that it receives an id, filters out any movie with that id and sets state to that resultant movie list.

- [x] Pass `deleteMovie` into the appropriate component.

- [x] Run `deleteMovie` on the currently selected movie when your delete request is complete and redirect the user to the `/movies` route.

#### Adding a Movie
>
> *Alright! You ready! Let's see you use the skills of the previous steps to build a crud function from start to finish.*

- [x] Use `EditMovieForm.js` as a model to build an `AddMovieForm` component from scratch. The component should hold all the attributes of a new movie in local state.

- [x] Add in a route that allows access to `AddMovieForm`.

- [x] Locate the part of the ui that should redirect to your new `AddMovieForm`. Make that button works as expected.

- [x] In `AddMovieForm,` add an event handler for form submission. When the form is submitted, run the appropriate request for adding a movie with the component's state values.

- [x] Make sure your component has access to and runs and modifications needed to global state and redirects to `/movies` after creation.

### Stretch goals

- Make the added DeleteMovieModal appear and be reacted to before deletion occurs.
- Add in `addToFavorites` functionality. When the favorite button is pushed in the `Movie` component, make sure that when the favorite button is pushed, the id and name of the currently viewed into the favorite state slice in `App.js.`
- For extra credit, ensure that only unique movies can be added as favorites. Consider the `.find` method for arrays.
- Add in some Style!

### Resource: API documentation

#### GET `http://localhost:9000/api/movies`

- Retrieves all the Movies with the following formatting:

```js
[{
  id: 5,
  title: 'Tombstone',
  director: 'George P. Cosmatos',
  metascore: 89,
  genre: "Drama",
  description: : "A successful lawman's plans to retire anonymously in Tombstone, Arizona are disrupted by the kind of outlaws he was famous for eliminating."
}]
```

#### GET `http://localhost:9000/api/movies`

- Retrieves all movies on the server.

#### GET `http://localhost:9000/api/movies/:id`

- Retrieves a movie with the passed value as id.

#### POST `http://localhost:9000/api/movies`

- Adds the movie passed in through body to the server movies list. Returns updated movies list.

#### PUT `http://localhost:9000/api/movies/:id`

- Replaced the movie with the passed in id with data passed in through body. Returns update movies list.

#### DELETE `http://localhost:9000/api/movies/:id`

- Removed movie with the passed in id. Returns the deleted movie's id.
