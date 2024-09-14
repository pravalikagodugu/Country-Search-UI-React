# Country-Search-UI-React
 A simple React app that features a search bar to find countries by name or capital. It gives autocomplete suggestions and an user interface for easy reach. Here,we use JSON data to provide correct search results.
### Features
- Search by country or capital.
- Displays real-time suggestions as you type.

### Tools and Technologies
- React.js for the UI
- JSON data for countries and capitals
- CSS for basic styling

npx create-react-app Country-Search-UI-React
cd Country-Search-UI-React
import React, { useState } from 'react';

const SearchBar = ({ countries }) => {
  const [query, setQuery] = useState('');
  const [suggestions, setSuggestions] = useState([]);

  const handleChange = (e) => {
    const value = e.target.value;
    setQuery(value);
    if (value) {
      const filteredSuggestions = countries.filter(country =>
        country.country.toLowerCase().includes(value.toLowerCase()) ||
        country.capital.toLowerCase().includes(value.toLowerCase())
      );
      setSuggestions(filteredSuggestions);
    } else {
      setSuggestions([]);
    }
  };

  return (
    <div>
      <input
        type="text"
        value={query}
        onChange={handleChange}
        placeholder="Search for a country or capital"
      />
      <ul>
        {suggestions.map((suggestion, index) => (
          <li key={index}>{suggestion.country} - {suggestion.capital}</li>
        ))}
      </ul>
    </div>
  );
};

export default SearchBar;

import React from 'react';
import SearchBar from './SearchBar';
import './App.css';

const countries = countries.js

function App() {
  return (
    <div className="App">
      <h1>Country Search</h1>
      <SearchBar countries={countries} />
    </div>
  );
}

.App {
  text-align: center;
  padding: 20px;
}
input {
  padding: 10px;
  width: 300px;
  margin-bottom: 20px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 5px 0;
  font-size: 18px;
}

export default App;


