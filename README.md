# pokemon_search_app
# Hosted Link:- https://tulasidurga1.github.io/pokemon_search_app/
# HTML Structure:-
````
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags and external CSS and JavaScript files -->
</head>
<body>
    <div class="content-wrapper">
        <header>
            <!-- Page title -->
        </header>
        <main>
            <form id="pokemon-type-filter">
                <!-- Dropdown for filtering by Pokémon type -->
            </form>
            <form id="pokemon-search-form">
                <!-- Input field for searching Pokémon by name -->
            </form>
            <section class="form-spacers"></section>
            <section id="pokedex">
                <!-- Pokémon cards will be displayed here -->
            </section>
        </main>
    </div>
</body>
</html>
````
- This HTML structure defines the basic layout of a webpage. It includes meta tags for character encoding and viewport settings.
- It links to an external stylesheet (style.css) and a JavaScript file (index.js).
- The <title> tag sets the title of the webpage to "GeeksterMon."
- The main content of the page is organized inside the <div class="content-wrapper">.
- There is a page header with the title "GeeksterMon."
- The main content area contains two forms: one for filtering Pokémon by type and another for searching Pokémon by name.
- The "pokedex" section is where Pokémon cards will be displayed.
###JavaScript Code (index.js):

### javascript:-
// Define API URLs and query parameters
````
const pokeTypeURL = 'https://pokeapi.co/api/v2/type/';
const pokeQueryParams = new URLSearchParams(window.location.search);
const typeParams = new URLSearchParams(window.location.search);
const typeSearch = typeParams.get('type');

// Select DOM elements
const pokedex = document.getElementById('pokedex');
const pokemonSearchForm  = document.querySelector('#pokemon-search-form');
const pokemonTypeFilter = document.querySelector('.type-filter');

// Arrays and Sets to store Pokémon data
let pokemonArray = [];
let uniqueTypes = new Set();

// Function to fetch Pokémon data from the API
const fetchPokemon = () => {
    // Create an array of promises for fetching Pokémon data
    const promises = [];
    for(let i = 1; i <= 151; i++){
        const pokemonURL = `https://pokeapi.co/api/v2/pokemon/${i}`;
        promises.push(fetch(pokemonURL).then(response => response.json()))
    }

    // Wait for all promises to resolve
    Promise.all(promises)
    .then(allPokemon => {
        // Map the fetched data into a more structured format
        const firstGenPokemon = allPokemon.map(pokemon => ({
            // Extract relevant data for each Pokémon
        }));
        pokemonArray = firstGenPokemon;
        // Call functions to display Pokémon cards and generate type filters
    });
}

// Event listener for searching Pokémon by name
pokemonSearchForm.addEventListener('input', (event) => {
    // Filter Pokémon based on user input and display matching cards
});

// Function to clear the Pokémon display
function clearPokedex() {
    // Remove all Pokémon cards from the "pokedex" section
}

// Function to create Pokémon cards and display them
function createPokemonCards(pokemons) {
    // Loop through the list of Pokémon and create cards for each one
}

// Function to create a single Pokémon card
function createPokemonCard(pokemon) {
    // Create HTML elements for the front and back of the card
    // Populate the card with Pokémon data
    // Append the card to the "pokedex" section
}

// Function to generate type filters
function generateTypes() {
    // Loop through unique Pokémon types and create filter options
    // Append filter options to the type filter dropdown
}
`````
- The JavaScript code starts by defining API URLs and selecting DOM elements that will be manipulated.
- It also defines arrays and sets to store Pokémon data and unique Pokémon types.
- The fetchPokemon function is responsible for fetching Pokémon data from the PokeAPI for the first 151 Pokémon.
- There's an event listener on the search form to filter Pokémon by name.
- Several functions are defined to manipulate and display Pokémon data, including clearing the display, creating Pokémon cards, and generating type filters.
### CSS Styles (style.css):

- The CSS code contains styling rules for the HTML elements used in the webpage. Here's a summary of some key CSS rules:
- Setting a background color for the body.
- Styling the page title (h1).
- Centering the search bar and type filter.
- Styling for Pokémon cards using the "flip card" technique.
- Styling for individual Pokémon types, with specific background colors for each type.
- Overall, this code creates a webpage for displaying Pokémon cards that can be filtered by type and searched by name.<br> It fetches Pokémon data from the PokeAPI, styles the page, and dynamically generates filter options based on Pokémon types.
