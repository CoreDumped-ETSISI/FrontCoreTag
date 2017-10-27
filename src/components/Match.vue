<template>
    <div class="row">
        <form class="col s12">
            <div class="row">
                <Duration/>
            </div>
        </form>
    </div>
</template>

<script>
import Duration from './MatchDuration'

export default {
    name: 'Match',
    components: {
        Duration
    }
}
</script>
