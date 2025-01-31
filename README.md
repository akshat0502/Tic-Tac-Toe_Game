<h1>
  <a href="https://tic-tac-toe-game-azure-five.vercel.app/">Tic Tac Toe Game</a>
</h1>
<h1>Tic Tac Toe Game Using React</h1>
<p>This guide explains how to create and run a React-based Tic Tac Toe game for two players. The game allows players to take turns marking X and O on a 3x3 grid and declares the winner or a tie.</p>
<h2>Steps to Run the React App:</h2>
<ol>
  <li>
    <b>Install Node.js:</b>
    <p>Ensure you have Node.js installed on your system. Download it from <a href="https://nodejs.org" target="_blank">https://nodejs.org</a>.</p>
  </li>
  <li>
    <b>Set Up a React Project:</b>
    <p>Use <code>create-react-app</code> to set up your React project:</p>
    <pre><code>npx create-react-app tic-tac-toe</code></pre>
  </li>
  <li>
    <b>Start the Development Server:</b>
    <pre><code>npm start</code></pre>
    <p>This will open the app in your default web browser at <code>http://localhost:3000</code>.</p>
  </li>
  <li>
    <b>Create the Tic Tac Toe Game:</b>
    <p>Modify the <code>App.js</code> file and create components for:</p>
    <ul>
      <li><b>Game Board:</b> A 3x3 grid for players to click on.</li>
      <li><b>Square:</b> A single clickable square that displays X or O.</li>
      <li><b>Game Logic:</b> Handles player turns and checks for a winner or tie.</li>
    </ul>
    <p>Example code for the main components:</p>
    <pre><code>
      function Square({ value, onClick }) {
  return (
    <button onClick={onClick}>
      {value}
    </button>
  );
}
      function Board() {
  const [squares, setSquares] = React.useState(Array(9).fill(null));
  const [isXNext, setIsXNext] = React.useState(true);

     const handleClick = (index) => {
    if (squares[index] || calculateWinner(squares)) return;
    const nextSquares = squares.slice();
    nextSquares[index] = isXNext ? 'X' : 'O';
    setSquares(nextSquares);
    setIsXNext(!isXNext);
  };

  const winner = calculateWinner(squares);
  const status = winner ? `Winner: ${winner}` : `Next Player: ${isXNext ? 'X' : 'O'}`;
}
return (
    <div>
      <div>{status}</div>
      <div style={{ display: 'grid', gridTemplateColumns: 'repeat(3, 1fr)', gap: '5px' }}>
        {squares.map((square, index) => (
          <Square key={index} value={square} onClick={() => handleClick(index)} />
        ))}
      </div>
    </div>
  );
  function calculateWinner(squares) {
  const lines = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8],
    [0, 3, 6], [1, 4, 7], [2, 5, 8],
    [0, 4, 8], [2, 4, 6]
  ];
  for (let line of lines) {
    const [a, b, c] = line;
    if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
      return squares[a];
    }
  }
  return null;
}
export default function App() {
  return <Board />;
}
    </code></pre>
  </li>
  <li>
    <b>Build for Production:</b>
    <p>When your app is ready for deployment, run:</p>
    <pre><code>npm run build</code></pre>
    <p>This creates an optimized production build in the <code>build</code> folder.</p>
  </li>
</ol>
<hr>
# Getting Started with Create React App


This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

The page will reload when you make changes.\
You may also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can't go back!**

If you aren't satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you're on your own.

You don't have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn't feel obligated to use this feature. However we understand that this tool wouldn't be useful if you couldn't customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: [https://facebook.github.io/create-react-app/docs/code-splitting](https://facebook.github.io/create-react-app/docs/code-splitting)

### Analyzing the Bundle Size

This section has moved here: [https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size](https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size)

### Making a Progressive Web App

This section has moved here: [https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app](https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app)

### Advanced Configuration

This section has moved here: [https://facebook.github.io/create-react-app/docs/advanced-configuration](https://facebook.github.io/create-react-app/docs/advanced-configuration)

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)
