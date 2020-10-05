<script>
  import { likes } from "../data/stores";
  const topics = [
    {
      topic: "stores",
      link: "examples/like",
      description: "increment a like counter",
    },
    {
      topic: "transitions",
      link: "examples/transitions",
      description: "show me some source code",
    },
  ].sort((a, b) => a.topic.localeCompare(b.topic));

  let filter = "";
  const isMatch = (a, b) => {
    if (!a || !b) return true;
    return -1 < a.toUpperCase().indexOf(b.toUpperCase());
  };
</script>

<svelte:head>
  <title>Learning Sapper and Svelte</title>
</svelte:head>

<label>Keywords:<input type="text" bind:value={filter} /></label>
{#each topics.filter((v) => isMatch(v.topic, filter) || isMatch(v.description, filter)) as topic}
  <figure>
    <figcaption>{topic.topic}</figcaption>
    <a href={topic.link}>{topic.description}</a>
  </figure>
{/each}

<p>This site has {$likes} likes</p>
