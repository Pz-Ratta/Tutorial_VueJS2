<template>
    <form @submit.prevent="submitForm">
        <div class="form-control">
           <label for="emp-name">ชื่อพนักงาน: </label> 
           <input v-model.trim="employee.name"/>
        </div>
        <div class="form-control">
           <label for="emp-salary">เงินเดือน: </label> 
           <input type="number" v-model="employee.salary"/>
        </div>
        <div class="form-control">
           <label for="emp-department">ตำแหน่งงาน: </label>
           <select v-model="employee.department">
            <option value="ฝ่ายการตลาด">ฝ่ายการตลาด</option>
            <option value="ฝ่ายการเงิน">ฝ่ายการเงิน</option>
            <option value="โปรแกรมเมอร์">โปรแกรมเมอร์</option>
           </select>
        </div>
        <div class="form-control">
            <h2>เพศ:</h2>
            <div>
                <input type="radio" id="gender-m" value="ชาย" v-model="employee.gender" />
                <label for="gender-m">ชาย</label>
                <input type="radio" id="gender-w" value="หญิง" v-model="employee.gender" />
                <label for="gender-w">หญิง</label>
            </div>
        </div>
        <div class="form-control">
            <h2>ทักษะ-ภาษา:</h2>
            <div>
                <input type="checkbox" value="ภาษาอังกฤษ" v-model="employee.skill" />
                <label for="skill">ภาษาอังกฤษ</label>
                <input type="checkbox" value="ภาษาจีน" v-model="employee.skill" />
                <label for="skill">ภาษาจีน</label>
                <input type="checkbox" value="ภาษาญี่ปุ่น" v-model="employee.skill" />
                <label for="skill">ภาษาญี่ปุ่น</label>
            </div>
        </div>
        <div>
            <button>บันทึกข้อมูล</button>
        </div>
    </form>
</template>
<script>
export default{
    name: 'FormComponent',
    data(){
        return{
            employee:{
                name: "",
                salary: 0,
                department: "",
                gender: "",
                skill: []
            }
        }
    },
    methods: {
        submitForm() {
            const newEmp = {
                name: this.employee.name,
                salary: this.employee.salary,
                department: this.employee.department,
                gender: this.employee.gender,
                skill: this.employee.skill
            }
            this.$emit("save", newEmp);
        }
    }
}
</script>
<style scoped>
form{
    margin: 2rem auto;
    max-width: 40rem;
    border-radius: 12px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.25);
    padding: 2rem;
    background: white;
}
.form-control{
    margin: 0.5rem 0;
}
label{
    font-weight: bold;
}
input, select{
    display: block;
    width: 100%;
    font: inherit;
    margin-top: 0.5rem;
}
button{
    font: inherit;
    background: orangered;
    color: white;
    cursor: pointer;
    padding: 0.75rem 2rem;
    border-radius: 15px;
}
input[type="radio"], input[type="checkbox"] 
{
    display: inline-block;
    width: auto;
    margin-right: 1rem;
}
input[type="radio"]+label, input[type="checkbox"]+label 
{
    font-weight: normal;
}
h2{
    font-size: 1rem;
    margin: 0.5rem 0;
}
</style>
