<template>
  <div class="Contacts">
    <page-header class="mb-3">
      {{ $t('お問い合わせ先一覧') }}
    </page-header>
    <div class="Contacts-Card">
      <table class="Contacts-Card-Table" v-bind="tableAttrs">
        <thead>
          <tr>
            <th class="text-center" scope="col">
              {{ $t('区市町村') }}
            </th>
            <th class="text-center url" scope="col">{{ $t('URL') }}</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td class="content" v-bind="headingAttrs">和歌山市</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.city.wakayama.wakayama.jp/1027184/index.html"
                >http://www.city.wakayama.wakayama.jp/1027184/index.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">岩出市</td>
            <td class="url">
              <a target="_blank" href="http://www.city.iwade.lg.jp/corona/"
                >http://www.city.iwade.lg.jp/corona/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">新宮市</td>
            <td class="url">
              <a
                target="_blank"
                href="https://www.city.shingu.lg.jp/forms/info/info.aspx?info_id=46299"
                >https://www.city.shingu.lg.jp/forms/info/info.aspx?info_id=46299</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">白浜町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.shirahama.wakayama.jp/soshiki/jumin/kenko/gyomu/1580283329996.html"
                >http://www.town.shirahama.wakayama.jp/soshiki/jumin/kenko/gyomu/1580283329996.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">印南町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.wakayama-inami.lg.jp/contents_detail.php?frmId=1074"
                >http://www.town.wakayama-inami.lg.jp/contents_detail.php?frmId=1074</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">日高川町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.hidakagawa.lg.jp/town/sec_hokenfukushi/coronavirus.html"
                >http://www.town.hidakagawa.lg.jp/town/sec_hokenfukushi/coronavirus.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">有田川町</td>
            <td class="url">
              <a
                target="_blank"
                href="https://www.town.aridagawa.lg.jp/top/kinkyu/5149.html"
                >https://www.town.aridagawa.lg.jp/top/kinkyu/5149.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">紀美野町</td>
            <td class="url">
              <a
                target="_blank"
                href="https://www.town.kimino.wakayama.jp/sagasu/hokenfukushika/coronavirus/1916.html"
                >https://www.town.kimino.wakayama.jp/sagasu/hokenfukushika/coronavirus/1916.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">御坊市</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.city.gobo.wakayama.jp/kinkyu/1582878419809.html"
                >http://www.city.gobo.wakayama.jp/kinkyu/1582878419809.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">紀の川市</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.city.kinokawa.lg.jp/kouhou/corona-kanren.html"
                >http://www.city.kinokawa.lg.jp/kouhou/corona-kanren.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">有田市</td>
            <td class="url">
              <a target="_blank" href="https://www.city.arida.lg.jp/index.html"
                >https://www.city.arida.lg.jp/index.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">那智勝浦町</td>
            <td class="url">
              <a
                target="_blank"
                href="https://www.town.nachikatsuura.wakayama.jp/info/849"
                >https://www.town.nachikatsuura.wakayama.jp/info/849</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">串本町</td>
            <td class="url">
              <a
                target="_blank"
                href="https://www.town.kushimoto.wakayama.jp/fukushi/shingatakorona-taisaku.html"
                >https://www.town.kushimoto.wakayama.jp/fukushi/shingatakorona-taisaku.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">北山村</td>
            <td class="url">
              <a target="_blank" href="https://www.vill.kitayama.wakayama.jp/"
                >https://www.vill.kitayama.wakayama.jp/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">古座川町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.kozagawa.wakayama.jp/2020info/index.html"
                >http://www.town.kozagawa.wakayama.jp/2020info/index.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">太地町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.taiji.wakayama.jp/kairan/%E5%A4%AA%E5%9C%B0%E7%94%BA%E5%9B%9E%E8%A6%A7.files/R2%E5%B9%B4%E5%BA%A6%E5%88%86/R2.4.10%E5%88%86%E5%9B%9E%E8%A6%A7/%E6%96%B0%E5%9E%8B%E3%82%B3%E3%83%AD%E3%83%8A%E3%82%A6%E3%82%A4%E3%83%AB%E3%82%B9%E6%84%9F%E6%9F%93%E7%97%87%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6.pdf"
                >http://www.town.taiji.wakayama.jp/kairan/%E5%A4%AA%E5%9C%B0%E7%94%BA%E5%9B%9E%E8%A6%A7.files/R2%E5%B9%B4%E5%BA%A6%E5%88%86/R2.4.10%E5%88%86%E5%9B%9E%E8%A6%A7/%E6%96%B0%E5%9E%8B%E3%82%B3%E3%83%AD%E3%83%8A%E3%82%A6%E3%82%A4%E3%83%AB%E3%82%B9%E6%84%9F%E6%9F%93%E7%97%87%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6.pdf</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">すさみ町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.susami.lg.jp/docs/2020022700014/"
                >http://www.town.susami.lg.jp/docs/2020022700014/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">上富田町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.kamitonda.lg.jp/kurashi/kenko_fukushi/3024.html"
                >http://www.town.kamitonda.lg.jp/kurashi/kenko_fukushi/3024.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">みなべ町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.minabe.lg.jp/docs/2020040100018/"
                >http://www.town.minabe.lg.jp/docs/2020040100018/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">由良町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.yura.wakayama.jp/docs/2020021400014/"
                >http://www.town.yura.wakayama.jp/docs/2020021400014/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">日高町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.wakayama-hidaka.lg.jp/docs/2020041300035/"
                >http://www.town.wakayama-hidaka.lg.jp/docs/2020041300035/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">美浜町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.mihama.wakayama.jp/docs/2020020400015/"
                >http://www.town.mihama.wakayama.jp/docs/2020020400015/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">広川町</td>
            <td class="url">
              <a
                target="_blank"
                href="https://www.town.hirogawa.wakayama.jp/soumu/corona-virus.html"
                >https://www.town.hirogawa.wakayama.jp/soumu/corona-virus.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">湯浅町</td>
            <td class="url">
              <a target="_blank" href="http://www.town.yuasa.wakayama.jp/"
                >http://www.town.yuasa.wakayama.jp/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">高野町</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.town.koya.wakayama.jp/town/korona/12746.html"
                >http://www.town.koya.wakayama.jp/town/korona/12746.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">九度山町</td>
            <td class="url">
              <a
                target="_blank"
                href="https://www.town.kudoyama.wakayama.jp/jumin/2020-0131-sinngatakoronauirusu.html"
                >https://www.town.kudoyama.wakayama.jp/jumin/2020-0131-sinngatakoronauirusu.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">かつらぎ町</td>
            <td class="url">
              <a target="_blank" href="http://www.town.katsuragi.wakayama.jp/"
                >http://www.town.katsuragi.wakayama.jp/</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">橋本市</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.city.hashimoto.lg.jp/importantnotices/9657.html"
                >http://www.city.hashimoto.lg.jp/importantnotices/9657.html</a
              >
            </td>
          </tr>
          <tr>
            <td class="content" v-bind="headingAttrs">海南市</td>
            <td class="url">
              <a
                target="_blank"
                href="http://www.city.kainan.lg.jp/important/1583226273505.html"
                >http://www.city.kainan.lg.jp/important/1583226273505.html</a
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { MetaInfo } from 'vue-meta'
import PageHeader from '@/components/PageHeader.vue'

