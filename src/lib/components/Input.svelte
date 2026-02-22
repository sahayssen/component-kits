
<script>
  let {name, num1, num2, num3 } = $props();
</script>

<label for="name"> {name}:</label>

<input
  type="text"
  name="name"
  required
  minlength={num1}
  maxlength={num2}
  size={num3}
  />

<style>

input{
  
  height: 10rem;
}

label {
  display: block;
  font:
     "Fira Sans",
    sans-serif;
  font-size: 30px;
  color: #0033A1;
}

input,
label {
  margin: 0.4rem ;
}

</style>