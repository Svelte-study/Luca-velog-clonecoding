<script lang="ts">
    import { css } from "@emotion/css";
    import Header from "../components/organisms/Header.svelte";
  
    const style = {
      container: css`
        max-width: 1720px;
        margin: 0 auto;
      `,
    }
  </script>
  
  <div class={style.container}>
      <Header/>
      <main>
        <slot/>
      </main>
  </div>