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
            <b-row v-for="(item, key) in fields" :key="key" class="my-1 px-2" align-h="center">
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
      <b-btn block variant="primary" class="calculator-button my-5" @click="getResult">
        Calculate Now!
      </b-btn>
      <h1 class="my-2">
        Increases Account for Vulx Cost
      </h1>
      <b-row class="my-3">
        <b-col lg="6">
          <b-card
            border-variant="primary"
            header="10% Increase"
            header-bg-variant="primary"
            header-text-variant="white"
            align="center"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in increaseTen" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
        <b-col lg="6">
          <b-card
            border-variant="primary"
            header="20% Increase"
            header-bg-variant="primary"
            header-text-variant="white"
            align="center"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in increaseTwenty" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
      </b-row>
      <b-row class="my-3">
        <b-col lg="6">
          <b-card
            border-variant="primary"
            header="30% Increase"
            header-bg-variant="primary"
            header-text-variant="white"
            align="center"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in increaseThirty" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
        <b-col lg="6">
          <b-card
            border-variant="primary"
            header="40% Increase"
            header-bg-variant="primary"
            header-text-variant="white"
            align="center"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in increaseForty" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
      </b-row>
      <h1 class="my-2">
        Revenue Increase Multiple Harvests
      </h1>
      <b-row class="my-3">
        <b-col lg="6">
          <b-card
            border-variant="primary"
            header="10% Increase"
            header-bg-variant="primary"
            header-text-variant="white"
            align="center"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in revTen" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
       <b-col lg="6">
          <b-card
            border-variant="primary"
            header="20% Increase"
            header-bg-variant="primary"
            header-text-variant="white"
            align="center"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in revTwenty" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
      </b-row>
      <b-row class="my-3">
        <b-col lg="6">
          <b-card
            border-variant="primary"
            header="30% Increase"
            header-bg-variant="primary"
            header-text-variant="white"
            align="center"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in revThirty" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
      <b-col lg="6">
          <b-card
            border-variant="primary"
            header="40% Increase"
            header-bg-variant="primary"
            header-text-variant="white"
            align="center"
          >
            <b-list-group flush>
              <b-list-group-item v-for="(item, key) in revForty" :key="key">
                {{ item.label }}
                <b-badge v-if="item.prepend" variant="primary" pill>
                  {{ item.prepend }} {{ item.value }}
                </b-badge>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Vue from 'vue'
import { BootstrapVue, FormInputPlugin, LayoutPlugin, CardPlugin, InputGroupPlugin, ButtonPlugin } from 'bootstrap-vue'
import Servonav from '@/components/Servonav'

