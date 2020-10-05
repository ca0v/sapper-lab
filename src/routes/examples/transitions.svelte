<script>
  import { fade, scale, fly } from "svelte/transition";

  const codeSamples = [
    {
      about: "computes the sum of a series of numbers",
      fn: (values) => values.reduce((value, prior) => value + prior, 0),
      inputs: [[1, 2, 3], []],
    },
    {
      about: "finds maximum of a series of numbers",
      fn: (values) =>
        values.reduce(
          (value, prior) => Math.max(value, prior),
          Number.MIN_VALUE
        ),
      inputs: [[1, 2, 3], []],
    },
  ].map((v) => ({ ...v, visible: false }));

  function asCode(code) {
    return code;
  }
</script>

<style>
  samples {
    display: inline-block;
    overflow: hidden;
  }

  code {
    cursor: pointer;
  }
</style>

<samples>
  {#each codeSamples as sample}
    <p>{sample.about}</p><code
      on:click={() => (sample.visible = !sample.visible)}>
      {asCode(sample.fn.toString())}
    </code>
    {#if sample.visible}
      {#each sample.inputs as input}
        <p transition:fly={{ x: -100 }}>
          when run with input
          {JSON.stringify(input)}
          it returns
          {JSON.stringify(sample.fn(input))}
        </p>
      {/each}
    {/if}
  {/each}
</samples>

<p>Click a function to see results..they appear using a fly animation</p>
