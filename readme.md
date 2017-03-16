![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# DE | Cinema Billboard

![](images/image-1.png)

## Learning Goals

After this lesson, you will be able to:

- Create an angular service to share information with all the components in your application.
- Create angular routes with parameters.
- Create different components related between them.

## Requirements

- [Fork this repo](https://guides.github.com/activities/forking/)
- Clone your fork into your `~/code/labs` folder.

## Submission

Upon completion, run the following commands:

```bash
$ git add .
$ git commit -m"done"
$ git push origin master
```

Navigate to your repo and create a Pull Request -from your master branch to the original repository master branch.

In the Pull Request name, add your campus, name, and last name separated by a dash "-".

## Deliverables

All the files of your project, including the service and the different components you will use to create your solution.

## Introduction

Nowadays, movie cinemas are hurting. The internet is damaging the industry, allowing people to search and download movies without paying for them. A cinema has contacted Ironhack to help them change people's views on movies.

Their idea is to redo their website by using Angular2. They think that if they use the latest technologies on their website, people will see them in a hip and cool new way.

The cinema has 5 different rooms, where you will be able to watch 5 movies. The newset purposal of this cinema is that they are not going to show you the lastest movies, but your favorite ones! Your task will be to help them decide which movies to show in the rooms.

### Iteration 1 | Service Creation

First, we are going to create an Angular Service to contain all of the movies' information. This service is going to have the following:

#### Movies

`movies` will be an Array of objects, that will contain one item per each cinema room. Each object inside the array will have the following information:

- **`id`** (Number) - A unique number used to distinguish between movies.
- **`title`** (String) - Contains the movie title.
- **`poster`** (String) - A URL to a poster image for the movie.
- **`synopsis`** (String) - A brief description about the movie.
- **`Genres`** (Array of Strings) - The genres of a movie, such as "Adventure", "Action", "Romantic Comedy" etc.
- **`year`** (Number) - Movie's release year.
- **`director`** (String) - Director of the movie.
- **`actors`** (Array of Strings) - The movie's actors names, using one string per each actor.
- **`hours`** (Array of Strings) - The times the movie is showing. i.e. `Wednesday 19:30, 22:30` would be an element of this array to indicate that you can watch a movie on wednesday at 19:30h and 22:30h.
- **`room`** (Number) - Room number of the movie. Will be a value between 1 and 5.

In the `movies` array you will have to create an element for each movie, and fill the different fields we just defined. **Use your favorite movies to do this**.

#### Methods

The movies service will also have two different methods that will be used later on the project. The methods you have to create are the following:

- **`getmovies()`** - Returns the array of movies.
- **`getMovie(id)`** - Will receive  a movie's number id as a parameter, and will return correct movie.

#### Tasks

- Create a `Cinema` service.
- Add a `Movies` array of objects. Each object will have the following properties:
  - `id`, number.
  - `title`, string.
  - `poster`, string.
  - `synopsis`, string.
  - `genres`, array of strings.
  - `year`, number.
  - `director`, string.
  - `actors`, array of strings.
  - `hours`, array of strings.
  - `room`, number.
- Add a `getMovies()` method, that will return the array of movies.
- Add a `getMovie(id)` method, that receives a number id as a parameter and returns an object from the `Movies` array.

### Iteration 2 | Routes

In the second iteration of this exercise, we will create two different routes to show the details of our cinema.

In the main page of the application, we will show a list with all the movies in the cinema. Once you click on one of the movies, you will see the movie's details.

We will create the components that will be used to show the information: `MyHomeComponent` and `MyMovieComponent`. Once we have created all the components we need, we have to create two different routes:

- `/home`, that will render the `MyHomeComponent` component.
- `/movie/:id`, that will render the `MyMovieComponent` component.

Remember, we also have to add the `<router-outlet></router-outlet>` tag in the `app.component.html` file to be able to load the different information depending on the indicated route.

#### Tasks

- Create two components:
  - `MyHomeComponent`
  - `MyMovieComponent`
- Create the different routes to show each component:
  - `/home`, to show `MyHomeComponent`
  - `/movie/:id`, to show `MyMovieComponent`
- Add `<router-outlet></router-outlet>` tag to `app.component.html` file

### Iteration 3 | Home Page

We are going to work on the `MyHomeComponent` component we created in the iteration above. We have to use the `Cinema` service to load all the movies information we have declared in the `movies` array.

In the main page, we will show a list of all the movies. In addition, we will add a link to view the details of a movie.

Remember, we're trying to stand out in the cinema world and convert all of the hip millenials. Add some styling to the home page.

![](images/image-2.png)

#### Tasks

- Load the movies from the `Cinema` service, with the `getMovies()` method we've previously defined.
- Display the movies on the `/home` page.
- Create a link for each movie that directs the user to `/movie/:id`.
- Style the page.

### Iteration 4 | Movie Page

Once the user visits a movie page, we have to show them the movie's details. Again, we need to use the `Cinema` service to load the information of one movie. On this page, display *all* of the movie's details, and create a back button to return to the home page.

In addition, add a bit of styling to make the details page look nice.

![](images/image-3.png)

#### Tasks

- Load the movie from the `Cinema` service, with the `getMovie()` method defined on it. Use the `:id` parameter in the URL to get the correct movie.
- Show the movie's details in the view.
- Add a "Go back" button, that takes the user to the home page.
- Style the page.

/Happy coding!
