<template>
    <div class="col-md-6">
        <div class="card">
            <div class="card-header">
                <h3 class="card-title">Daftar Pesanan</h3>
            </div>
            <div class="card-body">
                <div class="table-responsive">
                    <table class="table table-hover table-bordered">
                        <thead>
                            <tr>
                                <th>No</th>
                                <th>Nama</th>
                                <th>Makanan</th>
                                <th>Minuman</th>
                                
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="(row, index) in agenda" :key="index">
                                <td>{{ index+1 }}</td>
                                <td>{{ row.nama }}</td>
                                <td>{{ row.makanan }}</td>
                                <td>{{ row.minuman }}</td>
                                
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'AgendaShow',
        computed: {
            agenda(){
                return this.$store.state.listAgenda
            }
        }
    }
</script>