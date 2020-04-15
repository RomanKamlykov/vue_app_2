<template>
  <div class="results">
    <table>
      <caption>Услуг</caption>

      <tbody>
        <tr v-for="(result, index) in results" :key="index">
          <td>
            <span class="progress" :style="getStyleObj(result.count, countSum)"></span>
            {{result.title}}
          </td>
          <td>
            {{result.count}}
          </td>
        </tr>
      </tbody>
      
      <tfoot>
        <tr>
          <td>Всего</td>
          <td>{{countSum}}</td>
        </tr>
      </tfoot>
    </table>
  </div>
</template>

<script>
  export default {
    name: 'Results',
    props: ['results'],
    computed: {
      countSum: function() {
        let sum = 0;
        for (const el of this.results) sum += el.count
        //reduce don't work for some reason...
        return sum;
      }
    },
    methods: {
      getStyleObj: function(num, sum) {
        const styleObj = {};
        const size = Math.round(num/sum*100);
        styleObj.width = `${size}%`;
        if(size > 50) styleObj.background = '#B1E19B'
        return styleObj;
      }
    },
    mouted: function() {
      this.updateColor();
    }
  }
</script>

<style lang="scss">
  .results {

    table {
      border-collapse: separate;
      border-spacing: 0px 2px;
      width: 100%;

      caption, td {
        font-family: Arial;
        color: #333333;
        font-size: 13px;
        line-height: 24px;
      }
      caption {
        padding-right: 20px;
      }
      caption, tfoot tr td {
        line-height: 28px;
      }
      caption, tr td:last-of-type {
        text-align: right;
      }
      tr td:last-of-type {
        font-weight: bold;
        padding-right: 30px;
        width: 60px;
      }

      tbody tr td:first-of-type {
        position: relative;
        text-indent: 5px;
        z-index: 2;
        .progress {
          height: 24px;
          z-index: -1;
          position: absolute;
          left: 0;
          background: #ACE2F8; //#B1E19B;
          border-radius: 0px 3px 3px 0px;
          border-left: 1px solid rgba(51, 51, 51, 0.2);
        }
      }

      tbody tr td { vertical-align: middle; }
      tbody tr:first-of-type td { vertical-align: bottom; border-top: 1px solid #DADADA; height: 40px; }
      tbody tr:last-of-type td { vertical-align: top; border-bottom: 1px solid #DADADA; height: 40px; }

      tfoot tr td {
        font-weight: bold;
        font-size: 16px;
      }
    }
  }
</style>