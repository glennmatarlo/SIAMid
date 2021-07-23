<template>
    <div>

        <b-button v-b-modal.borrowedbookEntryModal variant="primary " >Add Borrowed Book</b-button>
        <b-modal id="borrowedbookEntryModal" title="Book Borrowed Entry" ok-title="Save Book" @ok="onSubmit">
           <form action="#" >
                <b-form-group 
                label="Book"
                label-for="book"
                >
                <b-form-input id="book" v-model="borrowedbook.book"  trim></b-form-input>
                </b-form-group>

                 <b-form-group
                label="Genre"
                label-for="Genre"
                >
                <b-form-input id="Genre" v-model="borrowedbook.genre"  trim></b-form-input>
                </b-form-group>

                 <b-form-group
                label="Author"
                label-for="Author"
                >
                <b-form-input id="Author" v-model="borrowedbook.author"  trim></b-form-input>
                </b-form-group>
           </form>

        </b-modal>
    </div>
</template>

<script>
export default {
    data() {
        return{
            borrowedbook:{},
        }
    },
    methods:{
        async onSubmit() {
            this.$axios.post('https://lentrix.tk/matarlo/api/borrowedbooks', this.borrowedbook)
            .then((res)=>{
                if(res.status==202) {
                    alert('Successfully added in the list')
                    this.$emit('onAdd')
                }
            })
        }
    }
}
</script>