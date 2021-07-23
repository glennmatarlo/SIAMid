<template>
    <div>

        <b-modal id="editBorrowedbookModal" title="Borrowed Book Entry" ok-title="Save Borrowed Book" @ok="onSubmit">
           <form action="#" >
                <b-form-group 
                label="Book"
                label-for="book"
                >
                <b-form-input id="book" v-model="borrowedbook.book"  trim></b-form-input>
                </b-form-group>

                 <b-form-group
                label="Genre"
                label-for="genre"
                >
                <b-form-input id="genre" v-model="borrowedbook.genre"  trim></b-form-input>
                </b-form-group>

                 <b-form-group
                label="Author"
                label-for="author"
                >
                <b-form-input id="author" v-model="borrowedbook.author"  trim></b-form-input>
                </b-form-group>
           </form>

        </b-modal>
    </div>
</template>

<script>
export default {
  props:{
      borrowedbook:{}
  },
   data() {
        return{
            borrowedbook:{},       
        }
    },
  methods:{
        async onSubmit() {
            this.$axios.put('https://lentrix.tk/matarlo/api/borrowedbooks/' + this.borrowedbook.id, this.borrowedbook)
            .then((res)=>{
                if(res.status==202) {
                    alert('Updated Successfully!!!')
                }
            })
            .catch((err)=> {
                alert(err.message)
            })
        }
    }
}
</script>