<script>
  import db from '../db/db.json';

  let imageURL;

  function refreshImage() {
    imageURL = db[Math.floor(Math.random() * db.length)];
    console.log(imageURL);
  }
</script>

<h1>Random Image</h1>
<button on:click={refreshImage}>Get Image</button>
{#if imageURL}
  <img src={imageURL} />
{/if}

<style>
  :global(body) {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    background-color: black;
    color: white;
  }

  h1 {
    text-align: center;
    font-size: 3rem;
  }

  button {
    display: block;
    user-select: none;
    cursor: pointer;
    margin: 5rem auto;
    width: fit-content;
    font-size: 1.5rem;
    padding: 1.25rem 3rem;
    border-radius: 99rem;
    border: 0;
    background-color: #1d4ed8;
    color: inherit;
    text-transform: uppercase;
    transition: background-color 80ms;
  }

  button:hover {
    background-color: #2563eb;
  }
</style>
