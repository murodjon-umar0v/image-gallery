<template>
 <div>
  <footer>
   <div class="container">
    <div class="form">
     <form method="POST" @submit.prevent="submitData">
      <input
       v-model="name"
       type="text"
       name="fullName"
       id="name"
       placeholder="Ism"
       required
      />
      <input
       v-model="surname"
       type="text"
       name="text"
       id="email"
       placeholder="Familiya"
       required
      />
      <input
       v-model="email"
       type="email"
       name="email"
       id="email"
       placeholder="Email manzil"
       required
      />
      <input
       v-model="phone"
       type="text"
       name="phone"
       id="subject"
       placeholder="Telefon raqam"
       required
      />
      <br />
      <br />
      <textarea
       v-model="message"
       name="message"
       id="message"
       cols="45"
       rows="10"
       placeholder="Izoh qoldiring"
       required
      ></textarea>
      <br />
      <br />
      <input type="submit" value="Yuborish" id="btn" />
     </form>
    </div>

    <span class="socials social-web">
     <div>A'loqa uchun</div>
     <a href="https://github.com/murodjon-umar0v" target="_blank">
      <img
       src="https://img.icons8.com/plasticine/2x/github.png"
       style="background: #fff"
       alt="LinkedIn"
      />
     </a>
     <a href="https://www.instagram.com/murodjon.2559" target="_blank">
      <img
       src="https://img.icons8.com/color/2x/instagram-new--v2.gif"
       alt="Instagram"
      />
     </a>
     <a
      href="https://www.linkedin.com/in/murodjon-umarov-90750321a/"
      target="_blank"
     >
      <img
       src="https://img.icons8.com/color/2x/linkedin-2--v2.gif"
       alt="LinkedIn"
      />
     </a>
     <a href="https://www.facebook.com/murodjon.umarov.921/" target="_blank">
      <img
       src="https://img.icons8.com/color/2x/facebook-circled--v4.gif"
       alt="Facebook"
      />
     </a>
     <a href="https://t.me/murodjon2559" target="_blank">
      <img
       src="https://img.icons8.com/color/2x/telegram-app--v5.gif"
       alt="Telegram"
      />
     </a>
    </span>
   </div>
  </footer>
  <div class="dev">
   💻 Developed by
   <a href="https://www.instagram.com/murodjon.2559">Murodjon Umarov</a> with
   <a href="https://vuejs.org/">Vue.js</a>
   💻
  </div>
 </div>
</template>

<script>
export default {
 data() {
  return {
   name: "",
   surname: "",
   email: "",
   phone: "",
   message: "",
  };
 },
 methods: {
  submitData() {
   this.$emit("submit-data", {
    name: this.name,
    surname: this.surname,
    email: this.email,
    phone: this.phone,
    message: this.message,
   });
  },
 },
};
</script>
