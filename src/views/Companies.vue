<template>
    <div>
        <base-header type="gradient-success" class="pb-6 pb-8 pt-5 pt-md-8">
            <!-- Card stats -->
            <router-link to="/create/company" class="text-light">   <h1>Create Company Profile</h1></router-link>
        </base-header>

        <div class="container-fluid mt--7">
            <div class="row">
                <div class="col">
                        <projects-table title="List of Companies"></projects-table>
                </div>
            </div>
        </div>
        <br>
        <br>
        <br>
        <br>
    </div>

</template>
<script>
  import ProjectsTable from './Tables/ProjectsTable'
  export default {
    name: 'tables',
    components: {
      ProjectsTable
    }
  };
</script>
<style></style>
