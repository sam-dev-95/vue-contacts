<template>
  <table class="table">
    <thead>
      <tr>
        <th>Name</th>
        <th>Phone Number</th>
        <th>Remove</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(contact, index) in contacts" :key="index">
        <td>{{ contact.firstName + " " + contact.lastName }}</td>
        <td>{{ contact.number }}</td>
        <td class="td-remove">
          <button
            class="btn-remove"
            type="button"
            @click="removeContact(index)"
          >
            Remove
          </button>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    contacts: Array,
  },
  methods: {
    removeContact(index) {
      this.$emit("removeContact", index);
    },
  },
};
</script>

<style lang="css" scoped>
table {
  margin-top: 2rem;
  width: 100%;
  max-width: 70rem;
  -webkit-box-shadow: 1px 5px 10px 0px rgba(0, 0, 0, 0.384);
  -moz-box-shadow: 1px 5px 10px 0px rgba(0, 0, 0, 0.384);
  box-shadow: 1px 5px 10px 0px rgba(0, 0, 0, 0.384);
}

th,
td {
  border: 1px solid #ddd;
  text-transform: capitalize;
  font-size: 1.2rem;
  padding: 1rem;
}

td.td-remove {
  display: flex;
  justify-content: center;
}

tr:nth-child(even) {
  background-color: #f2f2f2;
}

tr:hover {
  background-color: #ddd;
}

th {
  text-align: center;
  background-color: #327ab7;
  color: white;
  font-size: 1.5rem;
}

.btn-remove {
  cursor: pointer;
  padding: 0.5rem 2rem;
  border: 1px solid rgb(238, 50, 50);
  background-color: white;
  color: red;
  transition: 0.2s all;
}

.btn-remove:hover {
  background-color: rgb(238, 50, 50);
  color: white;
}
</style>