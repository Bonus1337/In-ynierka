<template>
  <div>
    <h1 class="mx-5">Dokumenty</h1>

    <table class="my-5">
      <tr>
        <th>Nazwa</th>
        <th>Waga</th>
      </tr>
      <tr>
        <td>{{ files.name }}</td>
        <td>2.2MB <v-icon>mdi-download</v-icon></td>
      </tr>
      <tr>
        <td>Dokumenty zgłoszeń</td>
        <td>2.3MB <v-icon>mdi-download</v-icon></td>
      </tr>
      <tr>
        <td>karta praktyk</td>
        <td>2.4MB <v-icon>mdi-download</v-icon></td>
      </tr>
      <tr>
        <td>karty zgłoszeń</td>
        <td>1.2MB <v-icon>mdi-download</v-icon></td>
      </tr>
    </table>
  </div>
</template>
<script>
export default {
  data() {
    return {
      files: [
        {
          file: "Dokumenty praktyk",
          size: "2.2MB",
        },
        {
          file: "Dokumenty zgłoszeń",
          size: "2.3MB",
        },
        {
          file: "karta praktyk",
          size: "2.4MB",
        },
        {
          file: "karty zgłoszeń",
          size: "1.2MB",
        },
      ],
    };
  },
};
</script>

<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td,
th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>
