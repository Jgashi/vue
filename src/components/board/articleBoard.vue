<template>
  <section class="board-wrapper">
    <div class="board-header">
      <div class="header-title">鐵人檔案</div>
      <div class="header-deco"></div>
    </div>
    <ul class="board-body">
      <li v-for="(year,index) in json" :key="index">
        <article class="article-wrapper">
          <div class="article-year">{{ year.irontitle }}</div>
          <div class="article-body" v-for="(articles,index) in year.articles" :key="index">
            <a class="article-type">{{ articles.type }}</a>
            <a class="article-title" :href="articles.href">{{ articles.title }} 系列</a>
            <p
              class="article-info"
            >{{ articles.info.success ? '鐵人練成' : '鐵人未練成' }} ｜ 共 {{ articles.info.count }} 篇文章 ｜ {{ articles.info.subscribe }} 人訂閱</p>
          </div>
        </article>
      </li>
    </ul>
    <div class="board-footer"></div>
  </section>
</template>
<script>
export default {
  name: "articleBoard",
  props: { json: null}
};
</script>
<style scoped lang="scss">
@import "@/assets/scss/style.scss";
.board-wrapper {
  margin: 20px auto;
  max-width: 1140px;
  border: 1px solid #e5e5e5;
  background: #fff;
  .board-header {
    padding: 14px 30px;
    z-index: 1;
    .header-title {
      font-size: 24px;
      padding-left: 24px;
    }
    .header-deco {
      background: #ffe8cc;
      width: 100%;
      height: 30px;
      margin-top: -19px;
    }
  }
  .board-body {
    padding: 0 30px 14px;
    .article-wrapper {
      .article-year {
        position: relative;
        padding: 8px 24px;
        border-bottom: 1px solid #dddddd;
        color: #495057;
        font-size: 18px;
        &::before {
          position: absolute;
          top: 18px;
          left: 10px;
          content: "";
          width: 8px;
          height: 8px;
          background: #495057;
          border-radius: 50px;
        }
      }
      .article-body {
        padding: 12px 4px;
        border-bottom: 1px solid #dddddd;
        .article-type {
          margin-bottom: 6px;
          padding: 2px 8px;
          border-radius: 20px;
          background: #4a89dc;
          font-weight: lighter;
          font-size: 14px;
          color: #fff;
          cursor: pointer;
        }
        .article-title {
          display: block;
          margin: 6px 0;
          color: #303233;
          font-size: 18px;
          font-weight: bold;
          transition: 0.3s;
          cursor: pointer;
          &:hover {
            color: #007db6;
          }
        }
        .article-info {
          color: #e8590c;
          font-size: 14px;
          font-weight: lighter;
        }
      }
    }
  }
}
</style>
