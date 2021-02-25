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
    <div class="mt-3 WhatsNew">
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
      <p>
        ＜また以下の項目につきましても引き続き、ご留意ください。＞
      </p>
      <ul>
        <li>
          高齢者はカラオケ、ダンスなど大規模な催しへの参加をお控え下さい
        </li>
        <li>
          医療、福祉施設の職員は家族以外との会食をお控え下さい
        </li>
      </ul>
      <p>
        ＜職場・事業所におかけましても、下記項目にご留意ください。＞
      </p>
      <ul>
        <li>
          症状が出れば通勤通学を控えて直ちにクリニックを受診
        </li>
        <li>
          事業所では発熱チェック
        </li>
        <li>
          病院、福祉施設サービスは特に注意
        </li>
        <li>
          各事業所で感染拡大予防ガイドラインを遵守
        </li>
        <li>
          濃厚接触者は陰性でもさらに注意
        </li>
        <li>
          医療機関は、まずコロナを疑う
        </li>
      </ul>
      <p>
        和歌山県民の皆様には、飲食を伴う懇親会・マスクなしでの会話などの「5つの場面」に留意し、3密の回避やマスクの常時着用、小まめな手洗いなど、「新しい生活様式」に基づく新型コロナウイルス感染防止対策を徹底頂きますよう、改めてお願いします。
      </p>
      <p>
        発熱などの症状が見られる場合は外出を控え、まずかかりつけ医など地域の身近な医療機関に電話で相談し、かかりつけ医がなく、どこを受診したらいいかわからない場合は、受診相談窓口に相談します（帰国者・接触者相談センターは廃止します）。
      </p>
      <p>
        なお、SNS等によりコロナウイルス感染者を特定するようなことはお控えいただき、人権尊重や個人情報の保護にご配慮ください。
      </p>
      <h3>
        【和歌山県民の皆様へ感染拡大防止の為、対策をお願いします】
      </h3>
      <p>
        新型コロナウイルス(COVID-19)の感染に関して、飛沫感染・接触感染の2つが考えられています。
      </p>
      <p>
        <strong>飛沫感染</strong><br />
        くしゃみ、咳、唾など新型コロナウイルス感染者の飛沫によって、ウイルスが空気中に放出されます。他社がそのウイルスを口・鼻などから吸い込むことで、感染してしまいます。<br />
        主な感染場所としては飲食店、カラオケ、ライブハウス、オフィスなど、人が多く集まる場所ほどリスクが高いと言われています。
      </p>
      <p>
        <strong>接触感染</strong><br />
        新型コロナウイルス感染者が咳、くしゃみなどを手で塞いだ後、そのままドアノブや電気スイッチ、手すりなどに触れることでウイルスが付着します。<br />
        そこに別の人が触れてしまい、その手で口、鼻、顔などを触ることで粘膜からウイルスが入り感染します。
      </p>
      <p>
        ウイルス自身で増えることができず、人の粘膜などに付着して入り込み、増殖していきます。「皮膚にコロナウイルスが付着しているかもしれない」という意識を一人ひとりが持ち、水と石鹸しっかりと手洗い・うがいをすることや、アルコールでの手指消毒を徹底することで、コロナウイルスの感染防止・感染力を失わせることができます。
      </p>
      <h3>
        【コロナウイルス対策として、基礎免疫力をアップ】
      </h3>
      <p>
        新型コロナウイルスに感染しない、うつさない為にも、行動自粛やマスク着用、手指の消毒以外にも、基礎免疫力を上げることが欠かせません。<br />
        その為にも生活習慣の改善を行い、ウイルスから身を守りましょう。
      </p>
      <ul>
        <li>
          <strong>お酒・タバコを控える</strong><br />
          人の体がアルコールを分解する時には、アセトアルデヒドという物質が出ます。<br />
          この物質やタバコに含まれる化学物質により、免疫力が低下すると言われています。
        </li>
        <li>
          <strong>バランスの良い食生活</strong><br />
          免疫細胞を作る為には、「1日3食」の栄養バランスの良い食事を取りましょう。<br />
          主食(ご飯、パン、麺)、主菜(肉、魚、卵、大豆製品)、副菜(菜、海藻、きのこ類)をそろえた食事をすることで、バランスの良い栄養素・エネルギーが摂取できます。<br />
          さらに、ヨーグルトなどの発酵食品、食物繊維、オリゴ糖などの栄養素は、腸内細菌叢を改善する働きがあります。免疫力を高めてくれますので、積極的に摂取しましょう。
        </li>
        <li>
          <strong>十分な睡眠を取る</strong><br />
          免疫と睡眠はとても密接に関わっています。最低でも６時間半以上、できれば７時間以上は睡眠を取るようにしましょう。寝不足の方は、しっかり眠っている方よりも風邪を引きやすいという研究データもあります。
        </li>
        <li>
          <strong>適度な運動習慣</strong><br />
          運動をすることで、血流が上がり免疫の働きが良くなります。<br />
          自宅で出来る簡単なストレッチ、スクワットやウォーキングでも効果がありますので、生活習慣として取り入れましょう。
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
