<script>
    import { css } from '@emotion/css';

    export let src;
    export let onClick;
    export let areaLabel;

    const style = {
        container: css`
            width: 24px;
            height: 24px;
            background: ${`url("${src}")`} no-repeat center/cover;
        `,
    };
</script>

<button on:click={onClick} aria-label={areaLabel} class={style.container} type="button"></button>
