<template>
    <a :target="field.blank ? field.blank : '_self'" :class="field.classes ? field.classes : defaultClasses"
       v-if="field.value"
       :href="field.href" v-text="text">
    </a>
    <span v-else v-text="emptyPlaceholder" :class="defaultClasses"></span>
</template>

<script>
    export default {
        props: ['resourceName', 'field'],

        data: () => ({
            defaultClasses: [
                'no-underline',
                'dim',
                'text-primary',
                'font-bold'
            ]
        }),

        computed: {
            text() {
                return this.field.text ? this.field.text : this.field.value
            },
            emptyPlaceholder() {
                return this.field.emptyText ? this.field.emptyText : '-'
            },
        }
    }
</script>
