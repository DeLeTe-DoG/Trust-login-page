<template>
    <div className="header_block">
        <div className="group_logo">
            <img className="group_logo_img" src="/src/assets/images/Group.svg">
        </div>
        <div className="contacts_blocks">
            <div v-for="el in contacts_data" className="contact_block">
                <img className="widget" :src="el.src">
                <a href="#">
                    <p v-if="el.contact !== undefined" className="contact_block_info">{{ el.contact }}</p>
                </a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        contacts_data: {
            type: Array,
            required: true,
        }
    }
}
</script>

<style scoped>

</style>