<template>
  <div>
    <Servonav />
    <b-container class="my-3">
      <b-row align-h="center">
        <b-col lg="6">
          <b-card
            border-variant="dark"
            header="Adjustable Variables"
            align="center"
          >
            <b-row align-h="center" v-for="(item, key) in fields" :key="key" class="my-1 px-2">
              <b-input-group v-if="item.prepend" :prepend="item.prepend" :append="item.label" class="mb-2">
                <b-form-input
                  :id="key + _uid"
                  v-model="item.value"
                  :type="item.type"
                  :disabled="item.disabled"
                  reqiured
                  @input="updateSellWeight"
                />
              </b-input-group>
              <b-input-group v-else :append="item.label" class="mb-2">
                <b-form-input
                  :id="key + _uid"
                  v-model="item.value"
                  :type="item.type"
                  :disabled="item.disabled"
                  reqiured
                  @input="updateSellWeight"
                />
              </b-input-group>
            </b-row>
          </b-card>
        </b-col>
        <b-col lg="6">
          <b-card
            border-variant="dark"
            header="Automatic Variables"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in schema" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
                <b-badge v-else variant="primary" pill>
                  {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
      </b-row>
      <b-row align-h="center" class="mx-3">
        <b-card-group deck>
          <b-card
            border-variant="dark"
            header="Increases Account for Vulx Cost"
          >
          </b-card>
        </b-card-group>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Vue from 'vue'
import { BootstrapVue, FormInputPlugin, LayoutPlugin, CardPlugin, InputGroupPlugin } from 'bootstrap-vue'
import Servonav from '@/components/Servonav'

Vue.use(BootstrapVue, FormInputPlugin, LayoutPlugin, CardPlugin, InputGroupPlugin)

export default {
  components: {
    Servonav
  },
  data () {
    return {
      fields: {
        perPound: {
          type: 'number',
          label: 'Price Per Pound',
          name: 'perPound',
          disabled: false,
          value: 1200,
          prepend: '$'
        },
        numPots: {
          type: 'number',
          label: 'Pots Per Room',
          name: 'numPots',
          disabled: false,
          value: 680
        },
        potSize: {
          type: 'number',
          label: 'Pot Size',
          name: 'potSize',
          disabled: false,
          value: 7
        },
        sellWeightPot: {
          type: 'number',
          label: 'Sell Weight Per Pot',
          name: 'sellWeightPot',
          disabled: false,
          prepend: '(g)',
          value: 70
        },
        vulxRate: {
          type: 'number',
          label: 'Vulx Rate',
          name: 'vulxRate',
          disabled: false,
          prepend: '($/kg)',
          value: 12.00
        }
      },
      schema: {
        sellWeightRoom: {
          type: 'number',
          label: 'Sell Weight per Room',
          name: 'sellWeightRoom',
          disabled: true,
          value: 104.94,
          live: true,
          prepend: '(lbs)'
        },
        vulxPerPot: {
          type: 'number',
          label: 'Vulx Needed per Pot',
          name: 'vulxPerPot',
          disabled: true,
          prepend: '(kg)',
          value: 0.595
        },
        vulxPerRoom: {
          type: 'number',
          label: 'Vulx Needed per Room',
          name: 'vulxPerRoom',
          disabled: true,
          prepend: '(kg)',
          value: 404.6000
        },
        vulxCPP: {
          type: 'text',
          label: 'Vulx Cost per Pot',
          name: 'vulxCPP',
          disabled: true,
          prepend: '$',
          value: (0.595 * 12).toFixed(2)
        },
        vulxCPR: {
          type: 'text',
          label: 'Vulx Cost per Room',
          name: 'vulxCPR',
          disabled: true,
          prepend: '$',
          value: ((0.595 * 12).toFixed(2) * 680)
        },
        vulxMinPercent: {
          type: 'text',
          label: 'Minimum % Increase Required For Break-Even in Single Harvest',
          name: 'vulxMinPercent',
          disabled: true,
          prepend: '%',
          value: ((7.14 / (1200 / 454)) / 70) * 100
        }
      },
      formData: {}
    }
  },
  methods: {
    getResult () {
      alert('cannot crackulate anything yet, page not finished')
    },
    updateSellWeight () {
      this.schema.sellWeightRoom.value = (this.fields.sellWeightPot.value * 0.00220462 * this.fields.numPots.value).toFixed(2)
      this.schema.vulxPerPot.value = (85 * this.fields.potSize.value / 1000).toFixed(4)
      this.schema.vulxPerRoom.value = (this.schema.vulxPerPot.value * this.fields.numPots.value).toFixed(4)
      this.schema.vulxCPP.value = (this.schema.vulxPerPot.value * this.fields.vulxRate.value).toFixed(2)
      this.schema.vulxCPR.value = ((this.schema.vulxCPP.value) * this.fields.numPots.value).toFixed(2)
      this.schema.vulxMinPercent.value = (((((this.schema.vulxCPP.value) / (this.fields.perPound.value / 454)) / this.fields.sellWeightPot.value)) * 100).toFixed(3)
    }
  }
}
</script>
