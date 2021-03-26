<template>
    <div class="row">
        <table class="table table-striped col-12">
            <thead>
                <tr>
                    <th>#</th>
                    <th>Name</th>
                    <th>City</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for ="student in students" : key="student.id" >
                    <td> {{student.id}} </td>
                    <td> {{student.name}} </td>
                    <td> {{student.city}} </td>
                </tr>
            </tbody>
            <tfoot>
                <h5 class="alert alert-info"> {{message}} : {{students.length}} </h5>
            </tfoot>


        </table>
    </div>
</template>

<script>
import students from '../students.js'
export default {
    data(){
        return {
            message: 'Total Number of Students is',
            students:students        }
    }
}
</script>