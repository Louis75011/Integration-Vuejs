<template>
    <div>
        <h2>
            <slot />
        </h2>
        <img src="/assets/triangles.png" alt="triangles, yellow">
    </div>
</template>

<script>
    export default {
        name: "Title"
    }
</script>

<style scoped lang="scss">
    h2 {
        display: flex;
        align-items: center;
        text-transform: uppercase;

        &:before,
        &:after {
            content: "";
            display: block;
            flex: 1;
            border-top: 2px solid black;
        }

        &:before {
            margin-right: 30px;
        }

        &:after {
            margin-left: 30px;
        }
    }

    img {
        display: block;
        margin: 0 auto 2rem;
        width: 7rem;
    }
</style>