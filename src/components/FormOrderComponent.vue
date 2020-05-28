<template>
  <section class="section">
    <div class="container">
      <h3>Total Pembelian</h3>
      <table class="table text-center">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Nama Menu</th>
            <th scope="col">Harga</th>
            <th scope="col">Jumlah</th>
            <th scope="col">Total</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th scope="row">1</th>
            <td>Chesse Pizza</td>
            <td>$15</td>
            <td>1 Porsi</td>
            <td>$15</td>
          </tr>
          <tr>
            <th scope="row">2</th>
            <td>Chesse Pizza</td>
            <td>$15</td>
            <td>2 Porsi</td>
            <td>$30</td>
          </tr>
          <tr>
            <th scope="row">3</th>
            <td>Chesse Pizza</td>
            <td>$15</td>
            <td>3 Porsi</td>
            <td>$45</td>
          </tr>
          <tr>
            <th scope="row">#</th>
            <td colspan="3"></td>
            <th>Total Harga</th>
          </tr>
          <tr>
            <th scope="row">#</th>
            <td colspan="3"></td>
            <td class="total-price">$90</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>
<script>
export default {
  name: "FormOrderComponent",
  component: {}
};
</script>