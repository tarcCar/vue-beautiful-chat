<template>
  <form id="form-enter" @submit.prevent="enterChat">
    <fieldset>
      <h2 class="fs-title">Register to Enter</h2>
      <input type="text" name="name" placeholder="Name" required>
      <input type="email" name="email" placeholder="E-Mail" required>
      <input type="text" name="phone" placeholder="Phone" required>
      <input type="submit" name="next" class="next action-button" value="Enter">
    </fieldset>
  </form>
</template>

<script>
export default {
  data() {
    return {
      user: {}
    }
  },
  methods: {
    enterChat() {
      this.$emit('userEntered', this.user)
    }
  }
}
</script>

<style scoped>
@import url(https://fonts.googleapis.com/css?family=Montserrat);
/*basic reset*/
* {
  margin: 0;
  padding: 0;
}

/*form styles*/
#form-enter {
  width: 400px;
  margin: 120px auto;
  text-align: center;
  position: relative;
  font-family: montserrat, arial, verdana;
}
#form-enter fieldset {
  background: white;
  border: 0 none;
  border-radius: 3px;
  /* box-shadow: 0 0 15px 1px rgba(0, 0, 0, 0.4); */
  padding: 20px 30px;
  box-sizing: border-box;
  width: 80%;
  margin: 0 10%;

  /*stacking fieldsets above each other*/
  position: relative;
}
/*Hide all except first fieldset*/
#form-enter fieldset:not(:first-of-type) {
  display: none;
}
/*inputs*/
#form-enter input,
#form-enter textarea {
  padding: 15px;
  border: 1px solid #ccc;
  border-radius: 3px;
  margin-bottom: 10px;
  width: 100%;
  box-sizing: border-box;
  font-family: montserrat;
  color: #2c3e50;
  font-size: 13px;
}
/*buttons*/
#form-enter .action-button {
  width: 100px;
  background: #27ae60;
  font-weight: bold;
  color: white;
  border: 0 none;
  border-radius: 1px;
  cursor: pointer;
  padding: 10px 5px;
  margin: 10px 5px;
}
#form-enter .action-button:hover,
#form-enter .action-button:focus {
  box-shadow: 0 0 0 2px white, 0 0 0 3px #27ae60;
}
/*headings*/
.fs-title {
  font-size: 20px;
  text-transform: uppercase;
  color: #2c3e50;
  margin-bottom: 10px;
}
.fs-subtitle {
  font-weight: normal;
  font-size: 13px;
  color: #666;
  margin-bottom: 20px;
}
</style>
