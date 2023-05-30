<template>
    <div class="footwrap">
        <p>Davy Jones Design</p>
        <p>© 2023, dmjones.me</p>
    </div>
</template>

<style lang="scss" scoped>
@import '@/styles/main.scss';
.footwrap {
    margin: 0 0 0 40px;
    display: flex;
    flex-direction: row;
    align-content: center;
    justify-content: space-between;
    width: calc(100% - 80px);
    height: 30px;
    padding: 7px 20px 5px;
    border-top: 1px solid $blue-dark;
    background: $blue-dark-3;
    & p {
        margin: 0;
        text-align: center;
        height: 10px;
        color: $blue-light-2;
    }
}
@import '@/styles/media.scss';

</style>
