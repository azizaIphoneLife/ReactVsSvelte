<script context="module">
  export const load = async ({ params, fetch }) => {
    console.log(params);
    const id = params.id;
    const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);

    const author = await res.json();

    return {
      props: {
        author,
      },
    };
  };
</script>

<script>
  export let author;
</script>

<h1>Author Info</h1>

<h1>{author.name}</h1>

<p>Website: {author.website}</p>
<p>Company Catch phrase: {author.company.catchPhrase}</p>

<style>
  h1 {
    margin-bottom: 30px;
  }
  p {
    margin-left: 80px;
  }
</style>
