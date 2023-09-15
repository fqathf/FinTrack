<template>
  <div class="container">
    <br />
    <div class="d-flex justify-content-between">
      <section class="form">
        <form v-on:submit.prevent="handleSubmit">
          <div class="field">
            <label class="label">Deskripsi</label>
            <div class="control">
              <textarea
                v-model="form.desc"
                class="textarea"
                placeholder="Isi Deskripsi Transaksi Anda di Sini"
              ></textarea>
            </div>
            <label class="label">Jumlah/Nominal</label>
            <div class="control">
              <input
                v-model="form.amount"
                class="input"
                type="number"
                placeholder="Isi Nominal Transaksi"
              />
            </div>
            <label class="label">Jenis Transaksi</label>
            <div class="control">
              <label class="radio">
                <input v-model="form.tc_type" type="radio" value="debit" />Debit
              </label>
              <label class="radio">
                <input
                  v-model="form.tc_type"
                  type="radio"
                  value="kredit"
                />Kredit
              </label>
            </div>
            <label class="label">Waktu</label>
            <div class="control">
              <input v-model="form.date" type="date" name="" id="" />
            </div>
            <br />
            <div class="control">
              <button class="button is-primary">Submit</button>
            </div>
            <br />
          </div>
        </form>
      </section>
      <div>
        <h3>Hasil Submit Form</h3>
        <!--ul>
          <li v-for="item in inputanForm" :key="item">
            {{ form }}
          </li>
        </ul-->
        <table class="table">
          <tr>
            <th scope="col">Deskripsi</th>
            <th scope="col">Nominal</th>
            <th scope="col">Jenis Transaksi</th>
            <th scope="col">Tanggal</th>
          </tr>
          <tr>
            <td v-for="item in inputanForm" :key="item">
              {{ form.desc }}
            </td>
            <td v-for="item in inputanForm" :key="item">
              {{ form.amount }}
            </td>
            <td v-for="item in inputanForm" :key="item">
              {{ form.tc_type }}
            </td>
            <td v-for="item in inputanForm" :key="item">
              {{ form.date }}
            </td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout(context) {
    return 'custom'
  },
  data() {
    return {
      form: {
        amount: 0,
        desc: '',
        tc_type: '',
        date: '',
      },
      inputanForm: [],
      total: 0,
    }
  },
  methods: {
    handleSubmit() {
      // console.log(this.form)
      const item = {
        form: this.form,
      }
      this.inputanForm.push(item)
    },
    debit() {
      total += amount
    },
    credit() {
      total -= amount
    },
  },
}
</script>
