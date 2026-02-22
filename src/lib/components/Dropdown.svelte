<script>
let {title,question,answer} = $props();
</script>

<details>
<summary> {title}</summary>
<span class="question"> {question} </span>
<p> <span class="answer"> {answer} </span> </p>
</details>

<style>

.question {
font-style: italic;
font-family: var(--font-serif);
font-size: 1rem;
font-color:#1a1a1a;
}

.answer{
font-family: var(--font-serif);
font-size: .8rem;
font-color:#1a1a1a;
}
details {
  border: 1px solid #aaaaaa;
  border-radius: 4px;
  padding: 0.5em 0.5em 0;
}

summary {
  font-weight: bold;
  margin: -0.5em -0.5em 0;
  padding: 0.5em;
}

details[open] {
  padding: 0.5em;
}

details[open] summary {
  border-bottom: 1px solid #aaaaaa;
  margin-bottom: 0.5em;
}

</style>