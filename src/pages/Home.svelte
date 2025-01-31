<script lang="ts">
    import { css } from "@emotion/css";
    import { BlogList } from "../mock/blogList";
    import PostCardItem from "../components/molecules/PostCard.svelte";
  import HomeTab from "../components/organisms/HomeTab.svelte";

    const style = {
        container: css`
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 32px;
            margin: 32px 0;
        `
    }
</script>


<HomeTab />
<div class={style.container}>
    {#each BlogList as item}
        <PostCardItem data={item}/>
    {/each}
</div>