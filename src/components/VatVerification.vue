<template>
    <div class="vat-verification">
        <div class="vat-box">
            
            <div>Enter Country Code</div>
            <input v-model="countryCode" type="text" >

            <div>Enter VAT ID</div>
            <input v-model="vatId" type="text" >

        </div>
        <button class="submit_btn" @click="submit">Submit</button>
        <p>{{resultText}}</p>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    props: ['post'],
    data() 
    {
        return {
            countryCode : "",
            vatId : "",
            resultText : ""
        }

    },
    methods:{
        async submit(){
            this.resultText = "Please wait..."

            if(!this.countryCode || !this.vatId)  {
                this.resultText = "Please fill out both fields";
                return;
            }

            var resp;
            await axios.get(`https://localhost:7138/api/Invoices/VatVerification/${this.countryCode}/${this.vatId}`)
            .then(response => {
                resp = response.data
            })

            if(resp == 0) this.resultText = "Vat ID Valid";
            if(resp == 1) this.resultText = "Vat ID Invalid";
            if(resp == 2) this.resultText = "Could not verify Vat Id, make sure the correct information was entered or try again later";
        }
    }
}

</script>