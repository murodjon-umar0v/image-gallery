<template>
 <nav class="container">
  <span class="avatar">
   <a
    target="_blank"
    href="data:image/jpeg;base64,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"
   >
    <img src="../assets/murod.jpg" alt="" />
   </a>
  </span>
  <span>
   <h3>Image Gallery</h3>
  </span>

  <span class="socials social-web">
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

  <div class="dropdown-wrapper">
   <div class="dropdown">
    <button class="dropbtn" @click="showDrop = !showDrop">
     <img
      src="https://img.icons8.com/ios/2x/menu.png"
      class="bar-icon"
      alt=""
     />
    </button>
    <div v-show="showDrop" class="dropdown-content">
     <span class="socials">
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
   </div>
  </div>
 </nav>
</template>

<script>
export default {
 name: "Navbar",
 data() {
  return {
   showDrop: false,
  };
 },
};
</script>
