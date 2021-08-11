<template>
  <form @submit.prevent="addToContacts" class="form">
      <h2 class="form-heading">Add Contact</h2>
    <div class="form-inputs">
      <div class="input-box">
        <label>First Name</label>
        <input v-model="contact.firstName" />
      </div>
      <div class="input-box">
        <label>Last Name</label>
        <input v-model="contact.lastName" />
      </div>
      <div class="input-box">
        <label>Phone Number</label>
        <input v-model="contact.number" />
      </div>
    </div>
    <div class="form-buttons">
      <button class="btn-add" type="submit">Add</button>
      <button class="btn-cancel" @click="closeBackdrop">cancel</button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      contact: { firstName: "", lastName: "", number: "" },
    };
  },
  methods: {
    addToContacts() {
      this.$emit("addToContacts", this.contact);
    },

    closeBackdrop(){
        this.$emit('closeBackdrop')
    }
  },
};
</script>

<style scoped>
.form {
  background-color: white;
  padding: 2rem 4rem;
  display: flex;
  flex-direction: column;
}

.form-heading{
    align-self: center;
    font-size: 2rem;
    color: #327AB7;
    margin-bottom: 2rem;
}

.input-box {
  display: flex;
  flex-direction: column;
  margin-bottom: 2rem;
}

.input-box label {
  font-size: 1.7rem;
  color: rgb(88, 88, 88);
}

.input-box input{
    height: 3rem;
    border: 1px solid #327AB7;
}

.form-buttons{
    display: flex;
    justify-content: center;
}

.form-buttons button{
    border: none;
    padding: 1rem 3rem;
    color: white;
    text-transform: capitalize;
    cursor: pointer;
    font-size: 1.5rem;
}

.form-buttons button.btn-add{
    background-color: #327AB7;
    margin-right: 1rem;
}

.form-buttons button.btn-cancel{
    background-color: rgb(238, 50, 50);
}
</style>