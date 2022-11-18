<template>
    <v-card>
        <v-card-title>
            Pracodawcy
            <v-spacer/>

        </v-card-title>
        <v-data-table
            :headers="headers"
            :items="users"
>
        <template v-slot:items="props">
            <td>{{ props.item.name }}</td>
            <td>{{ props.item.email }}</td>
            <td>{{ props.item.phone }}</td>
            <td>{{ props.item.city }}</td>
            <td>{{ props.item.website }}</td>
            <td>{{ props.item.created_at }}</td>
        </template>
</v-data-table>
    </v-card>
</template>

<script>


export default {
    data() {
        return {
            headers: [
                { text: 'Imie i nazwisko', value: 'name' },
                { text: 'E-mail', value: 'email' },
                { text: 'Nr telefonu', value: 'phone' },
                { text: 'Miasto', value: 'city' },
                { text: 'Strona internetowa', value: 'web' },
                { text: 'Stworzone', value: 'created_at' }
            ],
            users: [
                {
                    name: 'Jan Kowalski',
                    email: 'Jan_kowalski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.jankowalski.pl',
                    created_at: '2020-01-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                 {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
                {
                    name: 'Kuba Adamski',
                    email: 'Kuba_adamski@gmail.com',
                    phone: '123456789',
                    city: 'Warszawa',
                    web: 'www.kubaadamski.pl',
                    created_at: '2020-02-01'
                },
            ]
        }
    },
}
</script>
