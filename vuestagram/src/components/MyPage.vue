<template>
<div style="padding : 10px">
  <h4>νλ‘μ</h4>
  <input placeholder="π" />
  <div class="post-header" v-for="(a,i) in follower " :key="i">
    <div class="profile" :style="`background-image:url(${a.image})`"></div>
    <span class="profile-name">{{a.name}}</span>
  </div>
</div>
</template>

<script>
import { onMounted, reactive, ref, toRef } from "vue";  //λͺ¨λ  λ°μ΄ν°λ₯Ό reference data typeμΌλ‘ κ°μΈμΌ μ€μκ° λ°μκ°λ₯ 
import axios from 'axios';
import {useStore} from 'vuex';
export default {
    name: 'mypage',
    props:{
        one: Number,
    },
    //composition API
    setup(props, context){         //μ²«λ²μ§Έλ ν­μ props
        //setup()μμμ λ°μ΄ν° μμ± μ‘°μ ν μ μκ³  methods hook λ±μ λ§λ€ μ μμ
        let follower = ref([]);             //λλ¨Έμ§ μλ£ν 
        // let test = reactive({name:'kim'})   //λ³΄ν΅ array, object 
        // test;
        // let { one } = toRefs(props); //composition APIμμ props μ¬μ©λ² 
        // console.log(one.value);
        // let re = computed(()=>{
        //     return follower.value.length})
        //     console.log(re.value)
        // let store = useStore();
        // console.log(store.state.name)
        
        onMounted(() => {            //composition APIμμ Lifecycle Hook μ μ¬μ©νκΈ° μν΄
            axios.get('/follower.json').then((a) =>{
            follower.value = a.data //[{},{},{},{},{}]  //λ°μ΄ν° μμ νλ €λ©΄ λ°μ΄ν°.value
        })
    })
            return {follower}
    },
    date(){
        return{

        }
    }
}
</script>

<style>

</style>