<template>
    <div class="alert alert-primary">
        <h2>{{ title }}</h2>
        <p>{{ message }}</p>
        <hr>
        <div class="alert alert-light">
            <h3>Inner Slot</h3>
            <slot />
        </div>
    </div>
</template>

<script>
export default {
    name: 'Slot',
    data: function() {
        return {
            title: 'Slot',
            message: 'This is message.',
        }
    }
}
</script>