<template>
    <div class="card mb-4">
        <div class="card-header">
            <i class="fa fa-file-signature mr-1"></i>
            Form APP v2
        </div>
        <div class="card-body">
            <form>
                <div class="form-row">
                    <div class="col-md-6">
                        <div class="form-group">
                            <label class="small mb-1" for="inputFirstName"
                                >First Name</label
                            >
                            <input
                                class="form-control py-4"
                                id="inputFirstName"
                                type="text"
                                v-model="firstName"
                                placeholder="Enter first name"
                            />
                        </div>
                    </div>
                    <div class="col-md-6">
                        <div class="form-group">
                            <label class="small mb-1" for="inputLastName"
                                >Last Name</label
                            >
                            <input
                                class="form-control py-4"
                                id="inputLastName"
                                type="text"
                                v-model="lastName"
                                placeholder="Enter last name"
                            />
                        </div>
                    </div>
                </div>
                <div class="form-group mt-4 mb-0">
                    <a class="btn btn-primary btn-block" @click="submit"
                        >Add To List</a
                    >
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    name: "App",
    data() {
        return {
            firstName: "",
            lastName: "",
        };
    },
    methods: {
        submit() {
            const event = new CustomEvent("myEvent", {
                detail: { firstName: this.firstName, lastName: this.lastName },
            });
            window.dispatchEvent(event);
        },
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
