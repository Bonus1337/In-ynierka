<template>
  <div>
    <h1 class="mx-5">Podsumowanie Praktyk</h1>
    <template>
      <v-data-table
        dense
        :headers="headers"
        :items="days"
        item-key="date"
        class="elevation-1"
      ></v-data-table>
    </template>
    <v-row justify="center">
      <v-dialog v-model="dialog" persistent max-width="600px">
        <template v-slot:activator="{ on, attrs }">
          <v-btn class="my-5" color="primary" dark v-bind="attrs" v-on="on">
            Dodaj dzień
          </v-btn>
        </template>
        <v-card>
          <v-card-title>
            <span class="text-h5">Podsumowanie Dnia</span>
          </v-card-title>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Data"
                    type="date"
                    v-model="date"
                    required
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-select
                    :items="['1', '2', '3', '4', '5']"
                    label="Ocena"
                    v-model="rating"
                    required
                  ></v-select>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-autocomplete
                    :items="[
                      'H1',
                      'H2',
                      'H3',
                      'H4',
                      'H5',
                      'H6',
                      'H7',
                      'H8',
                      'H9',
                    ]"
                    label="Punkty z praktyk"
                    multiple
                    v-model="tasks"
                  ></v-autocomplete>
                </v-col>
                <v-col cols="12">
                  <v-textarea
                    filled
                    label="Opisz dzień"
                    auto-grow
                    v-model="description"
                    placeholder="Jak ci minął dzisiejszy dzień?"
                    required
                  ></v-textarea>
                </v-col>
              </v-row>
            </v-container>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="blue darken-1" text @click="dialog = false">
              Zamknij
            </v-btn>
            <v-btn color="blue darken-1" text @click="addData()"> Dodaj </v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
  </div>
</template>

<script>
export default {
  data: () => ({
    date: "",
    description: "",
    rating: "",
    tasks: [],
    dialog: false,
    days: [{}],
    headers: [
      {
        text: "Data",
        align: "start",
        sortable: false,
        value: "date",
      },

      { sortable: false, text: "Skala przyjemności", value: "rating" },
      { sortable: false, text: "Zadania", value: "tasks" },
      { sortable: false, text: "Ocena dnia", value: "description" },
    ],
  }),
  methods: {
    addData() {
      this.dialog = false;
      this.days.push({
        date: this.date,
        description: this.description,
        rating: this.rating,
        tasks: this.tasks,
      });
      this.date = "";
      this.description = "";
      this.rating = "";
      this.tasks = [];
    },
  },
};
</script>
