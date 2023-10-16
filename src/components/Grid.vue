<template>
    <v-table height="300px">
      <thead>
        <tr>
          <th class="text-left">
            Veículo
          </th>
          <th class="text-left">
            Placa
          </th>
          <th class="text-left">
            Seguradora
          </th>
          <th class="text-left">
            Data
          </th>
          <th class="text-left">
            M.O Inicial
          </th>
          <th class="text-left">
            M.O Final
          </th>
          <th class="text-left">
            Valor Total
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in placa"
          :key="item.placa"
        >
          <td>{{ item.veiculo }}</td>
          <td>{{ item.placa }}</td>
          <td>{{ item.seguradora }}</td>
          <td>{{ item.data }}</td>
          <td>{{ item.moinicial }}</td>
          <td>{{ item.mofinal }}</td>
          <td>{{ item.valortotal }}</td>
        </tr>
      </tbody>
    </v-table>
  </template>

<script>
export default {
  data() {
    return {
      placa: [] // Aqui você deve inicializar placa com um array vazio ou com os dados desejados.
    };
  }
  // ...
};
</script>
