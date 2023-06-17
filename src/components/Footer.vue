<template>
    <div class="footwrap">
        <a href="http://davyjones.me/">davyjones.me</a>
        <p>© 2023. All Rights Reserved.</p>
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
        color: $blue-light-3;
    } & a {
        padding-top: 3px;
        text-decoration: underline;
        font-weight: 500;
        color: $blue-light;
    } & a:hover {
            color: $blue-light-2;
        }
}
@import '@/styles/media.scss';

</style>
