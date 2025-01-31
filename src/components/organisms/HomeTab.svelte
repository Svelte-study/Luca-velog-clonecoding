<script lang="ts">
    import { css } from "@emotion/css";
  import Tab from "../molecules/Tab.svelte";
  import option from "../../assets/icons/option.svg";
  import IconButton from "../atoms/IconButton.svelte";

  const style = {
    container: css`
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 12px 0;
    `
  }
</script>

<div style={style.container}>
    <Tab />
    <div>
        dropdown
        <IconButton src={option} areaLabel="option" onClick={()=>{}} />
    </div>
</div>