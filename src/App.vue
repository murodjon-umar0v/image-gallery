<template>
 <div>
  <Navbar />
  <div class="img-gallery">
   <div class="img-wrapper" v-for="i in count" :key="i">
    <a download @click="downloadFile(i)">
     <img class="showedImages" :src="result[i]" alt="!" />
     <div class="hover-fade">
      <img
       class="download"
       src="https://img.icons8.com/fluency/2x/download.png"
       alt="!"
      />
     </div>
    </a>
   </div>
   <button class="load-more-btn" @click="count += 10">Yana yuklash</button>
  </div>
  <Footer @submit-data="submitData" />
 </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";

export default {
 name: "App",

 components: {
  Navbar,
  Footer,
 },

 watch: {
  result: function () {
   if (this.count > 100) {
    document.location.reload(true);
   }
  },
 },

 methods: {
  downloadFile(i) {
   this.$http
    .get(this.result[i], {
     responseType: "blob",
    })
    .then(
     (response) => {
      const url = window.URL.createObjectURL(new Blob([response.data]));
      const link = document.createElement("a");
      link.href = url;
      link.setAttribute("download", "murodjon-umarov.png");
      document.body.appendChild(link);
      link.click();
     },
     (response) => {
      console.log(response);
     }
    );
  },

  submitData(data) {
   const fullName = data.name + " " + data.surname;
   const fullMessage = `👤 Ism-sharif: ${fullName}\n📧 Email: ${data.email}\n📱 Telefon: ${data.phone}\n✍️ Xabar: ${data.message}`;
   console.log(fullMessage);
   this.$http
    .post(
     `https://api.telegram.org/bot${this.token}/sendMessage?chat_id=${this.chatId}&text=${fullMessage}`
    )
    .then(
     (response) => {
      console.log("Success!", response);
     },
     (error) => {
      console.log("Error!", error);
     }
    );
  },

  fetchRandomPhoto() {
   for (let i = 0; i < 10000; i++) {
    this.image =
     "https://picsum.photos/800/800/?image=" + Math.floor(Math.random() * 100);
    this.result.push(this.image);

    // convert array to set
    this.result = [...new Set(this.result)];
   }
  },
 },

 created() {
  this.fetchRandomPhoto();
 },

 data() {
  return {
   image: "",
   result: [],
   count: 10,

   token: "5467191512:AAGqaiKHxOQdR3kp4G1-9C8Rya88idQEyG0",
   chatId: "760864643",
  };
 },
};
</script>

<style>
@import url(./assets/global.css);
</style>
