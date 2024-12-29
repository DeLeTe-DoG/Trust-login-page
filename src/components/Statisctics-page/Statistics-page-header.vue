<template>
    <div className="header_block">
        <div className="group_logo">
            <img className="group_logo_img" src="/src/assets/images/Group.svg">
        </div>
        <div className="contacts_blocks">
            <input className="search_input" placeholder="Поиск">
            <div v-for="el in info_panel_data" className="contact_block">
                <img className="widget" :src="el.src">
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            info_panel_data: {
                type: Array,
                required: true,
            }
        }
    }
</script>

<style></style>