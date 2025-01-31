<script lang="ts">
    import { css } from "@emotion/css";
    import Button from "../atoms/Button.svelte";
    import trendIcon from "../../assets/icons/graph.svg";
    import recentIcon from "../../assets/icons/recent.svg";
    import feedIcon from "../../assets/icons/feed.svg";

    let selectedNumber = 1;

    const setSelectedNumber = (index: number) => {
        selectedNumber = index;
    };

    const style = {
        container: css`
            display: flex;
            width: fit-content;
            position: relative;
            > a {
                color: #868e96;
                &::before {
                    background: #868e96;
                }
                &:not(:first-of-type) {
                    margin-left: 20px;
                }
                &:nth-of-type(${selectedNumber}) {
                    color: #212529;
                    font-weight: 700;
                    &::before {
                        background: #212529;
                    }
                }
            }
        `,
    };
</script>

<nav class={style.container}>
    <Button 
        buttonType="iconText" 
        src={trendIcon} 
        text="트렌딩" 
        href="/trending/week" 
        on:click={() => setSelectedNumber(1)} 
    />
    <Button 
        buttonType="iconText" 
        src={recentIcon} 
        text="최신" 
        href="/recent" 
        on:click={() => setSelectedNumber(2)} 
    />
    <Button 
        buttonType="iconText" 
        src={feedIcon} 
        text="피드" 
        href="/feed" 
        on:click={() => setSelectedNumber(3)} 
    />
</nav>
