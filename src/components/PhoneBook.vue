<template>
  <div class="phone-book">
    <form @submit.prevent="addToContacts">
      <div class="form-inputs">
        <div>
          <label>First Name</label>
          <input v-model="contact.firstName" />
        </div>
        <div>
          <label>Last Name</label>
          <input v-model="contact.lastName" />
        </div>
        <div>
          <label>Phone Number</label>
          <input v-model="contact.number" />
        </div>
      </div>
      <button type="submit">Add</button>
    </form>
    <div>
      <table class="table">
        <thead>
          <tr>
            <th>Name</th>
            <th>Phone Number</th>
            <th />
          </tr>
        </thead>
        <tbody>
          <tr v-for="(contact, index) in contacts" :key="index">
            <td>{{ contact.firstName + " " + contact.lastName }}</td>
            <td>{{ contact.number }}</td>
            <td>
              <button type="button" @click="removeContact(index)">
                Remove
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "PhoneBook",
  props: {
    msg: String,
  },
  data: () => ({
    contact: { firstName: "", lastName: "", number: "" },
    contacts: [],
  }),
  methods: {
    addToContacts: function() {
      this.contacts.push({ ...this.contact });
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
  max-width: 1024px;
  padding: 30px;
}
.phone-book form .form-inputs {
  display: flex;
  justify-content: space-between;
}
.phone-book form button {
  width: 70px;
}
.phone-book form div,
.phone-book form div {
  margin: 12px;
}
@media (max-width: 768px) {
  .phone-book form {
    flex-direction: column;
  }
  .phone-book form button {
    width: 100%;
  }
}
</style>
