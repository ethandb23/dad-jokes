 <h1>Dad Jokes App</h1>
    <p>This project is a basic dad joke app that uses the DadJokes API to display random dad jokes on the screen. The app has minimal styling and was created using HTML, CSS, and JavaScript.</p>

<a href="https://dad-jokes-api-list-project-2.netlify.app">Deployed App</a>


<h2>Getting Started</h2>
<p>Clone the GitHub repository to your local machine by executing the following command in your terminal:</p>
<pre><code>git clone https://github.com/ethandb23/TTT</code></pre>
<p>Open the project folder in your preferred code editor. You can use any code editor such as Visual Studio Code, Atom, or Sublime Text.</p>
<p>Install any necessary dependencies by running the following command in your terminal:</p>
<pre><code>npm install</code></pre>
<p>This will install any required packages and dependencies required to run the project.</p>
<p>To build and start the application, run the following command in your terminal:</p>
<pre><code>npm start</code></pre>
<p>This will compile the code and start a local server at <a href="http://localhost:3000/">http://localhost:3000/</a>.</p>
<p>Finally, open your preferred web browser and navigate to <a href="http://localhost:3000/">http://localhost:3000/</a>. This will open the index.html file and display the application.</p>

<h2>About</h2>
<p>This was a solo project completed during a 1-week sprint.</p>


<h3>Technologies Used</h3>
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
  <li>RESTful API</li>
</ul>

<h3>Big Goals</h3>
<ul>
  <li>You will be working individually for this project, but we'll be guiding you along the process and helping as you go. Show us what you've got!</li>
  <li>A front-end list based React application that updates the UI and makes requests to the API.</li>
  <li>Include data from a third-party API.</li>
  <li>Pull data into the application using an API</li>
  <li>Deploy your app online, where the rest of the world can access it.</li>
  <li>Craft a README.md file that explains your app to the world</li>
</ul>




<p>During the planning stage, I began with pseudocode:</p>

    
    

<p>
// Define a function to fetch a random joke from the API
function getRandomJoke() {
</p>
<p>
  // Make an HTTP request to the API endpoint
  const response = fetch('https://icanhazdadjoke.com/', {
    headers: {
      'Accept': 'application/json'
    }
  });
  </p>
    // Parse the response JSON and return the joke
  const joke = response.json();
  return joke;
}
<p>
// Define a function to display a joke on the screen
function displayJoke(joke) {
</p>
<p>
  // Get the HTML element to display the joke
  const jokeElement = document.getElementById('joke');
</p>
<p>
  // Set the text of the element to the joke
  jokeElement.textContent = joke;
}
</p>
<p>
// Define an event listener for a button to fetch and display a random joke
const button = document.getElementById('button');
button.addEventListener('click', async () => {
</p>
<p>
  // Fetch a random joke from the API
  const joke = await getRandomJoke();
</p>

<p>
  // Display the joke on the screen
  displayJoke(joke);
});
</p>

<p>This pseudocode defines two functions: getRandomJoke and displayJoke. The getRandomJoke function makes an HTTP request to the icanhazdadjokes API and returns a random joke. The displayJoke function takes a joke as an argument and displays it on the screen by setting the text of an HTML element.</p>
<p>Finally, an event listener is defined for a button. When the button is clicked, it calls the getRandomJoke function to fetch a random joke, and then calls the displayJoke function to display it on the screen.</p>



<h2>Code</h2>
<p>The majority of the functionality of this app is coming from the DadJokes API. One of the key challenges I encountered during the build process was working with asynchronous JavaScript to fetch the data from the API and display it on the screen. Here is an example of the code I wrote to fetch the jokes:</p>

<p>The component has two methods, addJoke and addToFavorites, both of which update the state of the component using this.setState(). addJoke takes in a new joke and adds it to the beginning of the jokes array in the state using the spread operator. addToFavorites takes in a joke and adds it to the beginning of the favorites array in the state using the spread operator.
</p>

