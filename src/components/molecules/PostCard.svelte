<script lang="ts">
    import { css } from "@emotion/css";
    import heart from "../../assets/icons/heart.svg";
    export let data;

    // 날짜 포맷 함수 추가
    const formatDateKorean = (dateString: string): string => {
        const date = new Date(dateString);
        const year = date.getFullYear();
        const month = date.getMonth() + 1;
        const day = date.getDate();
        return `${year}년 ${month}월 ${day}일`;
    };

    const style = {
        container: css`
            display: flex;
            flex-direction: column;
            height: 100%;
            background-color: #fff;
            box-shadow: 0 4px 16px 0 rgba(0, 0, 0, 0.04);
            transition: box-shadow 0.25s ease-in, transform 0.25s ease-in;
            &:hover {
                box-shadow: 0 12px 20px 0 rgba(0, 0, 0, 0.08);
                transform: translateY(-8px);
            }
            > a {
                height: 100%;
                display: flex;
                flex-direction: column;
            }
        `,
        imgBox: css`
            padding-top: 52%;
            position: relative;
            > img {
                position: absolute;
                width: 100%;
                height: 100%;
                top: 0;
                left: 0;
            }
        `,
        textBox: css`
            flex: 1;
            padding: 16px;
        `,
        title: css`
            overflow: hidden;
            text-overflow: ellipsis;
            color: #212529;
            font-weight: 700;
            line-height: 1.3rem;
            margin-bottom: 4px;
        `,
        description: css`
            height: 4rem;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
            overflow: hidden;
            text-overflow: ellipsis;
            font-size: 14px;
            color: #495057;
            line-height: 1.3rem;
            margin-bottom: 24px;
        `,
        subInfo: css`
            font-size: 12px;
            color: #868e96;
            display: flex;
            > span + span {
                &::before {
                    content: "·";
                    margin: 0 4px;
                }
            }
        `,
        bottomBox: css`
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-top: 1px solid #f1f3f5;
            padding: 10px 16px;
            font-size: 12px;
            color: #868e96;

            > b {
                color: #212529;
                font-weight: 700;
            }

            > a {
                display: flex;
                align-items: center;
                &::before {
                    content: "";
                    display: inline-block;
                    width: 24px;
                    height: 24px;
                    border-radius: 50px;
                    vertical-align: middle;
                    margin-right: 8px;
                    background: url("${data.user.profile.thumbnail}") no-repeat center/cover;
                }
            }
        `,
        likeBox: css`
            display: flex;
            align-items: center;
            gap: 12px;
            color: #212529;

            &::before {
                content: "";
                display: inline-block;
                width: 12px;
                height: 12px;
                background: url("${heart}") no-repeat center/cover;
                vertical-align: middle;
            }
        `,
    };
</script>

<li class={style.container}>
  <a href={`/${data.url_slug}`}>
    <div class={style.imgBox}>
      <img src={data.thumbnail} alt={data.title} />
    </div>
    <div class={style.textBox}>
      <p class={style.title}>{data.title}</p>
      <p class={style.description}>{data.short_description}</p>
      <div class={style.subInfo}>
        <span>{formatDateKorean(data.released_at)}</span> <!-- 날짜 포맷 적용 -->
        <span>{data.comments_count}개의 댓글</span>
      </div>
    </div>
  </a>
  <div class={style.bottomBox}>
    <a href={`/user/${data.user.username}`}>
      <span>by <b>{data.user.profile.display_name}</b></span>
    </a>
    <span class={style.likeBox}>{data.likes}</span>
  </div>
</li>
