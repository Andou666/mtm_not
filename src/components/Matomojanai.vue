<template>
<div>
<main>
  <h2>まともじゃない検索</h2>
  <p  style="text-align: left;">某何かに影響されてまともじゃない結果を出す検索サイトを作りました。検索結果に責任は持ちません。すべて自己責任でお願いします。</p>
  <label><strong>検索ワード</strong></label>
  <input type=text id="q" v-model="q">
  <br>
  <label><strong>オプション</strong></label>
  <select id="type" v-model="type" name="medtype">    
    <option disabled placeholder="オプションを選択してください">オプションを選択してください</option>
    <option value=" site:zw OR site:bd OR site:ke">悪意のあるサイトが多い: .zw .bd .ke</option>
    <option value=" site:pw OR site:quest OR site:ke">フィッシングサイトが多い: .pw .quest .ke</option>
    <option value=" site:zw OR site:bd OR site:ke">マルウェアが多い: .zw .bd .ke</option>
    <option value=" site:SBS OR site:tokyo OR site:xyz">グレイウェアが多い: .SBS .tokyo .xyz</option>
    <option value=" site:cyou OR site:pw OR site:ws">C2が多い: .cyou .pw .ws</option>
  </select>
  <p>
      {{q}} を検索する
  </p>
  <a style="margin-bottom: 1em;" :href="searchText">検索</a>
  
<details>
        <summary>なにこれ？</summary>
        <ul style="text-align: left; margin: 0.2em;">
            <li>単純に検索オプションをつけてGoogle検索するだけです。
            </li>
            <li>悪意のあるドメインが多くでますがまともなサイトもでてきます。（多分）<a href="https://unit42.paloaltonetworks.jp/top-level-domains-cybercrime/">参考資料</a>
            </li>
            <li>検索オプションをつけているだけですので検索までは安全。そこから先のリンク先の安全性については一切責任を負いませんので注意して利用してください。</li>
        </ul>
    </details>

</main>    
</div>
</template>



<script>
export default {
  name: 'Matomo-janai',
  data: function(){
    return{
      q: "エッチな画像",
      type: " site:com",
      url: "https://www.google.com/search?q="
    }
  },
  computed: {
    searchText: function(){
      return this.url+this.q+this.type
    }
  },
  method: {
    search: function(){
      return "site:zw";
    }
  }
}
</script>

<style scoped>
a {
  color: #fff;
  background: #0D47A1;
  padding: 10px 30px;
  display: inline-block;
  border-radius: 5px;
  text-decoration: none;
}
</style>