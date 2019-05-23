<script>
  import Header from "./Header.svelte";

  const dogIcon =
    "data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pg0KPCEtLSBHZW5lcmF0b3I6IEFkb2JlIElsbHVzdHJhdG9yIDE4LjAuMCwgU1ZHIEV4cG9ydCBQbHVnLUluIC4gU1ZHIFZlcnNpb246IDYuMDAgQnVpbGQgMCkgIC0tPg0KPCFET0NUWVBFIHN2ZyBQVUJMSUMgIi0vL1czQy8vRFREIFNWRyAxLjEvL0VOIiAiaHR0cDovL3d3dy53My5vcmcvR3JhcGhpY3MvU1ZHLzEuMS9EVEQvc3ZnMTEuZHRkIj4NCjxzdmcgdmVyc2lvbj0iMS4xIiBpZD0iQ2FwYV8xIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zOnhsaW5rPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5L3hsaW5rIiB4PSIwcHgiIHk9IjBweCINCgkgdmlld0JveD0iMCAwIDQ0MS4yMyA0NDEuMjMiIHN0eWxlPSJlbmFibGUtYmFja2dyb3VuZDpuZXcgMCAwIDQ0MS4yMyA0NDEuMjM7IiB4bWw6c3BhY2U9InByZXNlcnZlIj4NCjxwYXRoIGQ9Ik00NDAuNjUxLDEzMi43MzljLTAuODg4LTIuMzU0LTIuNzIxLTQuMjI5LTUuMDU0LTUuMTcxTDM5Ni4zOSwxMTEuNzVjLTIuNDM1LTEyLjY2Ni0xMi4wNTYtMjIuODEtMjQuNDM2LTI2LjAwOA0KCWwtMi4xMTUtMjQuMzYzYy0wLjMwOS0zLjU2NS0yLjcwMS02LjYwOC02LjA5My03Ljc1MWMtMy4zOTEtMS4xNDItNy4xMzctMC4xNjctOS41NDEsMi40ODRsLTEwLjA2MiwxMS4wOTlsLTYuMjItMjEuNzY2DQoJYy0xLjA3Mi0zLjc1Mi00LjQ0LTYuMzg2LTguMzQxLTYuNTIxYy0zLjkyNC0wLjEzOS03LjQ0NCwyLjI1OC04Ljc3Myw1LjkyOEwyNzQuMzQsMTczLjA0N2MwLDAtMTcyLjEyNyw4LjAzNS0xNzIuMTk5LDguMDM5DQoJYy0zNS4yOTYsMi4xMjEtNjguNzM1LTE2Ljc2NS04NS4xNjctNDguMTE5Yy0yLjMwOS00LjQwMi03Ljc0OC02LjEwMi0xMi4xNDktMy43OTRjLTQuNDAzLDIuMzA4LTYuMTAxLDcuNzQ3LTMuNzk0LDEyLjE0OQ0KCWMxNC42OSwyOC4wMyw0MC43MDgsNDcuNzUsNzAuNTQxLDU0LjkzYy0zLjA5NywzLjYwOS05Ljc1MSwxMi41NTQtMTMuNjQyLDI2LjYxN2MtNC4yMzEsMTUuMjkxLTUuNzU2LDM5LjY2Nyw5LjgwMSw3MC42MTkNCglMNDIuNDk5LDMyNy43NmMtMS40NzQsMi4wMDEtMi4wNTQsNC41MjMtMS42MDMsNi45NjhsMTEuMTA1LDYwLjIxOGMwLjc4Nyw0LjI2OCw0LjUxLDcuMzY3LDguODUxLDcuMzY3aDExLjMxMg0KCWMyLjY2OSwwLDUuMi0xLjE4NSw2LjkxMS0zLjIzM2MxLjcxLTIuMDUsMi40MjItNC43NTMsMS45NDQtNy4zNzhsLTcuMDMyLTM4LjYyN2w3NC40MDEtNTUuODUzYzAuMTMxLTAuMDk5LTAuMTI2LDAuMTA3LDAsMA0KCWM3LjExNC01Ljk3NSwxMi4yNzgtMTIuNTU2LDE1Ljk3Mi0xOS4zMjJjMzguNzc3LDYuODA4LDkxLjg0NCwxNi4wMiwxMjUuODU3LDIxLjQ5OGwxNC45ODYsOTUuMzE0DQoJYzAuNjg5LDQuMzc3LDQuNDYsNy42MDIsOC44OTEsNy42MDJoOS4zMDhjNC45NzEsMCw5LTQuMDI5LDktOVYyOTYuNTZjOC40NDktNS43NywxMS40NjktMTUuNDIsMTMuNDcyLTI0Ljg3MQ0KCWMwLjA2My0wLjI5NywyMC4wMjItOTIuNDE2LDIwLjAyMi05Mi40MTZjMy43NjIsMC42MjcsNy41NjEsMC45NTYsMTEuMzg4LDAuOTU2YzI2LjM1NiwwLDUwLjQ5Mi0xNS40MzEsNjIuOTg3LTQwLjI3MQ0KCUM0NDEuNDAxLDEzNy43MTIsNDQxLjUzOSwxMzUuMDk0LDQ0MC42NTEsMTMyLjczOXoiLz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjwvc3ZnPg0K";
  const catIcon =
    "data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiIHN0YW5kYWxvbmU9Im5vIj8+CjwhLS0gQ3JlYXRlZCB3aXRoIElua3NjYXBlIChodHRwOi8vd3d3Lmlua3NjYXBlLm9yZy8pIC0tPgo8c3ZnIHhtbG5zOnN2Zz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmVyc2lvbj0iMS4wIiB3aWR0aD0iNDAwIiBoZWlnaHQ9IjM4MCIgaWQ9InN2ZzIiPgogIDxkZWZzIGlkPSJkZWZzNSIvPgogIDxwYXRoIGQ9Ik0gMTUxLjM0OTA0LDMwNy4yMDQ1NSBMIDI2NC4zNDkwNCwzMDcuMjA0NTUgQyAyNjQuMzQ5MDQsMjkxLjE0MDk2IDI2My4yMDIxLDI4Ny45NTQ1NSAyMzYuNTk5MDQsMjg3Ljk1NDU1IEMgMjQwLjg0OTA0LDI3NS4yMDQ1NSAyNTguMTI0MjQsMjQ0LjM1ODA4IDI2Ny43MjQwNCwyNDQuMzU4MDggQyAyNzYuMjE3MDcsMjQ0LjM1ODA4IDI4Ni4zNDkwNCwyNDQuODI1OTIgMjg2LjM0OTA0LDI2NC4yMDQ1NSBDIDI4Ni4zNDkwNCwyODYuMjA0NTUgMzIzLjM3MTcxLDMyMS42NzU0NyAzMzIuMzQ5MDQsMzA3LjIwNDU1IEMgMzQ1LjcyNzY5LDI4NS42Mzg5NyAzMDkuMzQ5MDQsMjkyLjIxNTE0IDMwOS4zNDkwNCwyNDAuMjA0NTUgQyAzMDkuMzQ5MDQsMTY5LjA1MTM1IDM1MC44NzQxNywxNzkuMTgwNzEgMzUwLjg3NDE3LDEzOS4yMDQ1NSBDIDM1MC44NzQxNywxMTkuMjA0NTUgMzQ1LjM0OTA0LDExNi41MDM3NCAzNDUuMzQ5MDQsMTAyLjIwNDU1IEMgMzQ1LjM0OTA0LDgzLjMwNjk1IDM2MS45OTcxNyw4NC40MDM1NzcgMzU4Ljc1ODA1LDY4LjczNDg3OSBDIDM1Ni41MjA2MSw1Ny45MTE2NTYgMzU0Ljc2OTYyLDQ5LjIzMTk5IDM1My40NjUxNiwzNi4xNDM4ODkgQyAzNTIuNTM5NTksMjYuODU3MzA1IDM1Mi4yNDQ1MiwxNi45NTkzOTggMzQyLjU5ODU1LDE3LjM1NzM4MiBDIDMzMS4yNjUwNSwxNy44MjQ5OTIgMzI2Ljk2NTQ5LDM3Ljc3NDE5IDMwOS4zNDkwNCwzOS4yMDQ1NDkgQyAyOTEuNzY4NTEsNDAuNjMxOTkxIDI3Ni43NzgzNCwyNC4yMzgwMjggMjY5Ljk3NDA0LDI2LjU3OTU0OSBDIDI2My4yMjcwOSwyOC45MDEzMzQgMjY1LjM0OTA0LDQ3LjIwNDU0OSAyNjkuMzQ5MDQsNjAuMjA0NTQ5IEMgMjc1LjYzNTg4LDgwLjYzNjc3MSAyODkuMzQ5MDQsMTA3LjIwNDU1IDI2NC4zNDkwNCwxMTEuMjA0NTUgQyAyMzkuMzQ5MDQsMTE1LjIwNDU1IDE5Ni4zNDkwNCwxMTkuMjA0NTUgMTY1LjM0OTA0LDE2MC4yMDQ1NSBDIDEzNC4zNDkwNCwyMDEuMjA0NTUgMTM1LjQ5MzQyLDI0OS4zMjEyIDEyMy4zNDkwNCwyNjQuMjA0NTUgQyA4Mi41OTA2OTYsMzE0LjE1NTI5IDQwLjgyMzkxOSwyOTMuNjQ2MjUgNDAuODIzOTE5LDMzNS4yMDQ1NSBDIDQwLjgyMzkxOSwzNTMuODEwMTkgNzIuMzQ5MDQ1LDM2Ny4yMDQ1NSA3Ny4zNDkwNDUsMzYxLjIwNDU1IEMgODIuMzQ5MDQ1LDM1NS4yMDQ1NSAzNC44NjM3NjQsMzM3LjMyNTg3IDg3Ljk5NTQ5MiwzMTYuMjA0NTUgQyAxMzMuMzg3MTEsMjk4LjE2MDE0IDEzNy40MzkxNCwyOTQuNDc2NjMgMTUxLjM0OTA0LDMwNy4yMDQ1NSB6ICIgc3R5bGU9ImZpbGw6YmxhY2s7ZmlsbC1vcGFjaXR5OjE7ZmlsbC1ydWxlOmV2ZW5vZGQ7c3Ryb2tlOm5vbmU7c3Ryb2tlLXdpZHRoOjFweDtzdHJva2UtbGluZWNhcDpidXR0O3N0cm9rZS1saW5lam9pbjptaXRlcjtzdHJva2Utb3BhY2l0eToxIiBpZD0icGF0aDE4OTEiLz4KPC9zdmc+";
  const pawPrintIcon =
    "data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij48Y2lyY2xlIGN4PSI0LjUiIGN5PSI5LjUiIHI9IjIuNSIvPjxjaXJjbGUgY3g9IjkiIGN5PSI1LjUiIHI9IjIuNSIvPjxjaXJjbGUgY3g9IjE1IiBjeT0iNS41IiByPSIyLjUiLz48Y2lyY2xlIGN4PSIxOS41IiBjeT0iOS41IiByPSIyLjUiLz48cGF0aCBkPSJNMTcuMzQgMTQuODZjLS44Ny0xLjAyLTEuNi0xLjg5LTIuNDgtMi45MS0uNDYtLjU0LTEuMDUtMS4wOC0xLjc1LTEuMzItLjExLS4wNC0uMjItLjA3LS4zMy0uMDktLjI1LS4wNC0uNTItLjA0LS43OC0uMDRzLS41MyAwLS43OS4wNWMtLjExLjAyLS4yMi4wNS0uMzMuMDktLjcuMjQtMS4yOC43OC0xLjc1IDEuMzItLjg3IDEuMDItMS42IDEuODktMi40OCAyLjkxLTEuMzEgMS4zMS0yLjkyIDIuNzYtMi42MiA0Ljc5LjI5IDEuMDIgMS4wMiAyLjAzIDIuMzMgMi4zMi43My4xNSAzLjA2LS40NCA1LjU0LS40NGguMThjMi40OCAwIDQuODEuNTggNS41NC40NCAxLjMxLS4yOSAyLjA0LTEuMzEgMi4zMy0yLjMyLjMxLTIuMDQtMS4zLTMuNDktMi42MS00Ljh6Ii8+PC9zdmc+";

  const dogsTabID = "omyavzt";
  const catsTabID = "o9ws5hl";
  const othersTabID = "od6";
  let dogs;
  let cats;
  let others;

  // get the three tabs of data from the google sheet
  getData(dogsTabID).then(data => (dogs = data));
  getData(catsTabID).then(data => (cats = data));
  getData(othersTabID).then(data => (others = data));

  async function getData(whatTab) {
    const mySheetID = "1bPW98SzQ5SRsincyVGdP3ctM8ey3oSpncnyo9ASFUDM/";
    const URLStart = "https://spreadsheets.google.com/feeds/list/";
    const URLEnd = "/public/full?alt=json";
    const fetchURL = URLStart + mySheetID + whatTab + URLEnd;

    return fetch(fetchURL, {
      method: "GET",
      headers: {
        Accept: "application/json",
        "Content-Type": "application/json"
      }
    })
      .then(response => response.json())
      .then(responseData => {
        return responseData.feed.entry;
      })
      .catch(error => console.warn(error));
  }
