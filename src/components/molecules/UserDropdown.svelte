<script lang="ts">
    import {css} from "@emotion/css";
  import Avatar from "../atoms/Avatar.svelte";
  import ppadro from "../../assets/images/빼드로.jpg";
  import downIcon from "../../assets/icons/select_down.svg";

  const style = {
    container: css`
    display: flex;
    align-items: center;
        &::after{
            content: '';
            display: inline-block;
            width: 24px;
            height: 24px;
            background: ${`url("${downIcon}")`} no-repeat center/24px;
                margin-left: 4px;
                vertical-align: middle;
        }
    `
  }
</script>

<button class={style.container}>
    <Avatar src={ppadro} width="40px" height="40px" alt="빼드로" />
</button>