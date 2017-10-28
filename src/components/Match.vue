<template>
    <div class="row main">
        <br>
        <form class="col s6 offset-s3">
            <div class="row">
                <Type/><br>
                <Duration/><br>
                <Players/><br>
                <Lifes/>
            </div>
        </form>
    </div>
</template>

<script>
import Type from './MatchType'
import Duration from './MatchDuration'
import Players from './MatchPlayers'
import Lifes from './MatchLifes'

export default {
    name: 'Match',
    components: {
        Type,
        Duration,
        Players,
        Lifes
    }
}
</script>

<style>

</style>
