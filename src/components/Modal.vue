<template>
    <div class="modal">
        <div class="inner">
            <slot />
            <button class="close" @click="toggleModal()">close</button>
        </div>
    </div>
</template>

<script>
export default {
    props: ['toggleModal']
}
</script>

<style lang="scss" scoped>
    .modal {
        position: fixed;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: rgba(0, 0, 0, 0.5);
        display: flex;
        justify-content: center;
        align-items: center;
        .inner {
            background-color: white;
            padding: 32px;
            position: relative;
            width: 50%;
            top: 0;
            text-align: center;
            // border: 3px solid black;
            box-shadow: 0.8rem 0.8rem rgba(59, 59, 59, 0.527), -0.8rem -0.8rem rgba(165, 165, 165, 0.589);
            animation: modalbox .7s cubic-bezier(0,0,.3,1.6);
            @keyframes modalbox {
                0% {
                    top: -350px; 
                    opacity: 0;
                    width: 20px;
                }
                100% {
                    top: 0; 
                    opacity: 1;
                }
            }
            button {
                min-width: 150px;
                min-height: 50px;
                background: white;
                padding: 0.3rem 3.4rem;
                border: 3px solid rgb(204, 14, 14);
                margin-right: 2.6rem;
                box-shadow: 0 0 0 white;
                font-size: 1.2rem;
                letter-spacing: -1.2px;
                font-family: Helvetica, Arial, sans-serif; 
                font-weight: bolder; 
                font-style : italic;
                transition: all 0.2s;
                cursor: pointer;
                &:hover {
                    box-shadow: 0.4rem 0.4rem 0 rgb(204, 14, 14);
                    transform: translate(-0.6rem, -0.6rem);
                }
                &:active {
                    box-shadow: 0 0 0 rgb(204, 14, 14);
                    transform: translate(0, 0);
                }
            }
        }
    }
</style>