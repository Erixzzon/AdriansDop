<template>
    <div>
        <div v-if="invite">
            <div class="row justify-content-md-center">
                <div class="section first col-12">
                    <h1 class="p-5">
                        Välkommen<br/>
                        till Adrians dop
                    </h1>                
                </div>
            </div>
            <div class="row justify-content-md-center">
                    <div class="section second col-12">
                        <h1 class="py-5">4 april är det dags för Adrians dop</h1>
                    </div>
                </div>
            <div class="row justify-content-md-center">
                <div class="section third col-12">
                    <img id="cupcakes" src="../assets/cupcakes.jpg">
                </div>
            </div>
            <div class="row justify-content-md-center">
                <div class="section fourth col-12">
                    <h1 class="py-5">
                        Och du är självklart bjuden
                    </h1>
                </div>
            </div>
            <div class="row justify-content-md-center">
                <div class="section fifth col-12 py-5">
                    <h2 class="">
                        Var
                    </h2>
                    <p>
                        Dopet äger rum i Österhaninge kyrka<br/>
                        <i>Klockarlötsvägen, 137 95 Österhaninge</i>
                    </p>                   
                    <p>
                        Fika bjuds på i Landfjärden<br/>
                        <i>Vassvägen 8, 148 93 Ösmo</i>
                    </p>
                    
                </div>
            </div>
            <div class="row justify-content-md-center">
                <div class="section sixth col-12">
                    <h1 class="pt-5">
                        Hoppas du kan vara med
                    </h1>
                    <h2>OSA senast 20 mars</h2>
                    <div class="form-group pb-5">
                        <div class="col-4 mx-auto">
                            <input type="text" class="form-control" v-model="code">
                            <button class="btn btn-outline-secondary btn-block" v-on:click="submitCode">Svara</button>
                            <p v-if="error">Ogiltlig kod</p>
                        </div>
                    </div>               
                </div>
            </div>
        </div>
        <div v-else>
            <div class="row justify-content-md-center">
                <div class="section response col-12">
                    <form name="response" method="POST" data-netlify="true" netlify class=" pt-5">
                        <input type="hidden" name="kod" v-model="code">
                        <div class="form-group col-4 mx-auto">
                            <label for="antal">Antal personer</label>
                            <input type="number" class="form-control" id="antal" name="antal" min="0" max="10">
                        </div>
                        <div class="form-group form-check col-4 mx-auto">
                            <input type="checkbox" class="form-check-input" id="dop" name="dop">
                            <label class="form-check-label" for="dop">Vi kommer till dopet</label>
                        </div>
                        <div class="form-group form-check col-4 mx-auto">
                            <input type="checkbox" class="form-check-input" id="fika" name="fika">
                            <label class="form-check-label" for="fika">Vi kommer till fikat</label>
                        </div>
                        <div class="col-4 mx-auto">
                            <button type="submit" class="btn btn-outline-secondary btn-block" v-on:click="submit">Skicka</button>
                        </div>
                        <p v-if="submitted">Tack för ditt svar</p>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Start',
    data () {
        return {
            inviteCodes: ['a9u7','3g7k','44nj','wd8p'],
            invite: true,
            code: '',
            error: false,
            submitted: false
        }      
    },
    methods: {
        submitCode: function () {
            this.code = this.code.toLowerCase();
            if(this.inviteCodes.includes(this.code)){
                this.invite = false;
            }else{
                this.error = true;
            }
        },
        submit: function(){
            this.submitted = true;
        }
    }
}
</script>

<style>
    .section{        
        max-width: 540px;
        text-align: center;
        background-repeat: no-repeat;
        background-size: cover;
    }

    .first{
        height: 100vh;
        background-image: url('../assets/Adrian.jpg');
        color: #FFF;
        text-shadow: 0 0 3px #000;
    }

    .second{
        background-color: #e6ffff;
        color: #808080
    }

    .third{
        background-color: #e6ffff;
    }

    #cupcakes {
        border-radius: 5px;
        width: 80%;     
    }

    .fourth{
        background-color: #e6ffff;
        color: #808080
    }

    .fifth{
        background-color: #e6ffff;
        color: #808080
    }

    .sixth{
        background-color: #ffffff;
        color: #808080
    }

    .response {
        height: 100vh;
        background-color: #e6ffff;
        color: #808080
    }
</style>