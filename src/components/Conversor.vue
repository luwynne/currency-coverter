<template>
    <div class="conversor">
        <h2>{{moedaA}} para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" v-bind:placeholder="moedaA" >
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>
</template>

<script>

export default{

    name:'conversor',
    props: ["moedaA", "moedaB"],

    data(){
        return{
            moedaA_value : "",
            moedaB_value : 0,
        }
    },

    methods:{

        converter(){
            let de_para = this.moedaA + "_" + this.moedaB;
            let url = "https://free.currencyconverterapi.com/api/v6/convert?q="+de_para+"&compact=ultra&apiKey=***********";
            fetch(url).then(res=>{ // fetch is an execution of the url purposed, which will return a result of that execition
                return res.json() // then we are transforming the result of the return into json
                .then(json => {
                    let cotacao = json[de_para];  // grabbing only the part that interests us from that return
                    this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);  // parsing the moeda a into a float to ensure
                });         // multiplying the value of the. to fixed(2) means put only 2 decimal slots at the end
            });

        }

    }

};


</script>


<style scoped>

.conversor{
    max-width: 300px;
    padding: 30px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}

</style>