<script setup>
import ConnectionForm from './forms/ConnectionForm.vue'
import ModbusGroupForm from './forms/ModbusGroupForm.vue'
import RegDataList from './RegDataList.vue'
</script>

<template>
    <div>

      <div class="container-fluid">
    <div class="row">
        <!-- Sidebar -->
        <nav class="col-lg-3 d-none d-md-block bg-light sidebar border">
            <div class="sidebar-sticky">
                <!-- Add your sidebar content here -->
                <h5>Configuration</h5>
                <ul class="nav flex-column">
                   
                    <!-- Add more sidebar links as needed -->
                    <connection-form />
      <modbus-group-form />
                </ul>
            </div>
        </nav>

        <!-- Main Content -->
        <main role="main" class="col-lg-9 ml-sm-auto">
            <!-- Add your main content here -->
            <reg-data-list />
        </main>
    </div>
</div>

      
      
    </div>
  
</template>


<style scoped>
 .sidebar {
      height: 100vh;
      background-color: #f8f9fa; /* Set your desired background color */
    }
</style>
