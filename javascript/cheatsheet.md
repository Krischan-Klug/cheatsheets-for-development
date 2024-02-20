# JavaScript CheatSheet

## Basics

<a href="https://www.codecademy.com/resources/cheatsheets/language/javascript">Guides</a>

## Formulars tips and tricks


`code`
//how to get data out of a formular with the browser API

const form = document.querySelector('[data-js="form"]');

form.addEventListener("submit", (event) => {
  event.preventDefault();

  const formData = new FormData(event.target);
  const data = Object.fromEntries(formData);

  console.log(data);
});
