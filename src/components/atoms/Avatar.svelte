<script lang="ts">
    import { css } from '@emotion/css';

    export let src: string = "";
    export let alt: string = "";
    export let width: string = "40px"; 
    export let height: string = "40px"; 

    const style = {
        avatar: css`
            color: transparent;
            border-radius: 50px;
            object-fit: cover;
            transition: all .125s ease-in;
        `,
    };

    $: dynamicStyle = css`
        width: ${width};
        height: ${height};
    `;
</script>

<img
    class={`${style.avatar} ${dynamicStyle}`}
    src={src}
    alt={alt}
    width={width}
    height={height}
/>
