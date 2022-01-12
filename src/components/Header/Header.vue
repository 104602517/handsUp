<template>
  <div class="header-wrapper">
    <div class="left-icon">
        <svg width="34" height="25">
            <image xlink:href="../../assets/ham.svg"/>
        </svg>
    </div>
    <div class="title">{{title}}</div>
    <div class="right-icon">
        <svg width="32" height="24">
            <image xlink:href="../../assets/exit.svg"/>
        </svg>
    </div>
  </div>
</template>

<script>
export default {
  props: ['title'],
}
</script>

<style lang="scss" scoped>
.header-wrapper {
    background: #8DC8FF;
    width: 100%;
    height: 55px;
    padding: 0px 12px;
    box-sizing: border-box;
    display: flex;
    align-items: center;

    .left-icon {
        margin-right: 25px;
        display: flex;
        align-items: center;
    }

    .title {
        font-family: Roboto;
        font-size: 36px;
        font-weight: 400;
        color: #fff;
        flex: 1 0 auto;
    }
}
</style>