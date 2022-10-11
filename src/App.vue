<script>
import ListComponent from './components/ListComponent.vue';

  export default{
    data(){
      return {
        message: 'Hola Mundo',
        informacion:[
          {
            header: 'How many team members can I invite?',
            description: 'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.'
          },
          {
            header: 'What is the maximum file upload size?',
            description: 'No more than 2GB. All files in your account must fit your allotted storage space.'
          },
          {
            header: 'How do I reset my password?',
            description: 'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.'
          },
          {
            header: 'Can I cancel my subscription?',
            description: 'Yes! Send us a message and we’ll process your request no questions asked.'
          },
          {
            header: 'Do you provide additional support?',
            description: 'Chat and email support is available 24/7. Phone lines are open during normal business hours.'
          },
        ]
      }
    },
    components:{
      ListComponent
    }
    
  }

</script>

<template>

  <div class="card">
    <img src="./assets/images/illustration-woman-online-desktop.svg" class="img-mobile" alt="Woman Working">
    <img class="box-img" src="./assets/images/illustration-box-desktop.svg" alt="box">
    <div class="to-right">
      <h1>FAQ</h1>
      
      <dl>
        <ListComponent class="lista"
        v-for="i in informacion"
        :key="i"
        :lista="i"
        ></ListComponent>
      </dl>
    </div>

  </div>

</template>

<style>

  :root{
    --Softviolet: hsl(273, 75%, 66%);
    --Softblue: hsl(240, 73%, 65%);
  }

  h1{
    font-size: 2.5em;
    color: hsl(231, 12%, 12%);
  }

  .img-mobile{
    display: none;
  }

  .card{    
    position: relative;
    top: 10vh;


    background: white;
    background-image: url(./assets/images/illustration-woman-online-desktop.svg), url(./assets/images/bg-pattern-desktop.svg);
    background-repeat: no-repeat, no-repeat;
    background-position: -73px 50%, -579px 65%;
    padding: 30px;
    width: 900px;
    /* max-width: 80%; */
    border-radius: 20px;
    min-height: 500px;

  }

  .to-right{
    width: 50%;
    margin-left: auto;
  }

  .box-img{
    position: absolute;
    top: 41%;
    left: -94px; 
  }

  @media (max-width: 1000px) {
      .card{
        background-size: 60%, 60%;
        background-position: -73px 50%, -73px 60%;
        width: 90vw;
      }
  }

  @media (max-width: 768px) {
      .card{
        margin-top: 50px;
        margin-bottom: 60px;

        padding-top: 100px;
        background: white;
        max-width: 450px;
        width: 90vw;
        min-width: 370px;
      }
      .box-img{
        position: absolute;
        width: 100px;
        top: -10px;
        left: 50%;
        transform: translateX(-150%);
      }
      .to-right{
        width: 100%;
      }

      .img-mobile{
        display: block;
        width: 290px;
        position: absolute;
        top: -100px;
        right: 50%;
        transform: translateX(50%);
      }
      h1{
        text-align: center;
      }
      
  }

</style>
