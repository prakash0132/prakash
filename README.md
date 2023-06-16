<!DOCTYPE html>
<html>
<head>
 
  <title>fancymovies</title>
  <link rel="stylesheet" type="text/css" href="movie1,.css">
</head>

<body>
  <header>
    <head>
      <meta charset="UTF-8">
      <title>Movie Search</title>
    </head>
    <body>
      <input type="text" id="searchBox" placeholder="Search movies...">
      <button id="searchButton">Search</button>
      <ul id="movieList"></ul>
      <script>
        const searchBox = document.getElementById('searchBox');
        const searchButton = document.getElementById('searchButton');
        const movieList = document.getElementById('movieList');
  
        searchButton.addEventListener('click', () => {
          const searchTerm = searchBox.value;
          searchMovies(searchTerm);
        });
  
        function searchMovies(searchTerm) {
          // Use an API or database to search for movies matching the search term
          // and add them to the movieList element as list items.
          // Here's an example using the Open Movie Database (OMDb) API:
  
          const apiKey = 'your-api-key-here';
          const url = `https://www.omdbapi.com/?apikey=${apiKey}&s=${searchTerm}`;
  
          fetch(url)
            .then(response => response.json())
            .then(data => {
              movieList.innerHTML = ''; // clear the list before adding new results
              if (data.Search) {
                data.Search.forEach(movie => {
                  const li = document.createElement('li');
                  li.textContent = movie.Title;
                  movieList.appendChild(li);
                });
              } else {
                const li = document.createElement('li');
                li.textContent = 'No results found.';
                movieList.appendChild(li);
              }
            })
            .catch(error => {
              console.error('Error searching for movies:', error);
            });
        }
      </script>
    
    </body>
    
    <h1>fancymovies</h1>
    <nav>
      <ul>
        <li><a href="#">Trending</a></li>
        <li><a href="#">Browser</a></li>
        <li><a href="#">leatest</a></li>
        <li><a href="#">older</a></li>
      </ul>
    </nav>
  </header>
 

  <main>
    <section class="hero-image">
      <h2>choose your favorite movies to download</h2>
      <p>click the down button to see latest movies</p>
      <button>movie-list</button>
    </section>

    <section class="movie-list">
      <h2>New Movies</h2>
      <ul>
        <li>
          <img src="mm1.jpg">
          <h3>race 3 dual audio in 4k
            720p,1080p
          </h3>
          <p>Release Date: <span>2022</span></p>
          <p>Rating: <span>8.0</span></p>
          <button>download</button>
        </li>
        <li>
          <img src="mm2.jpg">
          <h3>Movie Title 2</h3>
          <p>Release Date: <span>2021</span></p>
          <p>Rating: <span>7.5</span></p>
          <button>download</button>
        </li>
        <li>
          <img src="mm3.jpg">
          <h3>Movie Title 3</h3>
          <p>Release Date: <span>2023</span></p>
          <p>Rating: <span>9.2</span></p>
          <button>download</button>
          <button id="download-btn">Download</button>
<div id="timer">11</div>

        </li>
      </ul>
    </section>
  </main>
  <style>
    /* Footer styling */
    footer {
      background-color: #504d4d;
      color: #fff;
      padding: 20px;
      text-align: center;
    }

    /* Link styling */
    footer a {
      color: #fff;
      text-decoration: none;
      padding: 0 10px;
    }

    footer a:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>
  <!-- Main content here -->
  <h1>Welcome to Movie Website</h1>
  <p>Check out our latest movie releases!</p>

  <footer>
    <!-- Footer content here -->
    <p>&copy; 2023 Movie Website</p>
    <nav>
      <a href="#">Home</a>
      <a href="#">Movies</a>
      <a href="#">About Us</a>
      <a href="#">Contact Us</a>
    </nav>
  </footer>

  <footer>
    <p>&copy; 2023 fancymovies</p>
  </footer>
</body>
</html>
