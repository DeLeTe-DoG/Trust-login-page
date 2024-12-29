<template>
    <header>
        <StatisticsPageHeader :info_panel_data="info_panel_data" />
    </header>
    <section>
        <StaristicsPageStats :changed="changed" :stats_data="stats_data" />
    </section>
    <section>
        <StaristicsPageGroupsStats :groups_stats_data="groups_stats_data" />
    </section>
    <footer>
        <StatisticsPageFooter />
    </footer>
</template>

<script>
    import StatisticsPageHeader from './Statistics-page-header.vue'
    import StaristicsPageStats from './Statistics-page-stats.vue'
    import StaristicsPageGroupsStats from './Statistics-page-groups-stats.vue'
    import Notification from '../../assets/images/Notification.svg'
    import Burger from '../../assets/images/Burger.svg'
    import defaultUser from '../../assets/images/User.svg'
    import SalesImg from '../../assets/images/sales.svg'
    import TimerImg from '../../assets/images/timer.svg'
    import CheckImg from '../../assets/images/check.svg'
    import ShopSalesImg from '../../assets/images/shop-sales.svg'
    import BurgerBag from '../../assets/images/burger-bag.png'
import StatisticsPageFooter from './Statistics-page-footer.vue'
    
    let user_photo = defaultUser;

    let sales = 20978799.00;
    let orders = 970;
    let averageCheck = 530.00;
    let servingTime = '9 мин 35 сек'
    let foodcost = 830;
    let shopOrdersPercentage = 60;
    let shopOrders = shopOrdersPercentage + '%';
    let changed = true;            //если данные изменяются по прошествии 2-х часов

    export default {
        components: {StatisticsPageHeader, StaristicsPageStats, StaristicsPageGroupsStats, StatisticsPageFooter},
        data() {
            return{
                stats_data: [
                    {
                        heading: 'Выручка (₽)',
                        id: 1,
                        stats: sales,
                        icon: SalesImg,
                    },
                    {
                        id: 2,
                        heading: 'Заказы',
                        stats: orders,
                        icon: SalesImg,
                    },
                    {
                        id: 3,
                        heading: 'Средний чек (₽)',
                        stats: averageCheck,
                        icon: CheckImg,
                    },
                    {
                        id: 4,
                        heading: 'Время обслуживания',
                        stats: servingTime,
                        icon: TimerImg,
                    },
                    {
                        id: 5,
                        heading: 'Фудкост',
                        stats: foodcost,
                        icon: BurgerBag,
                    },
                    {
                        id: 6,
                        heading: 'Заказов через киоски (%)',
                        stats: shopOrders,
                        icon: ShopSalesImg,
                    },
                ],

                groups_stats_data: [
                    {
                        id: 1,
                        group_Name: 'Глобус',
                    },
                    {
                        id: 2,
                        group_Name: 'Карат',
                    },
                    {
                        id: 3,
                        group_Name: 'Транс',
                    },
                ],

                info_panel_data: [
                    {
                        id: 1,
                        src: Notification,
                    },
                    {
                        id: 1,
                        src: Burger,
                    },
                    {
                        id: 1,
                        src: user_photo,
                    },
                ],
            }
        }
    }
</script>

<style>
    .stats_block_page{
    margin:0;
        display: flex;
        flex-direction: column;
        width: 92vw;
        margin: 0 auto;
    }
    .stats_blocks_section {
        width: max-content;
        /* margin: 0 auto; */
        display: grid;
        grid-template: 1fr 1fr / 1fr 1fr 1fr;
        gap: 10px;
    }
    .stats_block {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        width: 445px;
        height: 120px;
        background-color: #fff;
        border-radius: 20px;
        padding: 0 0 10px 20px;
    }
    .stats_block_header{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        padding: 10px 10px 0 0;
        letter-spacing: 0.04em;
    }
    .stats_block_heading {
        font-size: 16px;
    }
    .stats_block_stat {
        color: #000;
        font-size: 30px;
        font-family: 900px;
    }
    .stats_block_icon {
        padding: 9px;
        border-radius: 18px;
        background-color: rgb(191, 213, 248, 0.2);
    }
    .stats_blocks_heading{
        font-size: 40px;
        font-weight: 700;
        color: #2e343b;
        padding: 50px 0 40px 0;
    }
    .stats_block_changeTitle{
        color: #969696;
        font-size: 16px;
    }
    .sort_nav, .SBH_dates{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    }
    .sort_nav{
        padding-bottom: 20px;
    }
    .SBH_dates{
        gap: 10px;
        width: max-content;
    }
    .sort_nav_input{
        width: 180px;
        height: 26px;
        padding: 13px 0 10px 50px;
        border-radius: 18px;
        border: none;
    }
    .BGCalendar{
        background: url('../../assets/images/Calendar.svg') no-repeat left #FFF;
        background-position-x: 10px;

    }
    .BGCalendarEdit{
        background: url('../../assets/images/CalendarEdit.svg') no-repeat left #FFF;
        background-position-x: 10px;
    }
    .SBH_dates_chose{
        width: 80px;
        height:50px;
        border-radius: 18px;
        border: none;
        font-size: 16px;
        background-color: #FFF;
        color: #000;
        transition: all 0.3s;
    }
    .SBH_dates_chose:hover{
        background-color: #D2D7E5;
    }
    .SBH_dates_chose:focus {
        background-color: #418CFF;
    }
    .SBH_dates_chose:focus p{
        color: #fff;
    }
    .SBH_dates_chose p {
        margin: 0 auto;
    }
    .footer_info, .footer_info_nav{
        color: #8E9AA9;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 30px 0;
        align-items: center;
    }
    .footer_info{
        border-top: 1px solid #D2D7E5;
    }
    .footer_info_nav{
        justify-content: center;
        gap: 25px;
        list-style-type: none;
        font-size: 14px;
    }
    .groupOriginal{
        font-size: 14px;
        font-weight: 200;
    }
    .stats_block_footer, .change_indicator{
        display: flex;
        flex-direction: row;
    }
    .stats_block_footer{
        gap:10px;
    }
    .change_indicator{
        /* width: 45px; */
        /* height: 20px; */
        border-radius: 10px;
        background: #CCF3DB;
        gap: 6px;
        padding: 2px 5px;
    }
    .change_indicator img{
        width: 10px;
    }
    .change_indicator p{
        font-size: 14px;
        color: #10B853;
    }
</style>