<pre><code>
Tclass App extends Component {
  state = {
    jokes: [],
    favorites: []
  };

  addJoke = (newJoke) => {
    this.setState({ jokes: [newJoke, ...this.state.jokes] });
  };

  addToFavorites = (joke) => {
    this.setState({ favorites: [joke, ...this.state.favorites] });
  };


</pre></code>

<p>
The render() method returns a fragment (designated by the empty tags <> and </>) that contains several other components, including AddJokeForm, JokeCard, JokesList, and FavoritesList.
</p>

<pre><code>
  render() {
    const { jokes, favorites } = this.state;
    return (
      <>
        <AddJokeForm addJoke={this.addJoke} />
        <JokeCard joke={jokes[0]} addToFavorites={this.addToFavorites} />
        <JokesList jokes={jokes.slice(1)} addToFavorites={this.addToFavorites} />
        <FavoritesList favorites={favorites} />
      </>
    );
  }
}

export default App;

</code></pre>

<p>AddJokeForm is a component that accepts a addJoke function as a prop, which will be used to add a new joke to the jokes array in the state. JokeCard is a component that displays the first joke in the jokes array along with a button that triggers the addToFavorites function to add the joke to the favorites array. JokesList is a component that displays the remaining jokes in the jokes array (excluding the first one), and also provides a button to add each joke to the favorites array. FavoritesList is a component that displays all of the jokes in the favorites array.

</p>


<h2>Challenges</h2>

<p>To solve the challenge of working with asynchronous JavaScript to fetch data from the API, I utilized the async/await syntax to make sure that my code waited for the API response before proceeding with any further actions. This allowed me to effectively manage the flow of data and avoid errors.
</p>

<p>When encountering errors in code, I often rely on two essential techniques to identify the source of the problem: console logging and breakpoints. By strategically placing console.log() statements throughout my code, I can see the value of variables at various points in the execution, helping me to pinpoint where the issue might be originating. Additionally, using breakpoints allows me to pause execution at a specific line and observe the state of the program. Additionally, I thoroughly read the documentation for the API to understand the expected format of the data, which helped me identify and resolve any issues with the data returned by the API.</p>

<h2>Wins and Takeaways</h2>
<p>Undertaking a new project is always an opportunity for growth and learning, and this recent experience was no exception. Throughout this project, I gained a deeper understanding of several key topics, including asynchronous JavaScript and working with APIs. Asynchronous programming can be a challenge to master, but this project provided me with ample opportunities to hone my skills in this area. I learned how to use Promises, async/await, and other techniques to manage asynchronous code and ensure smooth execution.
</p>

<p>Working with APIs was another important aspect of this project. I became more comfortable with the process of configuring APIs to allow access to resources, and the use of CORS headers. I learned how to handle different types of API requests, parse JSON responses, and handle errors gracefully. This knowledge will be invaluable in future projects that rely on external APIs for data and functionality.
</p>


<p>In addition to these technical skills, I also gained some valuable experience working on a solo project with a short timeframe. This required me to manage my time effectively, prioritize tasks, and make strategic decisions about which features to implement. I also explored some new CSS techniques, such as using grid layout and custom properties to streamline my styling workflow. Overall, this project was a great learning experience that helped me to grow both personally and professionally</p>

<h2>Potential Improvements</h2>
<ul>
  <li><strong>Better styling:</strong>A more visually appealing and user-friendly interface can enhance the user experience of the app. This can include a better layout, typography, and color scheme, as well as a more visually engaging way to display jokes. Additionally, adding animations or other visual effects can make the app more engaging and fun to use.</li>
  <li><strong>User Creation:</strong>  Implementing user creation functionality can allow users to create and save their own custom jokes to the app. This can be a great way to encourage user engagement and interaction with the app, as well as provide a personalized experience for each user.</li>
  <li><
Differentiation between fetched jokes and user-created jokes: If users are able to create and save their own jokes, it may be helpful to differentiate between these user-created jokes and the jokes that are fetched from the API. This can be done by visually distinguishing between the two types of jokes, or by labelling or categorizing them differently in the app's database or UI. This can help users keep track of which jokes they have created and which ones are from the API. Additionally, it can be a fun way to showcase the creativity and humor of users who contribute their own jokes to the app.
</li>
</ul>
