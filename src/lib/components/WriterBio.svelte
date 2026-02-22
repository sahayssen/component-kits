
<script>
import { base } from '$app/paths';
let {link, author, bio} = $props();
  // Prepend base path to local images (those starting with /)
  // but not to external URLs (http://, https://, //, data:)
  const resolvedSrc = $derived(
    link.startsWith('/') && !link.startsWith('//') 
      ? `${base}${link}` 
      : link
  );
</script>

<section>  
    <img 
    src={resolvedSrc}  
    class="image"
    loading="lazy"
width="100px"  height="100px" style="float:left">
  <h2>{author}</h2>
  <p>{bio}</p>
</section>

<style>
section {
display:"block"
margin-top:2rem;
display:"block";
padding: 1rem;
background-color: #f5f5f5;
}

h2{
display:"block";
padding-left:3.5em;
margin-top:.5rem;
margin-bottom:.1rem;
font-family: var(--font-serif);
font-size: 2rem;
font-color:#1a1a1a;
}

p{
padding-left: 7em;
display:"block";
margin-top:.5rem;
font-family: var(--font-serif);
font-size: 1rem;
font-color:#1a1a1a;
}

img{
margin-top:.5rem; 
}

</style> 