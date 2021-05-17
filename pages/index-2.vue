<template>
    <div id="container">
        <h1>Keemko</h1>
        <h4>First Name</h4>
         <input id='inputA' v-model='firstName' type="Text">
        <h4>Last Name</h4>
        <input id='inputB' v-model='lastName' type="Text">
        <br>
        <input id='submit' @click='submitTEXT(firstName, lastName)' type="submit">
        <div id="display">{{submitData}}</div>
    </div>
    
</template>

<style>
#container {
    margin-left: 20px;
}
#inputA {
    margin-left: 1px;
    border-style:solid; 
    border-width: 1px;
    border-color: black;
    height: 25px;
    width: 200px;
}
#inputB {
    margin-left: 1px;
    border-style:solid; 
    border-width: 1px;
    border-color: black;
    height: 25px;
    width: 200px;
}
#submit {
    border-style:solid;
    border-color:black;
    border-width:1px;
    margin-top: 5px;
}
#display {
    margin-left: 1px;
    border-style:solid; 
    border-width: 1px;
    border-color: black;
    height: 45px;
    width: 200px;
    margin-top: 5px;
}

</style>

<script>
export default {
    data() {
        return {
            firstName: '',
            lastName: '',
            submitData: ''
            
        }
    },
    methods: {
        submitTEXT(inputA, inputB) {
            this.submitData = this.concatStr(inputA, inputB)
            this.clearInput()
        },
        concatStr(strA, strB) {
            return strA + ' ' + strB;
        },
        clearInput() {
            this.firstName = '',
            this.lastName = ''
            
        }
    }
}
</script>