export default Vue.extend({
  components: {
    PageHeader
  },
  data() {
    return {
      pc: true
    }
  },
  computed: {
    tableAttrs(): any {
      return this.pc ? {} : { role: 'presentation' }
    },
    headingAttrs(): any {
      return this.pc ? {} : { role: 'heading', 'aria-level': '3' }
    }
  },
  mounted() {
    if (process.browser) {
      window.addEventListener('resize', this.handleResize)
      this.handleResize()
    }
  },
  destroyed() {
    if (process.browser) {
      window.removeEventListener('resize', this.handleResize)
    }
  },
  methods: {
    handleResize() {
      this.pc = window.innerWidth > 768
    }
  },
  head(): MetaInfo {
    return {
      title: this.$t('お問い合わせ先一覧') as string
    }
  }
})
</script>

<style lang="scss">
.Contacts {
  &-Card {
    @include card-container();

    &-Table {
      width: 100%;
      border-collapse: collapse;

      th {
        font-size: 14px !important;
      }

      td {
        padding: 0 16px;
        font-size: 14px;
      }

      @include largerThan($medium) {
        thead tr {
          height: 48px;
        }

        tbody tr {
          height: 96px;
        }

        th.url {
          width: 70%;
        }
        th,
        tr:not(:last-child) {
          border-top: none;
          border-left: none;
          border-right: none;
          border-bottom: thin solid rgba(0, 0, 0, 0.12);
        }

        tr:last-child {
          border: none;
        }
      }

      @include lessThan($medium) {
        thead {
          display: none;
        }

        tbody {
          tr {
            height: auto;

            .content {
              font-weight: bold;
              border-bottom: none !important;
              padding-top: 12px;
              padding-bottom: 8px;
            }

            .url {
              padding-bottom: 12px;
            }
          }

          tr:not(:last-child) {
            border-bottom: thin solid rgba(0, 0, 0, 0.12);
          }
        }

        td {
          display: block;
        }
      }

      p.caution {
        font-size: 12px;
        margin: 0;
      }
    }
  }
}
</style>
