<script lang="ts">
    import {css} from '@emotion/css';
    import logo from '../../assets/icons/logo.svg'
    import alertIcon from '../../assets/icons/notice.svg';
    import searchIcon from '../../assets/icons/search.svg';

    import Button from '../atoms/Button.svelte';
  import UserDropdown from '../molecules/UserDropdown.svelte';

    const style = {
        container: css`
            margin: 0 atuo;
            height: 64px;
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;

        `,
        logo: css`
            > img {
                height: 24px;
            }
        `,
        menuBox: css`
            display: flex;
            align-items: center;
            > :nth-of-type(1){
                margin-right: 4px;
            }
            > :nth-of-type(2){
                margin-right: 8px;
            }
            > :nth-of-type(3){
                margin-right: 20px;
            }
        `
    }
</script>


<header class={style.container}>
    <h1 class={style.logo}>
        <img src={logo} alt="velog" />
    </h1>
    <div class={style.menuBox}>
        <Button href="/notifications" src={alertIcon} buttonType="icon" />
        <Button href="/search" src={searchIcon} buttonType="icon" />
        <Button href="/" text="새 글 작성" buttonType="text" />
        <UserDropdown />
    </div>
</header>