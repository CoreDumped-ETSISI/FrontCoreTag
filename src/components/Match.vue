<template>
    <div class="row">
        <form class="col s12">
            <div class="row">
                <Duration/>
                <Players/>
            </div>
        </form>
    </div>
</template>

<script>
import Duration from './MatchDuration'
import Players from './MatchPlayers'

export default {
    name: 'Match',
    components: {
        Duration,
        Players
    }
}
</script>
