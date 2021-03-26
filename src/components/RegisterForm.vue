<template>
   <div class="form-box">
             <div id="form">
        <ValidationObserver v-slot="{ invalid }">
            <form action="#" method="GET">

                <ValidationProvider v-slot="{ errors }" name="name" rules="required">
                    <legend class="text-center mb-4"> <span id="personalia"> Fill Your Information below </span></legend>

                    <div class="form-floating mb-1">
                        <input id="name" v-model="data.name" class="form-control" placeholder="name" type="text" value="">
                        <label for="name">Name</label>
                    </div>
                    <span class="text-danger fw-bold mt-0 mb-3 d-inline-block">{{ errors[0] }}</span>
                </ValidationProvider>

                <ValidationProvider v-slot="{ errors }" name="Email" rules="required">
                    <div class="form-floating mb-1">
                        <input id="email" v-model="data.email" class="form-control" placeholder="email" type="email" value="">
                        <label for="email">Email</label>
                    </div>
                    <span class="text-danger fw-bold mt-0 mb-3 d-inline-block">{{ errors[0] }}</span>
                </ValidationProvider>


                <ValidationProvider v-slot="{ errors }" name="password" rules="required">
                    <div class="form-floating mb-1">
                        <input id="password" v-model="data.password" class="form-control" placeholder="password" type="password" value="">
                        <label for="password">Password</label>
                    </div>
                    <span class="text-danger fw-bold mt-0 mb-3 d-inline-block">{{ errors[0] }}</span>
                </ValidationProvider>

                 <ValidationProvider v-slot="{ errors }" name="address" rules="required">
                    <div class="form-floating mb-1">
                        <input id="address" v-model="data.address" class="form-control" placeholder="address" type="text" value="">
                        <label for="address">Address</label>
                    </div>
                    <span class="text-danger fw-bold mt-0 mb-3 d-inline-block">{{ errors[0] }}</span>
                </ValidationProvider>

                <ValidationProvider v-slot="{ errors }" name="bio" rules="required">
                    <div class="form-floating mb-1">
                          <textarea
                              id="bio"
                              v-model="data.bio"
                              class="form-control"
                              placeholder=" ... !"
                              style="height: 100px"
                          ></textarea>
                        <label for="bio">Bio</label>
                    </div>
                    <span class="text-danger fw-bold mt-0 mb-3 d-inline-block">{{ errors[0] }}</span>
                </ValidationProvider>

                <ValidationProvider v-slot="{ errors }" name="Gender" >
                          <label for="gender">Gender</label>
                    <select class="form-select my-1" id="gender" v-model="data.gender" >

                        <option value="Male">Male</option>
                        <option value="Female">Female</option>
                    </select>
                    <span class="text-danger fw-bold mt-0 mb-3 d-inline-block">{{ errors[0] }}</span>
                </ValidationProvider>

                 <ValidationProvider v-slot="{ errors }" name="track" >
                    
                    <label for="track">Track</label>
                    <select class="form-select my-1" id="track" v-model="data.track">
                        <option value="Open Source Applications Development">Open Source Applications</option>
                        <option value="System Development">System Development</option>
                        <option value="Embedded Systems">Embedded Systems</option>
                        <option value="Mobile Applications Development">Mobile Applications Development</option>
                    </select>
                    <span class="text-danger fw-bold mt-0 mb-3 d-inline-block">{{ errors[0] }}</span>
                </ValidationProvider>

                <ValidationProvider v-slot="{ errors }" name="Langs" rules="required">
                    <div class="form-floating mb-3">
                        <div v-for="(lang,index) in langs" :key="index" class="form-check form-check-inline">
                            <input :id="'lang-'+index" v-model="data.langs" :value="lang" class="form-check-input" name="langs" type="checkbox">
                            <label :for="'lang-'+index" class="form-check-label">{{ lang }}</label>
                        </div>
                    </div>
                    <span class="text-danger fw-bold mt-0 mb-3 d-inline-block">{{ errors[0] }}</span>
                </ValidationProvider>

            </form>


            {{checkValue(invalid)}}

        </ValidationObserver>

    </div>
   </div>
</template>

<script>
	export default {
		data() {
			return {
				value: "",
				langs: ["Arabic", "English", "German", "Japanese", "Russian","Mandarine"]
			};
		},

		methods: {
			checkValue(val) {
				this.$emit("changeFormStatus", val);
			}
		},
		props: {
			data: {
				required: true,
				type: Object
			}
		}
	};
</script>

<style scoped>
	.form-box {
		border: 1px solid lightgrey;
		padding: 28px;
		border-radius: 8px;
		box-shadow: 4px 2px 4px lightgrey;
		background: #f8f9fa;
		font-size: 14px;
	}
	h3 {
		margin: 40px 0 0;
	}

	ul {
		list-style-type: none;
		padding: 0;
	}

	li {
		display: inline-block;
		margin: 0 10px;
	}

	a {
		color: #42b983;
	}
	span {
		margin: 0;
		font-size: 13px;
	}
	form {
		margin: 0px;
	}
	legend {
		background-color: #202327;
		padding: 15px 10px;
        border-radius: 5px;
	}
	#personalia {
		color: #ffc107;
		font-size: 24px;
	}
</style>
