<template>
    <ul class="todos">

        <li class="card" draggable="true">
            <div class="cb-container">
                <input type="checkbox" class="cb-input" />
                <span class="check"></span>
            </div>
            <p class="item">یادگیری جاوااسکریپت</p>
            <button class="clear">
                <img src="../assets/images/icon-cross.svg" alt="Clear it" />
            </button>
        </li>



        <li class="card">
            <div class="cb-container">
                <input type="checkbox" class="cb-input" />
                <span class="check"></span>
            </div>
            <p class="item">یادگیری Nodejs</p>
            <button class="clear">
                <img src="../assets/images/icon-cross.svg" alt="Clear it" />
            </button>
        </li>

    </ul>
</template>

<script>
export default {

}
</script>

<style></style>