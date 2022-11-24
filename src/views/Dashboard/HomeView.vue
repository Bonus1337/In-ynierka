<template>
  <v-container>
    <v-row no-gutters>
      <v-col class="text-center" cols="12">
        <h1>Profil Studenta</h1>
      </v-col>
      <v-col class="text-center" cols="12">
        <v-avatar class="center" color="primary" size="150">{{
          userFirst
        }}</v-avatar>
      </v-col>
      <v-col class="text-center" cols="6">
        <v-card class="pa-2 my-2" outlined tile> Imie i nazwisko: </v-card>
        <v-card class="py-2 my-2" outlined tile> Wydział: </v-card>
        <v-card class="pa-2 my-2" outlined tile> Kierunek studiów: </v-card>
        <v-card class="pa-2 my-2" outlined tile> Nr Albumu: </v-card>
        <v-card class="pa-2 my-2" outlined tile> Miejsce praktyk: </v-card>
        <v-card class="pa-2 my-2" outlined tile> Data rozpoczęcia: </v-card>
        <v-card class="pa-2 my-2" outlined tile> Data zakończenia: </v-card>
      </v-col>
      <v-col class="text-center" cols="6">
        <v-card class="pa-2 my-2" outlined tile>
          {{ userInfo.name }}
        </v-card>
        <v-card class="pa-2 my-2" outlined tile>
          {{ userInfo.faculty }}
        </v-card>
        <v-card class="pa-2 my-2" outlined tile>
          {{ userInfo.departament }}
        </v-card>
        <v-card class="pa-2 my-2" outlined tile>
          {{ userInfo.album }}
        </v-card>
        <v-card class="pa-2 my-2" outlined tile>
          {{ userInfo.place }}
        </v-card>
        <v-card class="pa-2 my-2" outlined tile>
          {{ userInfo.start }}
        </v-card>
        <v-card class="pa-2 my-2" outlined tile>
          {{ userInfo.end }}
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      userFirst: "MS",
      userInfo: {
        name: "Maciej Szymański",
        faculty: "Inżynierii i Ekonomii",
        departament: "Informatyka",
        album: "10569",
        place: "Narodowy Fundusz Ochrony Środowiska i Gospodarki Wodnej",
        start: "01.10.2022",
        end: "01.02.2023",
      },
    };
  },
};
</script>
<style scoped>
.center {
  margin: 50px 0;
  color: white;
  font-size: 34px;
}
.text-center {
  font-size: 20px;
}
</style>
