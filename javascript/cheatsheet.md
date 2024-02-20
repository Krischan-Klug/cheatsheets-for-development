# JavaScript CheatSheet

## Basics

<a href="https://www.codecademy.com/resources/cheatsheets/language/javascript">Guides</a>

## Important Codeblocks

### how to get data out of a formular with the browser API

```javascript
const form = document.querySelector('[data-js="form"]');

form.addEventListener("submit", (event) => {
  event.preventDefault();

  const formData = new FormData(event.target);
  const data = Object.fromEntries(formData);
});
```

### How to fetch data from API
```javascript
const url = "sampleURL"

async function fetchData() {
  const response = await fetch(url);
  const json = await response.json();

  return json.results; //Array of results
}
```
### How to create and render with functions sample
```javascript
fetchDataAndRender(); //Call

async function fetchDataAndRender() {
  const myData = await fetchData(); // look one example above!
  Render(myData);
}

async function Render(data) {
  data.forEach((element) => {
    const card = Card(element);

    RenderElement(card);
  });
}

const root = document.getElementById("root");

function RenderElement(element) {
  root.appendChild(element); // Append the Element to the page
}

function Card(characterData) {
  const card = document.createElement("article"); // Create a new article Element
  card.classList.add("card"); // Add the class 'card'

  // Fill the article element with content.
  const heading = document.createElement("h2");
  heading.textContent = characterData.name;

  card.append(heading);

  const eyeColor = document.createElement("p");
  eyeColor.textContent = `Eye color: ${characterData.eye_color}`;

  card.append(eyeColor);

  const birthYear = document.createElement("p");
  birthYear.textContent = `Birth Year: ${characterData.birth_year}`;

  card.append(birthYear);

  return card;
}


```

