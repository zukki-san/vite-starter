<template>
    <section class="alert alert-primary">
        <h1>{{ data.title }}</h1>
        <p>{{ data.message }}</p>
        <textarea v-model="data.mydata" rows="5" class="form-control"></textarea>
    </section>
</template>

<script>
import axios from 'axios'
import { reactive, onMounted } from 'vue'

const url = "/data.txt"

export default {
    setup(props) {
        const data = reactive({
            title: 'Axios',
            message: 'This is axios sample.',
            mydata: '',
        })
        // 同期的に行う場合
        // const getData = async() => {
        //     let result = await axios.get(url)
        //     data.mydata = result.data
        // }

        // 非同期で行う場合
        const getData = () => {
            axios.get(url).then((result) => {
                data.mydata = result.data
            })
        }
        
        onMounted(() => {
            getData()
        })
        return { data, getData }
    }
}
</script>