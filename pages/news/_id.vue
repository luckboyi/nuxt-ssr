<template>
    <div>
        <h2>News-Content[{{$route.params.id}}]</h2>
        <h4>姓名：{{info.name}}</h4>
        <h4>年龄：{{info.age}}</h4>
        <h4>兴趣：{{info.interest}}</h4>
        <ul>
            <li>
                <a href="/">Home</a>
            </li>
        </ul>
    </div>
</template>
<script>
    import axios from 'axios'
    export default {
        validate ({params}) {
            //必须是个number
            return /^\d+$/.test(params.id)
        },
        data(){
            return {
            }
        },
        async asyncData(){
            let {data} = await axios.get('https://api.myjson.com/bins/f0xiz')
            return {info:data}
        }

    }
</script>