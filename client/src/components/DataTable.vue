<template>
  <div class="data-table">
    <h2><slot name="header"></slot></h2>
    <table>
      <thead>
        <tr>
          <th v-for="(item, i) in headers" :key="i">{{ item.text }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, idx) in items" :key="idx">
          <th scope="row">{{ item.name }}</th>
          <template v-for="(el, i) in item">
            <td :key="i" v-if="i != 'name'">{{ el }}</td>
          </template>
        </tr>
      </tbody>
    </table>
    <footer><slot name="footer"></slot></footer>
  </div>
</template>

<script>
export default {
  props: ['items', 'headers'],
};
</script>

<style scoped>
.data-table {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  margin: 40px;
  border-collapse: collapse;
  font-size: 0.9em;
  font-family: sans-serif;
  min-width: 400px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}
.data-table td,
th {
  text-align: left;
}
.data-table footer {
  margin: 30px 0 30px 0;
  font-style: italic;
}
.data-table thead tr {
  background-color: #009879;
  color: #ffffff;
  text-align: left;
}
.data-table th,
.data-table td {
  padding: 12px 15px;
}
.data-table tbody tr {
  border-bottom: 1px solid #dddddd;
}
.data-table tbody tr:nth-of-type(even) {
  background-color: #f3f3f3;
}
</style>
