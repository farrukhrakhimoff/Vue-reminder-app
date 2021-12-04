<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label for="def-reminder">Reminder</label>
            <input type="text" v-model="text" name="text" id="def-reminder" placeholder="Add the task">
        </div>

        <div class="form-control">
            <label for="def-day">Time & day</label>
            <input type="text" v-model="day" name="day" id="def-day" placeholder="Add month & day">
        </div>

        <div class="form-control form-control-check">
            <label>Cancel</label>
            <input type="checkbox" v-model="reminder" value="Reminder">
        </div><br>
        <input type="submit" value="Save Task" class="btn btn-block btn-secondary">
            
    </form>
</template>

<script>
export default {
    name : 'AddTask',
    data() {
        return {
            text : '',
            day : '',
            reminder : false
        }
    },
    methods : {
        onSubmit(e) {
            e.preventDefault()

            if(!this.text) {
                alert("Please, add reminder!")
                return
            }
            const newTask = {
                id: Math.floor(Math.random() * 1000000),
                this: this.text,
                day : this.day,
                reminder : this.reminder
            }
            console.log(newTask);
            this.$emit('add-task', newTask )

            this.text = ''
            this.day = ''
            this.reminder = false
        }
    }
}
</script>

<style scoped>
     .add-form {
         margin-bottom: 4rem;
     }
     .form-control {
         margin: 2rem 0;
     }
     .form-control label {
         display: block;
     }
     .form-control input {
         width: 100%;
         height: 4rem;
         margin: 5px;
         padding: 3px 7px;
         font-size: 17px;
     }
     .form-control-check {
         display: flex;
         align-items: center;
         justify-content: space-between;
     }
     .form-control-check label {
         flex: 1;
     }
     .form-control input {
         flex: 2;
         height: 2rem;
     }
     input::placeholder {
         font-size: .8rem;
     }
</style>