<template>
  <table class="user-table">
    <thead>
      <tr> 
        <th>{{Username}}</th>
        <th>{{Email}}</th>
        <th>{{phone}}</th>
        <th>{{website}}</th>
        <th>{{addressStr}}</th>
      </tr>
    </thead>
    <tbody v-for="data in Content" :key="data.id">
      <tr> 
        <td>{{data.username}}</td>
        <td>{{data.email}}</td>
        <td>{{data.phone}}</td>
        <td>{{data.website}}</td>
        <td>{{data.address.street}} {{data.address.suite}}</td>
      </tr>
    </tbody>
  </table>
</template>


<script>
console.log("dataTable.vue start");
let viewModel = { 
  Username: "使用者名稱",
  Email: "郵件",
  phone: "電話",
  website: "網站",
  addressStr: "地址"
};
module.exports = {
  props: ["Content"],
  data: function() {
    return viewModel;
  }
};
</script>
<style scoped>
table {
  border-spacing: 0;
  border-collapse: separate;
  width: 100%;
  text-align: left;
}

th {
  font-size: 12px;
  background-color: #fafafa;
  border-bottom: 1px solid rgba(0, 0, 0, 0.12);
  padding: 8px 24px;
  font-weight: 500;
  text-align: left;
  color: rgba(0, 0, 0, 0.54);
}

tbody {
  background-color: #ffffff;
}

tbody:hover {
  background-color: #f0f0f0;
}

td {
  color: rgba(0, 0, 0, 0.54);
  font-size: 13px;
  line-height: 16px;
  height: 48px;
  padding: 0;
  border-bottom: 1px solid rgba(0, 0, 0, 0.06);
  white-space: nowrap;
  padding: 10px 24px;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

tbody:hover .button_icon {
  opacity: 1;
}

.button_icon {
  opacity: 0;
  font-size: 16px;
  vertical-align: middle;
  align-items: center;
  text-align: center;
  border-radius: 50%;
  cursor: pointer;
  color: rgba(0, 0, 0, 0.52);
  line-height: 40px;
  background: none;
  box-shadow: none;
  border: none;
  font-size: 25px;
  padding: 0px 5px;
}

.button_icon:hover {
  color: rgba(0, 0, 0, 0.78);
}
</style>

