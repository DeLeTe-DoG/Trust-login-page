<template>
    <div className="stats_block_page">

        <h1 className="stats_blocks_heading">Проекты</h1>

        <div className="sort_nav">
            <div className="SBH_dates">
                <input className="sort_nav_input BGCalendar" type="text" placeholder="Дата с">
                <input className="sort_nav_input BGCalendarEdit" type="text" placeholder="Дата по">
            </div>
            <div className="SBH_dates dates">
                <button className="SBH_dates_chose"><p>День</p></button>
                <button className="SBH_dates_chose"><p>Неделя</p></button>
                <button className="SBH_dates_chose"><p>Месяц</p></button>
                <button className="SBH_dates_chose"><p>Квартал</p></button>
            </div>
        </div>

    <div className="stats_blocks_section">
        

        <div className="stats_block" v-for="el in stats_data" :key="el.id">
            <div className="stats_block_header">
                <h3 className="stats_block_heading">{{ el.heading }}</h3>
                <img :src="el.icon" className="stats_block_icon widget">
            </div>
            <h2 className="stats_block_stat">{{ el.stats }}</h2>
            <div className="stats_block_footer">
                <div className="change_indicator">
                    <img src="../../assets/images/ArrowUp.svg">
                    <p>7%</p>
                </div>
                <p className="stats_block_changeTitle">Последние два часа</p>
            </div>
        </div>
    </div>
    </div>
</template>

<script>
export default {
    props: {
        stats_data: {
            type: Array,
            required: true,
        },
        changed: {
            type: Boolean,
            required: true,
        }
    }
}
</script>

<style></style>