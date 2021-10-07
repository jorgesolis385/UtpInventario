<template>  
<div class="card">
    <div class="card-header">
        <h3 class="card-title">Lista de Elementos</h3>
    </div>
    <div class="card-body">
                <div id="example1_wrapper" class="dataTables_wrapper dt-bootstrap4">
                  <div class="row"><div class="col-sm-12 col-md-6">
                        <div class="dt-buttons btn-group flex-wrap">                              
                         <router-link to="/form" class="btn btn-secondary buttons-copy buttons-html5">Crear</router-link>
                        </div>
                    </div>
                  <div class="col-sm-12 col-md-6"><div id="example1_filter" class="dataTables_filter">
                      
                    </div></div></div><div class="row"><div class="col-sm-12">
                  <table id="example1" class="table table-bordered table-striped dataTable dtr-inline" role="grid" aria-describedby="example1_info">
                  <thead>
                  <tr role="row"><th class="sorting sorting_asc" tabindex="0" aria-controls="example1" rowspan="1" colspan="1" aria-sort="ascending" aria-label="Rendering engine: activate to sort column descending">Id</th>
                    <th class="sorting" tabindex="0" aria-controls="example1" rowspan="1" colspan="1" aria-label="Browser: activate to sort column ascending">Nombre Articulo</th>
                    <th class="sorting" tabindex="0" aria-controls="example1" rowspan="1" colspan="1" aria-label="Platform(s): activate to sort column ascending">Cantidad</th>
                    <th class="sorting" tabindex="0" aria-controls="example1" rowspan="1" colspan="1" aria-label="Engine version: activate to sort column ascending">Estado</th>
                    <th class="sorting" tabindex="0" aria-controls="example1" rowspan="1" colspan="1" aria-label="CSS grade: activate to sort column ascending">Fecha Ingreso</th>
                    <th class="sorting" tabindex="0" aria-controls="example1" rowspan="1" colspan="1" aria-label="CSS grade: activate to sort column ascending">Acciones</th>
                    </tr>
                  </thead>
                  <tbody>
                  <tr class="odd" v-for="item in items" :key="item.id">
                    <td class="dtr-control sorting_1" tabindex="0"> {{item.id}}</td>
                    <td>{{item.nombre}}</td>
                    <td>{{item.cantidad}}</td>
                    <td>{{item.estado}}</td>
                    <td>{{item.fecha_creacion}}</td>
                    <td>
                        <div class="btn-group">
                            <button type="button" class="btn btn-default btn-flat">
                                <i class="far fa-edit"></i>
                            </button>
                            <button type="button" v-on:click="eliminar(item.id)" class="btn btn-default btn-flat">
                               <i class="far fa-trash-alt"></i>
                            </button>
                            <button type="button" class="btn btn-default btn-flat">
                                  <i class="fas fa-truck-loading"></i>
                            </button>
                        </div>
                    </td>
                  </tr>
                  
                  </tbody>
                  <tfoot>
                  <tr><th rowspan="1" colspan="1">Id</th><th rowspan="1" colspan="1">Nombre Articulo</th><th rowspan="1" colspan="1">Cantidad</th><th rowspan="1" colspan="1">Fecha Ingreso</th><th rowspan="1" colspan="1">Estado</th>
                  <th class="sorting" tabindex="0" aria-controls="example1" rowspan="1" colspan="1" aria-label="CSS grade: activate to sort column ascending">Acciones</th>
                  </tr>
                  </tfoot>
                </table></div></div></div>
              </div>
              <!-- /.card-body -->
</div>
    
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      items: [{}]
    }
  },
  created() {
    axios.get("http://localhost:3000/articulos?").then((result) => {
        this.items=result.data;
      console.log(this.items);
    })
  },
   methods: {
    eliminar: function (id) {   
      console.log(id);
      axios.delete("http://localhost:3000/articulos/"+id).then((result) => {
         console.log(result);
    }).catch(e => {
            console.log(e);
        });
       
    }
  }
};
</script>

