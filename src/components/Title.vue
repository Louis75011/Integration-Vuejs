<template>
    <div>
        <h2>
                <slot></slot>
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
        text-align: center;
        text-transform: uppercase;
        font-weight: 500;

        slot {
            display: block;
            max-width: 60%;
        }

        &:before,
        &:after {
            content: "";
            display: block;
            flex: 1;
            border-top: 1px solid black;
        }

        &:before {
            margin-right: 30px;

            @media (max-width: 640px) {
                margin-right: 15px;
            }
        }

        &:after {
            margin-left: 30px;

            @media (max-width: 640px) {
                margin-left: 15px;
            }
        }
    }

    img {
        display: block;
        margin: 0 auto 2rem;
        width: 7rem;
    }
</style>