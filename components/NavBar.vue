
<template>
    <div>
        <b-navbar toggleable="sm" type="light" variant="light">
            <b-navbar-toggle target="nav-text-collapse"></b-navbar-toggle>

            <b-navbar-brand href="/">
                <img src="https://seeklogo.com/images/A/aws-ec2-elastic-compute-cloud-logo-2F9E73DBA5-seeklogo.com.png" class="d-inline-block align-top" width="30px;" alt="">
                BorrowUsBooks
            </b-navbar-brand>
            
            <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav class="ml-auto">
                    <template v-if="$auth.loggedIn">
                        <b-nav-item href="/">Home</b-nav-item>
                        <b-nav-item href="/dashboard">Dashboard</b-nav-item>
                        <b-nav-item href="/borrowedbooks">Borrowed Books</b-nav-item>
                        <b-nav-item href="#" @click.prevent="onLogout">Logout</b-nav-item>
                    </template>

                    <template v-else>
                        <b-nav-item href="/">Home</b-nav-item>
                    </template>
                </b-navbar-nav>
                
            </b-collapse>
        </b-navbar>
    </div>
</template>

<script>
export default {
    methods: {
        async onLogout() {
            this.$auth.logout()
        }
    }
}
</script>
