<template>
  <div class="col-8">
    <div class="links-container">
      <table class="table table-striped">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Name</th>
            <th scope="col">City</th>
            <th scope="col">Email</th>
            <th scope="col">Hobby</th>
            <th scope="col">Action</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="student in students" :key="student.id">
            <td>{{ student.id }}</td>
            <td>{{ student.name }}</td>
            <td>{{ student.city }}</td>
            <td>{{ student.email }}</td>
            <td>{{ student.hobby }}</td>
            <td>
              <button @click="deletestudent(student)" class="btn btn-danger">
                Delete This Row
              </button>
            </td>
          </tr>
          <tr>
            <td @click="addnew" class="text-center" colspan="5">
              <button type="button" class="btn btn-info col-12">
                Add New Student
              </button>
            </td>
          </tr>
        </tbody>
        <tfoot>
          <tr>
            <td class="text-center" colspan="5">
              <h4>{{ message }} : {{ students.length }}</h4>
            </td>
          </tr>
        </tfoot>
      </table>
    </div>
  </div>
</template>

<script>
import students from "../students";
console.log(students);
export default {
  data() {
    return {
      message: "Total Number of Students is",
      students: students,
    };
  },
  methods: {
    addnew() {
      let student_name = prompt("Please enter student's name");
      let student_email = prompt("Please enter student's email");
      let student_city = prompt("Please enter student's city");
      let student_hobby = prompt("Please enter student's hobby");
      this.students.push({
        id: this.students.length + 100,
        name: student_name,
        email: student_email,
        city: student_city,
        hobby: student_hobby,
      });
    },
    deletestudent(student) {
        for (let i = 0; i < this.students.length; i++) {
          if (this.students[i].id == student.id) {
            this.students.splice(i, 1);
            break;
          }
        }      
    },
  },
};
</script>
