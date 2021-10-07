<template>
    <div class="card card-default">
          <div class="card-header">
            <h3 class="card-title">Alquiler Articulo</h3>

            <div class="card-tools">
              <button type="button" class="btn btn-tool" data-card-widget="collapse">
                <i class="fas fa-minus"></i>
              </button>
              <button type="button" class="btn btn-tool" data-card-widget="remove">
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
          <!-- /.card-header -->
          <div class="card-body">
            <div class="row">
              <div class="col-md-6">
                <div class="form-group">
                  <label>ID Articulo</label>
                     <input type="text" class="form-control">
                </div>
                <!-- /.form-group -->
                <div class="form-group">
                  <label>Cantidad</label>
                   <input type="text" class="form-control">
                </div>
                <!-- /.form-group -->
              </div>
              <!-- /.col -->
              <div class="col-md-6">
                <div class="form-group">
                  <label>Nombre Articulo</label>
                   <input type="text" class="form-control">
                </div>
                <!-- /.form-group -->
                <div class="form-group">
                  <label>Estados</label>
                  <div class="form-group clearfix">
                      <div class="icheck-success d-inline">
                        <input type="radio" name="estado" checked="" id="radioSuccess1">
                        <label for="radioSuccess1">
                            Nuevo
                        </label>
                      </div>
                      <div class="icheck-danger d-inline">
                        <input type="radio" name="estado" checked="" id="radioDanger1">
                        <label for="radioDanger1">
                             Usado
                        </label>
                      </div>                                 
                    </div>
                </div>
                <!-- /.form-group -->
              </div>
              <!-- /.col -->
            </div>
            <!-- /.row -->
             <div class="row">
                <div class="col-md-6">
                    <button type="button" class="btn btn-block btn-primary">Crear Articulo</button>
                </div>
                <div class="col-md-6">
                    <button type="button" class="btn btn-block btn-default">Limpiar</button>
                </div>
             </div>    
          </div>
          <!-- /.card-body -->
          <div class="card-footer">
           
          </div>
        </div>
</template>

<script>
export default {

}
</script>

<style>

</style>