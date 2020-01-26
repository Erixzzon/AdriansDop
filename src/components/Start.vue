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
                <div class="section fifth col-12">
                    <h2 class="">
                        Var
                    </h2>
                    <p>
                        Dopet äger rum i Österhaninge kyrka<br/>
                        <i>Klockarlötsvägen, 137 95 Österhaninge</i>
                    </p>                   
                </div>
            </div>
            <div class="row justify-content-md-center">
                <div class="section sixth col-12">
                    <h2 class="">
                        När
                    </h2>
                    <p>
                        Dopet börjar klockan 14:30
                    </p>                                      
                </div>
            </div>
            <div class="row justify-content-md-center">
                <div class="section seventh col-12 pb-5">
                    <h2 class="">
                        Efteråt
                    </h2>
                    <p>
                        Bjuds det på fika i Landfjärdem<br/>
                        <i>Vassvägen 8, 148 93 Ösmo</i>
                    </p>                                       
                </div>
            </div>
            <div class="row justify-content-md-center">
                <div class="section eight col-12">
                    <h1 class="pt-5">
                        Hoppas du kan vara med
                    </h1>
                    <h2>OSA senast 14 mars</h2>
                    <div class="form-group pb-5">
                        <div class="col-4 mx-auto">
                            <input type="text" class="form-control" v-model="code" placeholder="Din kod">
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
                    <form name="svar" method="POST" class="pt-5">
                        <input type="hidden" name="form-name" value="svar" />   
                        <input type="hidden" name="kod" v-model="code">
                        <div class="form-group col-4 mx-auto">
                            <label for="antal">Antal personer</label>
                            <input type="number" class="form-control" id="antal" name="antal" min="0" max="10">
                        </div>
                        <div class="form-group form-check col-8 mx-auto">
                            <input type="checkbox" class="form-check-input" id="dopochfika" name="dopochfika">
                            <label class="form-check-label" for="dopochfika">Vi kommer till dopet och fikat</label>
                        </div>
                        <div class="form-group form-check col-8 mx-auto">
                            <input type="checkbox" class="form-check-input" id="dop" name="dop">
                            <label class="form-check-label" for="dop">Vi kommer bara till dopet</label>
                        </div>
                        <div class="form-group form-check col-8 mx-auto">
                                <input type="checkbox" class="form-check-input" id="inget" name="inget">
                                <label class="form-check-label" for="inget">Tyvärr, vi kan inte komma</label>
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
            inviteCodes: ['a9u7','3g7k','44nj','wd8p','h9u7', '4h9k', '49u3', 'rwq3', 'p902', 'hv6q', '65m4', '00gw', 'mkf7', 'x4ft', 'yt6n', 'af7j', '11bc', 'pz6b', 'vu48', 'rk22', '99y7', 'uu59', 'das7', 'hi8p', '87k1', '4ffo', 'ang1', 'das3', 'b4j5', 'd1ck', 'k0rv', 'b00b'],
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
        background-image: url('../assets/Adrian.jpeg');
        color: #FFF;
        text-shadow: 0 0 3px #000;
    }

    .second{
        background-color: #cceeff;
        color: #808080
    }

    .third{
        background-color: #cceeff;
    }

    #cupcakes {
        border-radius: 5px;
        width: 80%;     
    }

    .fourth{
        background-color: #cceeff;
        color: #808080
    }

    .fifth, .sixth, .seventh{
        background-color: #cceeff;
        color: #808080
    }

    .eight{
        background-color: #ffffff;
        color: #808080
    }

    .response {
        height: 100vh;
        background-color: #cceeff;
        color: #808080
    }
</style>