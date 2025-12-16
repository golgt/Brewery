<template>
    <v-row align="center" justify="center" dense>
      <v-col cols="12" md="6">
        <v-card
          
          class="mx-auto"
          prepend-icon="mdi-account"
          title="Autor"
        >
          <v-card-text>Martin Ovcarčík</v-card-text>
        </v-card>
      </v-col>
  
      <v-col cols="12" md="6">
        <v-card
          class="mx-auto"
          title="Mail"
        >
          <template v-slot:prepend>
            <v-icon color="primary" icon="mdi-pencil"></v-icon>
          </template>
          <v-card-text>martin.ovcarcik@student.ukf.sk</v-card-text>
        </v-card>
      </v-col>
  
      <v-col cols="12" md="6">
        <v-card
          prepend-icon="mdi-alert-circle"
          subtitle="!! IMPORTANT !!"
          title="INFO O OBRÁZKOCH"
        >
          <v-card-text>Všetky obrázky sú voľne dostupné alebo AI generated.</v-card-text>
        </v-card>
      </v-col>
  
      <v-col cols="12" md="6">
        <v-card
          class="mx-auto"
          subtitle="Žiadna reklama"
          title="POZOR"
        >
          <template v-slot:prepend>
            <v-avatar color="blue-darken-2">
              <v-icon icon="mdi-alert"></v-icon>
            </v-avatar>
        
          </template>
          <v-card-text>Všetko čo sa nachádza na tejto stránke je vymyslené.</v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </template>