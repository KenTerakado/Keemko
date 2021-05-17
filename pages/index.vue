<template>
    <form>
        <div id="container">
            <label id='header'>Keemko</label>
            <br>
            <label>First Name:</label>
            <input id='inputA' v-model='firstName' type="Text">
            <br>
            <label>Last Name:</label>
            <input id='inputB' v-model='lastName' type="Text">
            <br>
            <label>Age:</label>
            <input id='inputC' v-model='age' type="Text">
            <br>
            <label>Height (cm):</label>
            <input id='inputD' v-model='height' type="Text">
            <br>
            <label>Weight (kgs):</label>
            <input id='inputE' v-model='weight' type="Text">
            <br>
            <label id='Sex'>Gender:</label>
            <input type="radio" id="male" name="gender" value="male">
                <label for="male">Male</label><br>
            <input type="radio" id="female" name="gender" value="female">
                <label for="female">Female</label><br>
            <input type="radio" id="other" name="gender" value="other">
                <label for="other">Other</label>
            <br>
            
            <input id='submit' @click='submitTEXT(firstName, lastName, age, height, weight)' type="submit">
            <table id='table' width= 75% border='1'>
                    <tr>
                        <th>Name</th>
                        <th>Age</th>
                        <th>Height</th>
                        <th>Weight</th>
                        <th>Gender</th>
                    </tr>
                    <tr>
                        <th><div id='displayName'>{{ fullName }}</div></th>
                        <th><div id='displayAge'>{{age}}</div></th>
                        <th><div id='displayHeight'>{{height}}</div></th>
                        <th><div id='displayWeight'>{{weight}}</div></th>
                        <th><div id='displayGender'>{{gender}}</div></th>
                    
                    </tr>
                </table>
        </div>
    </form>
</template>

<style>
#male {
    margin-left: 169px;
}

#female {
    margin-left: 228px;
}

#other {
    margin-left: 228px;
}

#header {
    font-size: 32px;

}

#container {
    margin-left: 20px;
}

#inputA {
    margin-left: 12px;
    margin-bottom: 4px;
    border-style:solid; 
    border-width: 1px;
    border-color: black;
    height: 25px;
    width: 200px;
}

#inputB {
    margin-left: 13px;
    margin-bottom: 4px;
    border-style:solid; 
    border-width: 1px;
    border-color: black;
    height: 25px;
    width: 200px;
}

#inputC {
    margin-left: 62px;
    margin-bottom: 4px;
    border-style:solid; 
    border-width: 1px;
    border-color: black;
    height: 25px;
    width: 200px;
}

#inputD {
    margin-left: 6px;
    margin-bottom: 4px;
    border-style:solid; 
    border-width: 1px;
    border-color: black;
    height: 25px;
    width: 200px;
}

#inputE {
    margin-left: 1px;
    margin-bottom: 4px;
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
    margin-left: 245px;
    margin-top: 5px;
}
#displayName, #displayAge, #displayHeight, #displayWeight, #displayGender {
    margin-left: 1px; 
    border-width: 1px;
    height: 35px;
    width: 200px;
    margin-top: 5px;
    margin-bottom: 5px;
}

#table, th, td {
    margin-top: 5px;
    border: 1px solid black;
}

</style>

<script>
export default {
    data() {
        return {
            firstName: '',
            lastName: '',
            fullName: '',
            height: '',
            weight: '',
            age: '',
            gender: ''
            
        }
    },
    methods: {
        submitTEXT(inputA, inputB, inputC, inputD, inputE) {
            this.fullName = this.concatStr(inputA, inputB)
            this.age = this.submitAge()
            this.height = this.submitHeight()
            this.weight = this.submitWeight()
            this.clearInput()
        },
        
        submitAge(strC) {
            return strC;
        },

        submitHeight(strD) {
            return strD;
        },

        submitWeight(strE) {
            return strE;
        },

        concatStr(strA, strB) {
            return strA + ' ' + strB;
        },
        clearInput() {
            this.firstName = '',
            this.lastName = '',
            this.height = '',
            this.weight = '',
            this.age = ''
        }

    }
}
</script>