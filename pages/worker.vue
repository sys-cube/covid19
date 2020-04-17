<template>
  <div class="Worker">
    <page-header class="mb-3">
      {{ $t('企業の皆様・はたらく皆様へ') }}
    </page-header>
    <static-card>
      <h3>
        <external-link
          url="https://www.pref.wakayama.lg.jp/prefg/060100/d00203270.html"
          :icon-size="24"
          >{{ $t('新型コロナウイルス発生に関する県内事業者への「相談窓口」の開設') }}
        </external-link>
      </h3>
      <p>
        {{
          $t(
            '和歌山県商工観光労働部では、新型コロナウイルスの流行により、影響を受けるまたは、その恐れがある県内事業者の皆様を支援するため、下記の相談窓口を設置します。'
          )
        }}
      </p>
    </static-card>
    <static-card>
      <h3>
        <external-link
          url="https://www.wakayama-sangyo.com/2020/03/09/%e6%96%b0%e5%9e%8b%e3%82%b3%e3%83%ad%e3%83%8a%e3%82%a6%e3%82%a4%e3%83%ab%e3%82%b9%e3%81%ab%e9%96%a2%e3%81%99%e3%82%8b%e7%9c%8c%e5%86%85%e4%ba%8b%e6%a5%ad%e8%80%85%e5%90%91%e3%81%91%e6%94%af%e6%8f%b4/"
          :icon-size="24"
          >{{ $t('県内事業者向け支援策(外部リンク)') }}
        </external-link>
      </h3>
      <p>
        {{
          $t(
            '各団体による相談窓口、関連対策へのリンクが記載されています。'
          )
        }}
      </p>
    </static-card>
    <static-card>
      <h3>
        <external-link
          url="https://www.pref.wakayama.lg.jp/prefg/060300/gyoumu/kinyuu/sangyoushien.html"
          :icon-size="24"
          >{{ $t('中小企業者への金融支援について') }}
        </external-link>
      </h3>
      <p>
        {{
          $t(
            '主な金融支援策について一覧表がありますので融資制度をご活用されたい企業様はご確認ください。経営の安定化や事業の活性化に必要な資金を円滑に調達していただくために、県と金融機関、信用保証協会が協力して行う融資制度を設けました。'
          )
        }}
      </p>
    </static-card>
    <static-card>
      <h3>
        <external-link
          url="https://www.pref.wakayama.lg.jp/prefg/060600/d00203536.html"
          :icon-size="24"
          >{{ $t('テレワーク緊急導入支援プログラムのご紹介') }}
        </external-link>
      </h3>
      <p>
        {{
          $t(
            '今般、日本テレワーク協会（以下、JTA）において、テレワークの緊急導入をお考えの企業向けに、JTA会員企業・団体によるテレワーク緊急導入支援プログラムがとりまとめられましたので、ご紹介いたします。'
          )
        }}
      </p>
    </static-card>
    <static-card>
      <h3>
        <external-link
          url="https://www.mhlw.go.jp/stf/seisakunitsuite/bunya/0000164708_00001.html#hatarakukata"
          :icon-size="24"
          >{{
            $t('働く方と経営者の皆様へ（厚生労働省ページ）（外部リンク）')
          }}
        </external-link>
      </h3>
      <p>
        {{
          $t(
            '厚生労働省の公式ホームページにて働く方・経営者への支援について、雇用調整助成金、テレワーク、小学校等の臨時休業等に関する支援、妊娠中の女性労働者等への配慮、関係団体への要請、融資・貸付等、社会保険料の猶予等についての詳細が記載されています。'
          )
        }}
      </p>
    </static-card>
    <static-card>
      <h3>
        <external-link
          url="https://jsite.mhlw.go.jp/wakayama-roudoukyoku/newpage_00100.html"
          :icon-size="24"
          >{{ $t('小学校等の臨時休業に伴う支援等相談窓口（厚生労働省和歌山労働局）（外部リンク）') }}
        </external-link>
      </h3>
      <p>
        {{
          $t(
            '新型コロナウイルス感染症に関する労働相談等について、特別労働相談窓口を設けました。'
          )
        }}
      </p>
    </static-card>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { MetaInfo } from 'vue-meta'
import StaticCard from '@/components/StaticCard.vue'
import PageHeader from '@/components/PageHeader.vue'
import ExternalLink from '@/components/ExternalLink.vue'

export default Vue.extend({
  components: {
    PageHeader,
    StaticCard,
    ExternalLink
  },
  head(): MetaInfo {
    return {
      title: this.$t('企業の皆様・はたらく皆様へ') as string
    }
  }
})
</script>
