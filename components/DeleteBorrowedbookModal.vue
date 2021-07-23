<template>
    <div>
        <b-modal id="deleteBorrowedbookModal" title="Books Borrowed Entry" ok-title="Delete Borrowed Book" @ok="onDelete" ok-variant="danger">
            Are you sure you want to delete this book? <br>
        </b-modal>
    </div>
</template>
<script>
export default {
  props:{
      borrowedbook:{}
  },
  methods:{
        async onDelete() {
            this.$axios.delete('https://lentrix.tk/matarlo/api/borrowedbooks/' + this.borrowedbook.id)
            .then((res)=>{
                if(res.status==202) {
                    alert('Borrowed Book deleted')
                    this.$emit('onDeleted')
                }
            })
        }
    }
}
</script>