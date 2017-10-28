<template>
    <div class="row">
        <form class="col s12">
            <div class="row">
                <Type/>
                <Duration/>
                <Players/>
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
