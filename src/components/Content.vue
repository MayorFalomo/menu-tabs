<template>
    <div class="contentContainer" >
        <h1>{{content.position }} </h1>
        <span> {{content.name }} </span>
        <p> {{content.date }} </p>
    </div>

    <div>
        <p><span><Icon icon="uit:angle-double-right" width="50" height="50" /> </span> {{content.firstComment}} </p>
        <p><span><Icon icon="uit:angle-double-right" width="50" height="50" /> </span> {{content.secondComment}} </p>
        <p><span><Icon icon="uit:angle-double-right" width="50" height="50" /> </span> {{content.ThirdComment}} </p>
    </div>
</template>

<script>

import { Icon } from '@iconify/vue';
export default {
    name: "Content",
    props: {
        content: Object,
        Icon,
    }
}
</script>

<style>

</style>