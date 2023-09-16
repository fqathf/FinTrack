<template>
  <div class="container">
    <br />
    <div class="d-flex justify-content-between">
      <section class="form">
        <b-form v-on:submit.prevent="handleSubmit">
          <div class="field">
            <label class="label">Jumlah/Nominal</label>
            <div class="control">
              <input
                v-model="form.nominal"
                class="form-control input"
                type="number"
                placeholder="Isi Nominal Transaksi"
                required
              />
            </div>
            <div class="control">
              <b-form-group
                label="Jenis Transaksi"
                v-slot="{ ariaDescribedby }"
              >
                <b-form-radio
                  v-model="form.jenis_transaksi"
                  :aria-describedby="ariaDescribedby"
                  name="some-radios"
                  value="Debit"
                  required
                  >Debit</b-form-radio
                >
                <b-form-radio
                  v-model="form.jenis_transaksi"
                  :aria-describedby="ariaDescribedby"
                  name="some-radios"
                  value="Kredit"
                  required
                  >Kredit</b-form-radio
                >
              </b-form-group>
            </div>
            <label class="label">Waktu</label>
            <div class="control">
              <b-form-datepicker
                id=""
                v-model="form.tanggal"
                class="mb-2"
              ></b-form-datepicker>
            </div>
            <label class="label">Deskripsi Transaksi</label>
            <div class="control">
              <b-form-textarea
                id="textarea"
                v-model="form.deskripsi"
                placeholder="Isi Deskripsi Transaksi Anda di Sini..."
                rows="3"
                max-rows="6"
              ></b-form-textarea>
            </div> <br>
            <div class="control">
              <button class="btn btn-primary">Submit</button>
            </div>
            <br />
          </div>
        </b-form>
      </section>
      <div>
        <h3>Riwayat Transaksi</h3>
        <!--ul>
          <li v-for="item in inputanForm" :key="item">
            {{ form }}
          </li>
        </ul-->
        <!--table class="table">
          <thead class="thead-light">
            <tr>
              <th scope="col">Deskripsi</th>
              <th scope="col">Nominal</th>
              <th scope="col">Jenis Transaksi</th>
              <th scope="col">Tanggal</th>
            </tr>
          </thead>
          <tbody>
            <CardItem
              v-for="(forms, i) in resultQuery"
              :key="i"
              :forms="forms"
              :isGrid="isGrid"
            />
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
          </tbody>
        <table-->
        <b-table striped hover :items="forms"></b-table>
        <h5>Total: {{ form.total }}</h5>
      </div>
    </div>
  </div>
</template>
<script>
import CardItem from '@/components/Card/CardItem.vue'

export default {
  layout(context) {
    return 'custom'
  },
  components: {
    CardItem,
  },
  data() {
    return {
      form: {
        nominal: undefined,
        jenis_transaksi: '',
        tanggal: '',
        deskripsi: '',
        total: 500000
      },
      forms: [
        {
          nominal: 500000,
          jenis_transaksi: 'Debit',
          tanggal: '2023-09-16',
          deskripsi: 'Tabungan',
        },
      ],
    }
  },
  methods: {
    handleSubmit() {
      console.log(this.form)
      const item = {
        form: this.form,
      }
      if (item.form.jenis_transaksi == 'Debit') {
        item.form.total += parseInt(item.form.nominal)
      } else if (item.form.jenis_transaksi == 'Kredit') {
        item.form.total -= parseInt(item.form.nominal)
      }
      this.forms.push(this.form)
    },
  },
  /*computed: {
    resultQuery() {
      if (this.searchQuery) {
        return this.formT.filter((item) => {
          return this.searchQuery.toLowerCase
            .split(' ')
            .every((v) => item.title.toLowerCase().include(v))
        })
      } else {
        console.log(this.forms)
        return this.forms
      }
    },
  },*/
}
</script>