</script>

<style>
  .animalIcon {
    vertical-align: bottom;
    padding-right: 10px;
    height: 50px;
  }
  .menuItem {
    margin-left: 30px;
    font-size: 1.8em;
    margin-top: 30px;
  }
  a {
    text-decoration: none;
    background-color: transparent;
    color: rgba(0, 0, 0, 0.9);
  }
  a:hover {
    text-decoration: none;
  }
  a:visited {
    color: rgba(0, 0, 0, 0.9);
  }
</style>

<Header />

<div class="menuItem">
  <a href="/" class="typelink">
    <img class="animalIcon" src={dogIcon} alt="dog icon" />
    {#if !dogs}Fetching Dogs...{:else}{dogs.length} Dogs{/if}
  </a>
</div>
<div class="menuItem">
  <a href="/" class="typelink">
    <img class="animalIcon" src={catIcon} alt="cat icon" />
    {#if !cats}Fetching Cats...{:else}{cats.length} Cats{/if}
  </a>
</div>
<div class="menuItem">
  <a href="/" class="typelink">
    <img class="animalIcon" src={pawPrintIcon} alt="paw print icon" />
    {#if !others}Fetching Others...{:else}{others.length} Others{/if}
  </a>
</div>

<h3>ToDo List</h3>
<ol>
    <li>Move menu to it's own svelte file?? - pass 3 arrays</li>
    <li>Include a nice font?</li>
    <li>Fix all ofline service worker errors</li>
    <li>Remove service worker console.log statements</li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ol>
