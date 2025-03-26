<template>
  <div class="app">
    <div class="container">
      <h2>Customer Inquiry Tracker</h2>

      <form @submit.prevent="addInquiry">
        <input
          type="text"
          v-model="name"
          placeholder="Customer Name"
          required
        />
        <textarea
          v-model="inquiry"
          placeholder="Inquiry Details"
          required
        ></textarea>
        <select v-model="priority">
          <option>Low</option>
          <option>Medium</option>
          <option>High</option>
        </select>
        <button type="submit">Add Inquiry</button>
      </form>

      <h3>Inquiry List:</h3>
      <ul v-if="inquiries.length">
        <li v-for="(inq, index) in inquiries" :key="index">
          <p><strong>{{ inq.name }}</strong> ({{ inq.priority }})</p>
          <p>{{ inq.inquiry }}</p>
          <button @click="removeInquiry(index)">Delete</button>
        </li>
      </ul>
      <p v-else>No inquiries yet.</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      inquiry: "",
      priority: "Low",
      inquiries: []
    };
  },
  methods: {
    addInquiry() {
      if (!this.name || !this.inquiry) return;
      this.inquiries.unshift({
        name: this.name,
        inquiry: this.inquiry,
        priority: this.priority
      });
      this.name = "";
      this.inquiry = "";
      this.priority = "Low";
    },
    removeInquiry(index) {
      this.inquiries.splice(index, 1);
    }
  }
};
</script>

<style scoped>
.app {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: #f4f4f4;
  font-family: Arial, sans-serif;
}
.container {
  background: white;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 400px;
  text-align: center;
}
input, textarea, select, button {
  width: 100%;
  margin: 5px 0;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
button {
  background: #007bff;
  color: white;
  cursor: pointer;
}
button:hover {
  background: #0056b3;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  background: #f9f9f9;
  padding: 10px;
  margin-top: 5px;
  border-radius: 4px;
}
</style>
