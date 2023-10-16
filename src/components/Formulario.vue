<template>
  <v-form v-model="valid">
    <v-container>
      <v-row>
        <v-col cols="12" md="1">
          <v-text-field  clearable v-model="veiculo" :rules="nameRules" :counter="10" label="Veículo" placeholder="Ex:Palio" required
            hide-details></v-text-field>
        </v-col>

        <v-col cols="12" md="2">
          <v-text-field  clearable v-model="placa" :rules="nameRules" :counter="10" label="Placa" placeholder="ABC-1234" hide-details
            required></v-text-field>
        </v-col>

        <v-col cols="12" md="2">
          <v-text-field  clearable v-model="seguradora" :rules="nameRules" :counter="10" label="Seguradora" placeholder="Ex:Allianz"
            hide-details required></v-text-field>
        </v-col>

        <v-col cols="12" md="2">
          <v-text-field  clearable v-model="data" :rules="dataRules" label="Data" type="date" hide-details required></v-text-field>
        </v-col>

        <v-col cols="12" md="1">
          <v-text-field  clearable v-model="moini" label="M.O Inicial" required
            hide-details></v-text-field>
        </v-col>

        <v-col cols="12" md="1">
          <v-text-field  clearable v-model="mofin" label="M.O Final" required
            hide-details></v-text-field>
        </v-col>

        <v-col cols="12" md="1">
          <v-text-field  clearable v-model="mototal" label="Valor Total" required
            hide-details></v-text-field>
        </v-col>

        <v-col cols="auto">
          <v-btn color="green" size="x-large">
            adicionar
          </v-btn>
        </v-col>

      </v-row>
    </v-container>
  </v-form>
</template>
<script>
export default {
  data: () => ({
    valid: false,
    veiculo: '',
    placa: '',
    nameRules: [
      value => {
        if (value) return true

        return 'Preenchimento obrigatório'
      },
      value => {
        if (value?.length <= 10) return true

        return 'Name must be less than 10 characters.'
      },
    ],
    data: '',
    dataRules: [
      value => {
        if (value) {
          // Verifica se a data está no formato "YYYY-MM-DD"
          if (/^\d{4}-\d{2}-\d{2}$/.test(value)) {
            // Divide a data em ano, mês e dia
            const [year, month, day] = value.split('-').map(Number);
            // Verifica se é uma data válida
            if (
              month >= 1 && month <= 12 &&
              day >= 1 && day <= 31 &&
              year >= 1900 && year <= new Date().getFullYear()
            ) {
              return true; // A data é válida
            } else {
              return 'Data inválida';
            }
          } else {
            return 'Formato de data inválido (use YYYY-MM-DD)';
          }
        } else {
          return 'Preenchimento obrigatório';
        }
      }
    ],
  }),
}
</script>