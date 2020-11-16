<template>
  
</template>

<script>
export default {
  data() {
    return {
      drawer: true,
      mini: false,
      items: [
        { title: "Home", icon: "fas fa-home", path: "/" },        
      ]
    };
  },
  computed: {
    small() {
      return this.$vuetify.breakpoint.smAndDown;
    }
  },
  watch: {
    mini: n => localStorage.setItem("sidemenu.mini", n ? "true" : "false")
  },
  created() {
    if (this.small) {
      this.drawer = false;
      this.mini = false;
    } else {
      this.mini =
        (localStorage.getItem("sidemenu.mini") || "true") === "true"
          ? true
          : false;
      this.drawer = true;
    }
  }
};
</script>
