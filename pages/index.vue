<template>
  <div class="MainPage">
    <div class="Header mb-3">
      <page-header :icon="headerItem.icon">
        {{ headerItem.title }}
      </page-header>
      <div class="UpdatedAt">
        <span>{{ $t('最終更新') }} </span>
        <time :datetime="updatedAt">{{ Data.lastUpdate }}</time>
      </div>
      <div
        v-show="!['ja', 'ja-basic'].includes($i18n.locale)"
        class="Annotation"
      >
        <span>{{ $t('注釈') }} </span>
      </div>
    </div>
    <whats-new class="mb-4" :items="newsItems" />
    <static-info
      class="mb-4"
      :url="localePath('/flow')"
      :text="$t('自分や家族の症状に不安や心配があればまずは電話相談をどうぞ')"
      :btn-text="$t('相談の手順を見る')"
    />
    <v-row class="DataBlock">
      <!-- 検査陽性者の状況 -->
      <confirmed-cases-details-card />
      <!-- 陽性患者数 -->
      <confirmed-cases-number-card />
      <!-- 陽性患者の属性 -->
      <confirmed-cases-attributes-card />
      <!-- 検査実施人数 -->
      <inspection-persons-number-card />
      <!-- 新型コロナコールセンター相談件数 -->
      <telephone-advisory-reports-number-card />
    </v-row>
    <v-divider />
    <div class="mt-3">
      <p>
        当サイトは和歌山県内の新型コロナウイルス感染症に関連する発生状況・対応状況について随時更新しております。
      </p>
      <h3>
        【和歌山県の新型コロナウイルス感染症(COVID-19)に関連する情報】
      </h3>
      <p>
        和歌山県内では年末年始から多くの市町で多数のコロナウイルス感染が確認され、急速に感染拡大が進んでいます。特に和歌山市での拡大が顕著であり、岩出市、橋本市、海南市などでも感染者が確認されております。また高齢者の入院増加で、医療提供体制の逼迫が懸念されています。
        <br />
        (陽性が判明した方の感染経路などにつきましては、保健所が調査・発表しています)
      </p>
      <p>
        先日1月14日からは「緊急事態宣言」の対象区域に近隣の大阪府・京都府・兵庫県も追加されました。期間は、3月7日（日）までとなります。<br />
        この状況を踏まえ、和歌山県災害対策課より「県民の皆様へのお願い」が改めて発表されております。
      </p>
      <p>
        本県においても和歌山市を中心としたコロナウイルス感染者が増加傾向にあり、他県からのウイルス持ち込み、大人数での会食後に家族や知人に感染が広がるといった事例が多く見られます。
      </p>
      <p>
        和歌山県民の皆様におかれましても、下記お願い事項にご協力頂きますよう、よろしくお願いします。
      </p>
      <ul>
        <li>
          緊急事態宣言対象区域への、不要不急の往来は控える<br />
          ※栃木県、埼玉県、千葉県、東京都、神奈川県、岐阜県、愛知県、京都府、大阪府、兵庫県、福岡県
        </li>
        <li>
          特に感染が拡大している区域での会食、接待を伴った飲食はお控えください
        </li>
        <li>
          遅くまで集団で会食・宿泊をしない
        </li>
        <li>
          在宅勤務(テレワーク)や時差出勤などの取り組みの強化
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { MetaInfo } from 'vue-meta'
import PageHeader from '@/components/PageHeader.vue'
import WhatsNew from '@/components/WhatsNew.vue'
import StaticInfo from '@/components/StaticInfo.vue'
import Data from '@/data/data.json'
import News from '@/data/news.json'
import ConfirmedCasesDetailsCard from '@/components/cards/ConfirmedCasesDetailsCard.vue'
import ConfirmedCasesNumberCard from '@/components/cards/ConfirmedCasesNumberCard.vue'
import ConfirmedCasesAttributesCard from '@/components/cards/ConfirmedCasesAttributesCard.vue'
import InspectionPersonsNumberCard from '@/components/cards/InspectionPersonsNumberCard.vue'
import TelephoneAdvisoryReportsNumberCard from '@/components/cards/TelephoneAdvisoryReportsNumberCard.vue'
import { convertDatetimeToISO8601Format } from '@/utils/formatDate'

export default Vue.extend({
  components: {
    PageHeader,
    WhatsNew,
    StaticInfo,
    ConfirmedCasesDetailsCard,
    ConfirmedCasesNumberCard,
    ConfirmedCasesAttributesCard,
    TelephoneAdvisoryReportsNumberCard,
    InspectionPersonsNumberCard
  },
  data() {
    const data = {
      Data,
      headerItem: {
        icon: 'mdi-chart-timeline-variant',
        title: this.$t('都内の最新感染動向')
      },
      newsItems: News.newsItems
    }
    return data
  },
  computed: {
    updatedAt() {
      return convertDatetimeToISO8601Format(this.$data.Data.lastUpdate)
    }
  },
  head(): MetaInfo {
    return {
      title: this.$t('都内の最新感染動向') as string
    }
  }
})
</script>

<style lang="scss" scoped>
.MainPage {
  .Header {
    display: flex;
    flex-wrap: wrap;
    align-items: flex-end;

    @include lessThan($small) {
      flex-direction: column;
      align-items: baseline;
    }
  }

  .UpdatedAt {
    @include font-size(14);

    color: $gray-3;
    margin-bottom: 0.2rem;
  }

  .Annotation {
    @include font-size(12);

    color: $gray-3;
    @include largerThan($small) {
      margin: 0 0 0 auto;
    }
  }
  .DataBlock {
    margin: 20px -8px;

    .DataCard {
      @include largerThan($medium) {
        padding: 10px;
      }

      @include lessThan($small) {
        padding: 4px 8px;
      }
    }
  }
}
</style>
