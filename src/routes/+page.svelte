<script lang='ts'>
    import Searchbar from "./../header/Searchbar/Searchbar.svelte";
    import Navbar from "./../header/Navbar/Navbar.svelte";

    let content = [
        {
            "title": "Home",
            "path": "/Home"
        }
    ]
</script>
<div class='container'>
    <div class='nb'>
        <Navbar width='35vw' content={content} />
    </div>

    <div class='sb'>
        <Searchbar width='20vw' />
    </div>

</div>

<style lang='scss'>
    .container {
        display: flex;
        align-items: center;
        height: 3em;
        
    }

</style>
