<template>
    <div>
        <NavBar />
        <EditBorrowedbookModal :borrowedbook="selectedBorrowedbook" />
        <DeleteBorrwedbookModal :borrowedbook="selectedBorrowedbook" @onDeleted="getAll"/>
        <div class="container">
            <h1>
                Borrowed Books
                <BorrowedbookEntryModal class="float-right" @onAdd="getAll"/>
            </h1>

            <table class="table table-hover">
                <thead>
                    <tr class="bg-info text-white">
                        <th>Book Title</th>
                        <th>Genre</th>
                        <th>Author</th>
                        <th>&nbsp;</th>
                        <th>&nbsp;</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="borrowedbook in borrowedbooks" :key="borrowedbook.id">
                        <td>{{borrowedbook.book}}</td>
                        <td>{{borrowedbook.genre}}</td>
                        <td>{{borrowedbook.author}}</td>
                        <td>
                            <b-button @click="onEdit(borrowedbook)" variant="info" size="sm">
                                Edit
                            </b-button>
                        </td>
                        <td>
                            <b-button @click="onDelete(borrowedbook)" variant="danger" size="sm">
                                Delete
                            </b-button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
<Footer />
    </div>
</template>

<script>
export default {
    
    data() {
        return {
            borrowedbooks: [],
            selectedBorrowedbook: {}
        }
    },
    methods: {
        async getAll() {
            await this.$axios.get('https://lentrix.tk/matarlo/api/borrowedbooks')
            .then((res)=>{
                if(res.status==200) {
                    this.borrowedbooks =res.data
                }
            })
        },
        onEdit(selectedBorrowedbook) {
            this.selectedBorrowedbook = selectedBorrowedbook;
            this.$bvModal.show('editBorrowedbookModal')
        },
        onDelete(selectedBorrowedbook) {
            this.selectedBorrowedbook = selectedBorrowedbook;
            this.$bvModal.show('deleteBorrowedbookModal')
        }
    },
    created() {
        this.getAll()
    }
}
</script>