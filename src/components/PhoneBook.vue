<template>
  <div class="phone-book">
    <button @click="showBackDrop = true" class="btn-add-contact">Add Contact</button>
    <contacts-table @removeContact="removeContact" :contacts="contacts"/>
    <backdrop v-if="showBackDrop"><form-contact @addToContacts="addToContacts" @closeBackdrop="showBackDrop = false"/></backdrop>
  </div>
</template>

<script>
import Backdrop from './Backdrop.vue';
import FormContact from './Form.vue';
import ContactsTable from './ContactsTable.vue';
export default {
  name: "PhoneBook",
  props: {
    msg: String,
  },
  components:{
    FormContact,
    ContactsTable,
    Backdrop,
  },
  data: () => ({
    // contact: { firstName: "", lastName: "", number: "" },
    contacts: [],
    showBackDrop: false
  }),
  methods: {
    addToContacts (contact) {
      this.contacts.push({...contact});
      this.showBackDrop = false;
    },
    removeContact: function(cIndex) {
      this.contacts.splice(cIndex, 1);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.phone-book {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.btn-add-contact{
  padding: 1rem 3rem;
  background-color: #327AB7;
  color: white;
  border-radius: 10rem;
  font-size: 1.5rem;
  font-weight: bold;
  cursor: pointer;
  transition: all .3s;
  border: 1px solid #327AB7;
  color: #327AB7;
  background-color: white;
}

.btn-add-contact:hover{
  background-color: #327AB7;
  color: white;
  transform: scale(1.1);
}
</style>
