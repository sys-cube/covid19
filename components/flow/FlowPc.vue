<template>
  <div :class="$style.FlowCard">
    <div :class="$style.FirstSectionWrapper">
      <h3>{{ $t('新型コロナウイルス感染症にかかる相談窓口について') }}</h3>
      <p>
        新型コロナウイルス感染症についてのご相談は、最寄りの保健所又は県庁健康推進課にご連絡ください。
      </p>
      <table :class="$style.InquiryCounterTable">
        <tbody>
          <tr>
            <th />
            <th>住所</th>
            <th>連絡先</th>
            <th>受付時間（平日）</th>
          </tr>
          <tr>
            <td>県庁健康推進課</td>
            <td>和歌山市小松原通1－1</td>
            <td>TEL 073－441－2170（専用ダイヤル）<br />FAX 073－431－1800</td>
            <td>24時間対応<br />（土・日・祝含む）</td>
          </tr>
          <tr>
            <td>和歌山市保健所</td>
            <td>和歌山市吹上5－2－15</td>
            <td>TEL 073－488－5112<br />FAX 073－431－9980</td>
            <td>
              <p>9:00～17:45</p>
            </td>
          </tr>
          <tr>
            <td>海南保健所</td>
            <td>海南市大野中939</td>
            <td>
              TEL 073－482－0600<br />
              FAX 073－482－3786
            </td>
            <td>9:00～17:45</td>
          </tr>
          <tr>
            <td>岩出保健所</td>
            <td>岩出市高塚209</td>
            <td>
              TEL 0736－61－0020<br />
              FAX 0736－61－0013
            </td>
            <td>9:00～17:45</td>
          </tr>
          <tr>
            <td>橋本保健所</td>
            <td>橋本市高野口町名古曽927</td>
            <td>
              TEL 0736－42－3210<br />
              FAX 0736－42－5468
            </td>
            <td>9:00～17:45</td>
          </tr>
          <tr>
            <td>湯浅保健所</td>
            <td>有田郡湯浅町湯浅2355－1</td>
            <td>
              TEL 0737－64－1291<br />
              FAX 0737－64－1290
            </td>
            <td>9:00～17:45</td>
          </tr>
          <tr>
            <td>御坊保健所</td>
            <td>御坊市湯川町財部859－2</td>
            <td>
              TEL 0738－22－3481<br />
              FAX 0738－23-3004
            </td>
            <td>9:00～17:45</td>
          </tr>
          <tr>
            <td>田辺保健所</td>
            <td>田辺市朝日ヶ丘23－1</td>
            <td>
              TEL 0739－26－7933<br />
              FAX 0739－26－7916
            </td>
            <td>9:00～17:45</td>
          </tr>
          <tr>
            <td>新宮保健所</td>
            <td>新宮市緑ヶ丘2－4－8</td>
            <td>TEL 0735－21－9630<br />FAX 0735－21－9639</td>
            <td>9:00～17:45</td>
          </tr>
          <tr>
            <td>新宮保健所串本支所</td>
            <td>東牟婁郡串本町西向193</td>
            <td>TEL 0735－72－0525<br />FAX 0735－72－2739</td>
            <td>9:00～17:45</td>
          </tr>
        </tbody>
      </table>
      <p>
        ※緊急の場合は、受付時間外でも案内される電話番号にかければ、職員に相談できます。（ただし、FAXを除きます）
      </p>
    </div>
  </div>
</template>

<script>
export default {
  components: {}
}
</script>

<style module lang="scss">
.FirstSectionWrapper {
  page-break-before: avoid;
  page-break-inside: avoid;
  > h3 {
    color: $gray-2;
    font-size: 1.5rem;
    margin-bottom: 7px;
    @media print {
      display: none;
    }
  }
}

.Outer {
  $grid-gap: 12px;

  display: grid;

  &Upper {
    grid-gap: $grid-gap;
    grid-template-columns: 70% 30%;
    -ms-grid-columns: 70% 12px 30%;
    grid-template-rows: repeat(3, auto);
    -ms-grid-rows: auto 12px auto 12px auto;
    // HACK: IEでGridの順番がうまくいかない対応
    // https://github.com/tokyo-metropolitan-gov/covid19/issues/1313
    & > *:nth-child(1) {
      -ms-grid-column: 1;
      -ms-grid-row: 1;
    }

    & > *:nth-child(2) {
      -ms-grid-column: 1;
      -ms-grid-row: 3;
    }

    & > *:nth-child(3) {
      -ms-grid-column: 1;
      -ms-grid-row: 5;
    }

    & > *:nth-child(4) {
      -ms-grid-column: 3;
      -ms-grid-row: 1;
      -ms-grid-row-span: 3;
    }

    & > *:nth-child(5) {
      -ms-grid-column: 3;
      -ms-grid-row: 5;
    }

    margin-bottom: 36px;
  }

  &Lower {
    grid-gap: $grid-gap;
    grid-template-columns: repeat(2, calc(50% - 6px));
    -ms-grid-columns: calc(50% - 6px) 12px calc(50% - 6px);
    grid-template-rows: repeat(3, auto);
    -ms-grid-rows: auto 12px auto 12px auto;
    // HACK: IEでGridの順番がうまくいかない対応
    // https://github.com/tokyo-metropolitan-gov/covid19/issues/1313
    & > *:nth-child(1) {
      -ms-grid-column: 1;
      -ms-grid-row: 1;
    }

    & > *:nth-child(2) {
      -ms-grid-column: 1;
      -ms-grid-row: 3;
      -ms-grid-row-span: 3;
    }

    & > *:nth-child(3) {
      -ms-grid-column: 3;
      -ms-grid-row: 1;
      -ms-grid-row-span: 3;
    }

    & > *:nth-child(4) {
      -ms-grid-column: 3;
      -ms-grid-row: 5;
    }
  }
}

.InquiryCounterTable {
  width: 100%;
  border-collapse: collapse;
  border: 2px solid #008830;
  th {
    background: rgba(217, 217, 217, 0.3);
  }
  th,
  td {
    border: 2px solid #008830;
    padding: 5px;
  }
}
</style>
