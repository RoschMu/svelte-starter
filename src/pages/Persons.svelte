<script>
  import axios from "axios";
  import { onMount } from "svelte";

  let persons = [];

  onMount(() => {
    getPerson();
  });

  function getPerson() {
    axios.get("http://localhost:8080/infections/persons").then((response) => {
      persons = response.data;
    });
  }
</script>

<h1>This is the list of all persons</h1>
<h1>Tsdfsdfsdf</h1>
<h1>sdfsdfsdf</h1>

<!-- svelte-ignore component-name-lowercase -->
<table class="table">
  <thead>
    <tr>
      <th>ID</th>
      <th>Name</th>
      <th>Birthdate</th>
    </tr>
  </thead>
  <tbody>
    {#each persons as person}
      <tr>
        <td>{person.id}</td>
        <td>{person.name}</td>
        <td>{person.birthdate}</td>
      </tr>
    {/each}
  </tbody>
</table>
