<script lang="ts">
    import { css } from '@emotion/css';
    import {link} from 'svelte-routing';

    export let text: string = "";
    export let src: string = '';
    export let href:string;

    type ButtonType = 'icon' | 'text' | 'iconText';
    export let buttonType: ButtonType = 'icon';

    const buttonStyles = {
        icon: css`
            display: inline-block;
            width: 40px;
            height: 40px;
            background: ${`url("${src}")`} no-repeat center/24px;
            border-radius: 50px;

            :hover {
                background-color: #EBECED;
            }
        `,
        text: css`
            display: inline-flex;
            align-items: center;
            height: 32px;
            padding: 1px 16px;
            border: 1px solid #212529;
            border-radius: 16px;
            font-size: 14px;
            font-weight: 700;
            transition: all .125s ease-in;

            &:hover {
                background: #212529;
                color: #f8f9fa;
            }
        `,
        iconText: css`
            display: inline-flex;
            height: 24px;

            &::before {
                content: '';
                display: inline-block;
                width: 24px;
                height: 24px;
                mask: ${`url("${src}")`} no-repeat center/cover;
                margin-right: 8px;
            }
        `,
    };

</script>

<a class={buttonStyles[buttonType]} aria-label={text} href={href} use:link>
    {text}
</a>
