<template>
  <div className="all">
    <header>
      <PageHeader :contacts_data="contacts_data" />
    </header>
    <section>
      <PageFormBlock />
    </section>
    <footer>
      <PageFooter />
    </footer>
  </div>
</template>

<script>
  import Phone from "./assets/images/Phone.svg"
  import Email from "./assets/images/Email.svg"
  import Whatsup from "./assets/images/Whatsup.svg"
  import Telegram from "./assets/images/Telegram.svg"
  import PageHeader from './components/Page-header.vue';
  import PageFooter from './components/Page-footer.vue';
  import PageFormBlock from './components/Page-form-block.vue';

  export default {
    components: {PageHeader, PageFooter, PageFormBlock},
    
    data(){
      return{
        contacts_data: [
        {
          id: 1,
          src: Phone,
          contact: "+7 900 888 88 88",
        },
        {
          id: 2,
          src: Email,
          contact: "trust.tatar@gmail.com"
        },
        {
          id: 3,
          src: Telegram,
        },
        {
          id: 5,
          src: Whatsup,
        },
      ]
    }
    }
  }
</script>

<style scoped>

</style>