<template>
    <div class="row">
        <form class="col s12">
            <div class="row">
	    	<Type/>
                <Duration/>
                <Players/>
            </div>
        </form>
    </div>
</template>

<script>
import Type from './MatchType'
import Duration from './MatchDuration'
import Players from './MatchPlayers'

export default {
    name: 'Match',
    components: {
	Type,
        Duration,
        Players
    }
}
</script>
