<template>
    <PanelItem :index="index" :field="field">
        <template #value>
            <div class="image-gallery-field">
                <ul
                    v-if="field.value && field.value.length"
                    class="flex flex-wrap image-list -mt-4"
                >
                    <FieldImage
                        v-for="image in field.value"
                        :image="image"
                        :key="image.id"
                        readonly
                    />
                </ul>
                <p v-else>-</p>
            </div>
        </template>
    </PanelItem>
</template>

<script>
import FieldImage from "./FieldImage.vue";

export default {
    props: ["index", "resource", "resourceName", "resourceId", "field"],
    components: {
        FieldImage,
    },
};
</script>
