<template>
    <div class="row">
        <div class="col s8 left-align lifes">
            <h1>Lives:<b class="extra-lifes"> x{{ lifes }}</b>
            <img src="../images/heart.png" style="max-width: 2em"/>
            </h1>
        </div>
        <div class="col s8 left-align lifes">
            <h1>Deaths:<b class="extra-lifes"> x{{ deaths }}</b>
            <img src="../images/Skull.png" style="max-width: 2em"/>
            </h1>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Lifes',
    data: function() {
        return {
            page: 'IntroCenter',
            lifes: 3,
            deaths: 10
        }
    }
}
</script>

<style>
.lifes{
    font-size: xx-large;
    font-size: 250%;
}
.extra-lifes{
    font-size: 100%;
}

</style>
