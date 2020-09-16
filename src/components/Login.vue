<template>
  <div id="popup">
    <v-card id="logincard" style="display:block" class="mx-auto" max-width="344">
      <v-list-item three-line>
        <v-list-item-content>
          <v-form v-model="valid">
            <v-container>
              <v-text-field
                v-model="username"
                :rules="userRules"
                :counter="18"
                label="Username"
                maxlength="18"
                required
              ></v-text-field>
              <v-text-field
                v-model="password"
                :rules="userRules"
                :counter="36"
                label="Password"
                type="password"
                maxlength="36"
                required
              ></v-text-field>
            </v-container>
          </v-form>
        </v-list-item-content>

        <v-list-item-avatar tile size="80" color="grey"></v-list-item-avatar>
      </v-list-item>

      <v-card-actions>
        <v-btn text>Login</v-btn>
        <v-btn @click="dialog = true" id="btn-register" text>Register</v-btn>
      </v-card-actions>
    </v-card>

    <div id="btn-regis">
    <v-row justify="center">
      <v-dialog v-model="dialog" persistent max-width="600px">
        <!-- <template v-slot:activator="{ on, attrs }">
        <v-btn
          color="primary"
          dark
          v-bind="attrs"
          v-on="on"
        >
          Open Dialog
        </v-btn>
        </template>-->
        <v-card>
          <v-card-title>
            <span class="headline">User Profile</span>
          </v-card-title>
          <v-card-text>
            <v-container>
              <v-row>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field label="Legal first name*" required></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Legal middle name"
                    hint="example of helper text only on focus"
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="6" md="4">
                  <v-text-field
                    label="Legal last name*"
                    hint="example of persistent helper text"
                    persistent-hint
                    required
                  ></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-text-field label="Email*" required></v-text-field>
                </v-col>
                <v-col cols="12">
                  <v-text-field label="Password*" type="password" required></v-text-field>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-select :items="['0-17', '18-29', '30-54', '54+']" label="Age*" required></v-select>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-autocomplete
                    :items="['Skiing', 'Ice hockey', 'Soccer', 'Basketball', 'Hockey', 'Reading', 'Writing', 'Coding', 'Basejump']"
                    label="Interests"
                    multiple
                  ></v-autocomplete>
                </v-col>
              </v-row>
            </v-container>
            <small>*indicates required field</small>
          </v-card-text>
          <v-card-actions>
            <v-spacer></v-spacer>
            <v-btn color="blue darken-1" text @click="dialog = false">Close</v-btn>
            <v-btn color="blue darken-1" text @click="dialog = false">Save</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </v-row>
    </div>
  </div>
  
</template>

<script>
export default {
  data: () => ({
    name: "login",
    valid: false,
    username: "",
    password: "",
    dialog: false,
    userRules: [
      //   (vRec) => vRec || "Name is required",
      //   (vRec) => vRec.length <= 6 || "Name must be less than 6 characters",
    ],
  }),
};
</script>

<style>
#popup {
  /* position: fixed; */
  position: fixed;
  top: 0;
  right: 10px;
  margin-top: 65px;
}
</style>