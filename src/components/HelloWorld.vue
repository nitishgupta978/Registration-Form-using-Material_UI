<template>
  <v-card
    class="mx-auto"
    style="max-width: 800px;"
  >
    <v-system-bar
      color="deep-purple darken-4"
      dark
    >
      <v-spacer></v-spacer>
  
    </v-system-bar>
    <v-toolbar
      color="deep-purple accent-4"
      cards
      dark
      flat
    >
      
      <v-avatar>
      <img
        src="../assets/logo.png"
        alt="image"
        rounded
        size="56"
      ></v-avatar>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn
      class="ma-2"
      :loading="loading4"
      :disabled="loading4"
      color="info"
      @click="loader = 'loading4'"
    >
      Add User
      <template v-slot:loader>
        <span class="custom-loader">
          <v-icon light>mdi-cached</v-icon>
        </span>
      </template>
    </v-btn>

    </v-toolbar>
  
   <v-row justify="center">
    <v-col
      cols="14"
      sm="12"
      md="10"
      lg="8"
    >
      <v-card ref="form">
        <v-card-text>
          <v-text-field
            ref="name"
            v-model="name"
            :rules="[() => !!name || 'This field is required']"
            :error-messages="errorMessages"
            label="Full Name"
            placeholder="John Doe"
            required
          >
          </v-text-field>

             <!-- <v-header justify=" space-around">ProfilePic  </v-header> -->
            <!-- <br> -->
         <v-radio-group row v-model="row" label="ProfilePic">
         <v-radio value="radio-1"></v-radio>
         <v-avatar color="indigo">
          <img src="../assets/Ellipse -01.png"
          alt="john"
          row 
          >
         </v-avatar>

          
         <v-radio value="radio-2"></v-radio>
         <v-avatar color="indigo">
          <img src="../assets/Ellipse -02.png"
          alt="john"
          row 
          >
         </v-avatar>

         
         <v-radio value="radio-3"></v-radio>
         <v-avatar color="indigo">
          <img src="../assets/Ellipse -03.png"
          alt="john"
          row 
          >
         </v-avatar>

         </v-radio-group>

       <v-overflow-btn
      class="my-2"
      :items="items"
      label="Select gender"
      dense
    ></v-overflow-btn>
          <v-header>Departments</v-header>
          <v-checkbox
            v-model="right"
            label="HR"
            hide-details
          ></v-checkbox>

            <v-checkbox
            v-model="right"
            label="Salse"
            hide-details
          ></v-checkbox>

             <v-checkbox
            v-model="right"
            label="CIO"
            hide-details
          ></v-checkbox>

            <v-text-field
            ref="Salary"
            v-model="Salary"
            :rules="[ 'This field is required']"
            label="Salary"
            required
            placeholder="eg.5000"
          ></v-text-field>

          <v-text-field
            ref="note"
            v-model="Note"
            :rules="[() => !!Note || 'This field is required']"
            label="note"
            required
            placeholder="text"
          ></v-text-field>

          
        </v-card-text>
        <v-divider class="mt-12"></v-divider>
        <v-card-actions>
          <v-btn text>
            Cancel
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn
      depressed
      color="wight"
    >
      Refresh
    </v-btn>
          <v-slide-x-reverse-transition>
            <v-tooltip
              v-if="formHasErrors"
              left
            >
              <template v-slot:activator="{ on, attrs }">
                <v-btn
                  icon
                  class="my-0"
                  v-bind="attrs"
                  @click="resetForm"
                  v-on="on"
                >
                  <v-icon>mdi-refresh</v-icon>
                </v-btn>
              </template>
              <span>Refresh form</span>
            </v-tooltip>
          </v-slide-x-reverse-transition>
          <v-btn
            color="primary"
            text
            @click="submit"
          >
            Submit
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
   </v-card>
</template>

<script>
  export default {
    name: 'HelloWorld',

     data: () => ({
      items: ['male', 'female'],
    }),
  }
</script>
