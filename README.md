# SLIDE THEORY

A polished, responsive 15-puzzle game built with HTML, CSS, and vanilla
JavaScript. Arrange the numbered tiles from **1 to 15** in order, track
your moves and time, beat your best score, or use the built-in solver to
see the puzzle solved.

## Features

-   **Interactive 4×4 board** --- move tiles into the empty space.
-   **Three difficulty levels** --- Easy, Intermediate, and Hard.
-   **Move counter and timer** --- track your progress during each game.
-   **Best scores** --- saves the fewest-move score separately for each
    difficulty in the browser.
-   **Hint system** --- highlights a tile that moves the puzzle toward
    its solution.
-   **AI Solve** --- animates a solution using the IDA\* search
    algorithm.
-   **Solvability checking** --- uses inversion counting and the blank
    tile's row to reject unsolvable shuffled boards.
-   **Light and dark themes** --- supports manual theme switching and
    the system color preference.
-   **Sound effects** --- optional move and victory sounds.
-   **Settings dialog** --- change difficulty, sound, theme, and clear
    saved best scores.
-   **Responsive layout** --- designed to work on desktop and mobile
    screens.
-   **Keyboard controls** --- use the arrow keys to move tiles when the
    game board is visible.

## How to Play

1.  Open the game and select **Play now** or scroll to the Play section.
2.  Select a difficulty using the settings button.
3.  Click a tile next to the empty space to slide it, or use the arrow
    keys.
4.  Arrange the tiles in numerical order from left to right, top to
    bottom.
5.  The empty space should end in the bottom-right corner.
6.  Use **Reset** to restart the current board, **New Game** to shuffle
    a new board, or **Hint** for help.
7.  Choose **AI Solve** to watch the solver attempt to solve the current
    board.

**Scoring note:** A game in which Hint or AI Solve is used does not
count toward the best-score record.

## How the Solver Works

The project includes an **IDA\*** (Iterative Deepening A\*) solver. It
combines:

-   **Manhattan distance** --- estimates how far each tile is from its
    goal position.
-   **Linear conflict** --- adds a lower-bound penalty when tiles in the
    same goal row or column block each other.
-   **Iterative deepening** --- searches within increasing cost limits
    until it finds a solution.
-   **Web Worker support** --- runs the search in a worker when
    available, with a time-sliced fallback to keep the interface
    responsive.

The solver aims to find a shortest solution. Some difficult positions
may take too long and time out.

## Technologies

-   **HTML5** for the page structure
-   **CSS3** for responsive styling, themes, animations, and layout
-   **Vanilla JavaScript** for game logic, controls, timer, persistence,
    and solving
-   **Web Workers** for background solver execution when supported
-   **Web Audio API** for sound effects
-   **localStorage** for settings and best scores

No external libraries, package manager, or build step are required for
the supplied single-file version.

## Run Locally

### Option 1: Open the HTML file

1.  Download or clone this project.
2.  Open `SLIDE THEORY-2.html` in a modern browser.
3.  Start playing.

### Option 2: Use a local development server

If you prefer serving it over HTTP, place the HTML file in a folder and
run a simple local server from that folder:

``` bash
python3 -m http.server 8000
```

Then open <http://localhost:8000> and select the HTML file if it does
not open automatically.

## Deploy for Free

This is a static website, so it can be hosted on a static-site service
without a backend.

### Netlify

1.  Keep the HTML file in a project folder.
2.  For a cleaner URL, rename it to `index.html`.
3.  Open [Netlify](https://app.netlify.com/).
4.  Sign in and use the manual deploy / drag-and-drop option if
    available.
5.  Upload the folder containing `index.html`.
6.  Open the generated public URL and test the game.

### Cloudflare Pages

1.  Rename the HTML file to `index.html`.
2.  Put it in a project folder or a GitHub repository.
3.  Create a Pages project in [Cloudflare
    Pages](https://pages.cloudflare.com/).
4.  Connect the repository or use a supported direct-upload workflow.
5.  Deploy and test the published URL.

### GitHub Pages

1.  Create a GitHub repository and add the HTML file.
2.  Rename the file to `index.html` so it loads as the site homepage.
3.  Open the repository's **Settings → Pages**.
4.  Choose the branch and root folder to publish.
5.  Save and wait for GitHub Pages to publish the site.

Hosting-provider interfaces and free-plan limits can change, so check
the provider's current instructions if a menu looks different.

## Project Structure

The supplied version is self-contained:

``` text
slide-theory/
├── index.html       # Rename SLIDE THEORY-2.html to this for deployment
└── README.md        # Project documentation
```

The HTML file contains the page markup, CSS styles, and JavaScript logic
in one file.

## Browser Compatibility

Use a recent version of Chrome, Edge, Firefox, or Safari. Some browser
settings or privacy modes may restrict local storage or background
workers; the game includes fallback handling for storage and solver
execution.

## Data and Privacy

-   Game settings and best scores are stored in the browser's
    `localStorage`.
-   The project does not require an account or backend server.
-   Clearing browser site data may remove saved settings and best
    scores.
-   Scores are stored locally and are not shared between devices
    automatically.

## License

No license is specified in the supplied project. Add a license file if
you want to define how others may use, modify, or redistribute the code.