Vue.use(BootstrapVue, FormInputPlugin, LayoutPlugin, CardPlugin, InputGroupPlugin, ButtonPlugin)

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
          value: 900,
          prepend: '$'
        },
        numBeds: {
          type: 'number',
          label: 'Number of Raised Beds',
          name: 'numBeds',
          disabled: false,
          value: 3
        },
        bedSize: {
          type: 'number',
          label: 'Raised Bed Cubic Feet',
          name: 'bedSize',
          disabled: false,
          value: 768
        },
        sellWeightBed: {
          type: 'number',
          label: 'Sell Weight per Bed',
          name: 'sellWeightBed',
          disabled: false,
          prepend: '(lbs)',
          value: 42
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
        sellWeight: {
          type: 'number',
          label: 'Total Sell Weight',
          name: 'sellWeight',
          disabled: true,
          value: 42 * 3,
          live: true,
          prepend: '(lbs)'
        },
        vulxPerBed: {
          type: 'number',
          label: 'Vulx Needed per Bed',
          name: 'vulxPerBed',
          disabled: true,
          prepend: '(kg)',
          value: 492.31
        },
        vulxPerRoom: {
          type: 'number',
          label: 'Vulx Needed per Room',
          name: 'vulxPerRoom',
          disabled: true,
          prepend: '(kg)',
          value: 1476.92
        },
        vulxCPB: {
          type: 'text',
          label: 'Vulx Cost per Bed',
          name: 'vulxCPB',
          disabled: true,
          prepend: '$',
          value: (492.31 * 12)
        },
        vulxCPR: {
          type: 'text',
          label: 'Vulx Cost per Room',
          name: 'vulxCPR',
          disabled: true,
          prepend: '$',
          value: (((25 / 39) * 768) * 3)
        },
        vulxMinPercent: {
          type: 'text',
          label: 'Minimum % Increase Required For Break-Even in Single Harvest',
          name: 'vulxMinPercent',
          disabled: true,
          prepend: '%',
          value: (((492.31 * 12) / 900) / 42) * 100
        }
      },
      increaseTen: {
        incSellWeightPP: {
          label: 'Increased Sell Weight per Pot',
          value: '0',
          prepend: '(g)'
        },
        incSellWeightPR: {
          label: 'Increased Sell Weight per Room',
          value: '0',
          prepend: '(lbs)'
        },
        incRevPP: {
          label: 'Increased Revenue per Bed',
          value: '0',
          prepend: '$'
        },
        incRevPR: {
          label: 'Increased Revenue per Room',
          value: '0',
          prepend: '$'
        }
      },
      increaseTwenty: {
        incSellWeightPP: {
          label: 'Increased Sell Weight per Bed',
          value: '0',
          prepend: '(g)'
        },
        incSellWeightPR: {
          label: 'Increased Sell Weight per Room',
          value: '0',
          prepend: '(lbs)'
        },
        incRevPP: {
          label: 'Increased Revenue per Bed',
          value: '0',
          prepend: '$'
        },
        incRevPR: {
          label: 'Increased Revenue per Room',
          value: '0',
          prepend: '$'
        }
      },
      increaseThirty: {
        incSellWeightPP: {
          label: 'Increased Sell Weight per Bed',
          value: '0',
          prepend: '(g)'
        },
        incSellWeightPR: {
          label: 'Increased Sell Weight per Room',
          value: '0',
          prepend: '(lbs)'
        },
        incRevPP: {
          label: 'Increased Revenue per Bed',
          value: '0',
          prepend: '$'
        },
        incRevPR: {
          label: 'Increased Revenue per Room',
          value: '0',
          prepend: '$'
        }
      },
      increaseForty: {
        incSellWeightPP: {
          label: 'Increased Sell Weight per Bed',
          value: '0',
          prepend: '(g)'
        },
        incSellWeightPR: {
          label: 'Increased Sell Weight per Room',
          value: '0',
          prepend: '(lbs)'
        },
        incRevPP: {
          label: 'Increased Revenue per Bed',
          value: '0',
          prepend: '$'
        },
        incRevPR: {
          label: 'Increased Revenue per Room',
          value: '0',
          prepend: '$'
        }
      },
      revTen: {
        oneHarvest: {
          label: '1 Harvest',
          value: '0',
          prepend: '$'
        },
        twoHarvest: {
          label: '2 Harvests',
          value: '0',
          prepend: '$'
        },
        threeHarvest: {
          label: '3 Harvests',
          value: '0',
          prepend: '$'
        }
      },
      revTwenty: {
        oneHarvest: {
          label: '1 Harvest',
          value: '0',
          prepend: '$'
        },
        twoHarvest: {
          label: '2 Harvests',
          value: '0',
          prepend: '$'
        },
        threeHarvest: {
          label: '3 Harvests',
          value: '0',
          prepend: '$'
        }
      },
      revThirty: {
        oneHarvest: {
          label: '1 Harvest',
          value: '0',
          prepend: '$'
        },
        twoHarvest: {
          label: '2 Harvests',
          value: '0',
          prepend: '$'
        },
        threeHarvest: {
          label: '3 Harvests',
          value: '0',
          prepend: '$'
        }
      },
      revForty: {
        oneHarvest: {
          label: '1 Harvest',
          value: '0',
          prepend: '$'
        },
        twoHarvest: {
          label: '2 Harvests',
          value: '0',
          prepend: '$'
        },
        threeHarvest: {
          label: '3 Harvests',
          value: '0',
          prepend: '$'
        }
      },
      formData: {}
    }
  },
  methods: {
    getResult () {
      this.increaseTen.incSellWeightPP.value = this.fields.sellWeightBed.value * 0.1
      this.increaseTen.incSellWeightPR.value = (this.schema.sellWeight.value * 0.1).toFixed(5)
      this.increaseTen.incRevPP.value = ((this.increaseTen.incSellWeightPP.value * this.fields.perPound.value) - this.schema.vulxCPB.value).toFixed(2)
      this.increaseTen.incRevPR.value = (this.increaseTen.incRevPP.value * this.fields.numBeds.value).toFixed(2)

      this.increaseTwenty.incSellWeightPP.value = this.fields.sellWeightBed.value * 0.2
      this.increaseTwenty.incSellWeightPR.value = (this.schema.sellWeight.value * 0.2).toFixed(5)
      this.increaseTwenty.incRevPP.value = ((this.increaseTwenty.incSellWeightPP.value * this.fields.perPound.value) - this.schema.vulxCPB.value).toFixed(2)
      this.increaseTwenty.incRevPR.value = (this.increaseTwenty.incRevPP.value * this.fields.numBeds.value).toFixed(2)

      this.increaseThirty.incSellWeightPP.value = this.fields.sellWeightBed.value * 0.3
      this.increaseThirty.incSellWeightPR.value = (this.schema.sellWeight.value * 0.3).toFixed(5)
      this.increaseThirty.incRevPP.value = ((this.increaseThirty.incSellWeightPP.value * this.fields.perPound.value) - this.schema.vulxCPB.value).toFixed(2)
      this.increaseThirty.incRevPR.value = (this.increaseThirty.incRevPP.value * this.fields.numBeds.value).toFixed(2)

      this.increaseForty.incSellWeightPP.value = this.fields.sellWeightBed.value * 0.4
      this.increaseForty.incSellWeightPR.value = (this.schema.sellWeight.value * 0.4).toFixed(5)
      this.increaseForty.incRevPP.value = ((this.increaseForty.incSellWeightPP.value * this.fields.perPound.value) - this.schema.vulxCPB.value).toFixed(2)
      this.increaseForty.incRevPR.value = (this.increaseForty.incRevPP.value * this.fields.numBeds.value).toFixed(2)

      this.revTen.oneHarvest.value = (this.increaseTen.incRevPR.value)
      this.revTen.twoHarvest.value = (Number(this.revTen.oneHarvest.value) + (this.increaseTen.incSellWeightPP.value * this.fields.perPound.value * this.fields.numBeds.value)).toFixed(2)
      this.revTen.threeHarvest.value = (Number(this.revTen.oneHarvest.value) + (this.increaseTen.incSellWeightPP.value * this.fields.perPound.value * this.fields.numBeds.value * 2)).toFixed(2)

      this.revTwenty.oneHarvest.value = (this.increaseTwenty.incRevPR.value)
      this.revTwenty.twoHarvest.value = (Number(this.revTwenty.oneHarvest.value) + (this.increaseTwenty.incSellWeightPP.value * this.fields.perPound.value * this.fields.numBeds.value)).toFixed(2)
      this.revTwenty.threeHarvest.value = (Number(this.revTwenty.oneHarvest.value) + (this.increaseTwenty.incSellWeightPP.value * this.fields.perPound.value * this.fields.numBeds.value * 2)).toFixed(2)

      this.revThirty.oneHarvest.value = (this.increaseThirty.incRevPR.value)
      this.revThirty.twoHarvest.value = (Number(this.revThirty.oneHarvest.value) + (this.increaseThirty.incSellWeightPP.value * this.fields.perPound.value * this.fields.numBeds.value)).toFixed(2)
      this.revThirty.threeHarvest.value = (Number(this.revThirty.oneHarvest.value) + (this.increaseThirty.incSellWeightPP.value * this.fields.perPound.value * this.fields.numBeds.value * 2)).toFixed(2)

      this.revForty.oneHarvest.value = (this.increaseForty.incRevPR.value)
      this.revForty.twoHarvest.value = (Number(this.revForty.oneHarvest.value) + (this.increaseForty.incSellWeightPP.value * this.fields.perPound.value * this.fields.numBeds.value)).toFixed(2)
      this.revForty.threeHarvest.value = (Number(this.revForty.oneHarvest.value) + (this.increaseForty.incSellWeightPP.value * this.fields.perPound.value * this.fields.numBeds.value * 2)).toFixed(2)
    },
    updateSellWeight () {
      this.schema.sellWeight.value = (this.fields.sellWeightBed.value * this.fields.numBeds.value).toFixed(2)
      this.schema.vulxPerBed.value = ((25 / 39) * this.fields.bedSize.value).toFixed(4)
      this.schema.vulxPerRoom.value = (this.schema.vulxPerBed.value * this.fields.numBeds.value).toFixed(4)
      this.schema.vulxCPB.value = (this.schema.vulxPerBed.value * this.fields.vulxRate.value).toFixed(2)
      this.schema.vulxCPR.value = ((this.schema.vulxCPB.value) * this.fields.numBeds.value).toFixed(2)
      this.schema.vulxMinPercent.value = (((((this.schema.vulxCPB.value) / (this.fields.perPound.value)) / this.fields.sellWeightBed.value)) * 100).toFixed(3)
    }
  }
}
</script>
