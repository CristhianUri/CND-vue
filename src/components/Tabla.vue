<template v-if="">
    <div class="contianer">
        <div class="row">
            <div class="col-xs-12">
                <table class="table table-stripped">
                    <thead>
                        <tr>
                            <th style="width:40px;"></th>
                            <th>Descripcion</th>
                            <th style="width:200px;">Monto</th>
                            <th style="width:100px;">¿Cancelado?</th>

                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td></td>
                            <td>
                                <input type="text" class="form-control" >
                            </td>
                            <td>
                                <input type="text" class="form-control" >
                            </td>
                            <td>
                                <button @click="add()" type="button" class="btn btn-success btn-block">Agregar</button>
                            </td>
                         </tr>
                        <tr  v-if="namesArray.length===0">
                            <td colspan="4" class="text-center">No hay registros por mostrar</td>
                         </tr>
                        <tr  v-for="(skill, index) in namesArray">
                           <td>
                          
                            <button   @click="remove(index)" 
                            type="button" class="btn btn-danger btn-xs">
                                <i class="bi bi-trash"></i>
                            </button>
                           </td>

                           <td>{{ namesArray[index].name }}</td>
                            <td>{{ namesArray[index].amount }}</td>
                            <td class="text-center" :title="namesArray[index].paid ? 'si' : 'no'"><button class="btn btn-default btn-sm" :class="{'btn-success':namesArray[index].paid}">
                                <i v-if="namesArray[index].paid " class="bi bi-check2"></i>
                                <i v-if="!namesArray[index].paid " class="bi bi-x"></i>
                                </button>
                            </td>
                        </tr>
                    </tbody>
                </table>
                
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ["names-array", "index"],
        methods:{
            remove(index){
                this.namesArray.splice(index,1) 
                
            },
            
         }
    }
    
</script>