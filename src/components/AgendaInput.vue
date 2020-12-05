<template>
    <div class="col-md-6">
        <div class="card">
            <div class="card-header">
                <h3 class="card-title">List Pesanan</h3>
            </div>
            <div class="card-body">
                <div class="form-group">
                    <label for="">Nama</label>
                    <input type="text" v-model="agenda.nama" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="">Makanan</label>
                    <input type="text" v-model="agenda.makanan" class="form-control" required>
                </div>
                <div class="form-group">
                    <label for="">Minuman</label>
                    <input type="text" v-model="agenda.minuman" class="form-control" required>
                </div>
                <div class="form-group">
                    <button class="btn btn-danger btn-sm" :disabled="isLoading" @click.prevent="simpan">{{ isLoading ? 'Loading...':'Tambahkan' }}</button>
                </div>    
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'AgendaInput',
    data(){
        return {
            agenda: {
                nama: '',
                makanan: '',
                minuman: ''
            }
        }
    },
    methods: {
        simpan(){
            this.$store.dispatch('simpanAgenda', this.agenda)
            this.agenda = {
                nama: '',
                makanan: '',
                minuman: ''
            }
        }
    },
    computed: {
        isLoading(){
            return this.$store.state.isLoading
        }
    }
}
</script>