<template>
    <div>
        <button @click="counter += 1">{{ counter }}</button>
        <input type="text" v-model="name">
        {{ helloWorld }}

        <list-item  v-for="(people,index ) in updatedPeoples" :name="people.fullName" :id="index" :isActive="activeId == index" :activeId="activeId"></list-item>
        <br>
        <button @click="next">Next</button>
        <!-- <ul style="list-style: none;">
            <li v-for="people in updatedPeoples">
                {{ people.fullName }}
            </li>
        </ul> -->
    </div>
</template>

<script>
import ListItem from '../components/ListItem.vue'
export default {
    components: {
        'list-item' : ListItem
    },
    data() {
        return {
            counter: 0,
            name: null,
            peoples: [
                {
                    first_name: 'Maricar',
                    last_name: 'Lacap',
                    active: true,
                },
                {
                    first_name: 'Kevin',
                    last_name: 'Mensah',
                    active: false,
                },
                {
                    first_name: 'Jerry',
                    last_name: 'Mensah',
                    active: false,
                },
                {
                    first_name: 'Marilyn',
                    last_name: 'Lacap',
                    active: false,
                },
                {
                    first_name: 'Kristian',
                    last_name: 'Mensah',
                    active: false,
                },
            ],
            'activeId':0
        }
    },
    computed: {
        helloWorld() {
            return console.log(this.name, 'executed');
        },
        updatedPeoples() {
            return this.peoples.map(person => ({
                ...person,
                'fullName': `${person.first_name}, ${person.last_name}`

            }))
        }
    },
    methods: {
        next(){
            console.log('NEX');
            this.activeId = (this.activeId + 1) % this.updatedPeoples.length;
        }
    }
}
</script>

<style lang="scss" scoped></style>