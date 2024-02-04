<template >
    <div>
        <input type="text" v-model="newDelas">
        <button @click="addDel">Добавить</button>
        <ul>
            <li v-for="delas in dela" 
            :key="delas.id">
                <p :style="{ 'text-decoration': delas.checked ? 'line-through' : 'none' }">
                    {{ delas.text }}
                </p>
                <input type="checkbox" v-model="delas.checked">
                <button @click="delitDels(delas.id)">Удалить</button>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name: 'Chec',
    props: {
        dela: Object,
        newDelas: String
        
    },
    emits: ['addDela', 'delit','editDela'],
    data() {
        return {
            newDelas: '',
        }
    },
    methods: {
        editDel(delas){
            this.$emit('addDela', delas)
        },
        delitDels(id) {
            this.$emit('delit', id)
        },
        addDel() {
            this.$emit('addDela', this.newDelas)
        }
    }
}
</script>
<style></style>