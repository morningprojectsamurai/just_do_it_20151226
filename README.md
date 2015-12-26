# just_do_it_20151226
やってみた祭り第1回

<html>
<head>
<script type="text/javascript" src="https://code.jquery.com/jquery-2.1.4.min.js"></script>
<script type="text/javascript" src=“/just_do_it/instafesta/js/core.js"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/meyer-reset/2.0/reset.css" type="text/css" />
<!-- style の中はインタフェースの見栄えを整えるためのコード -->
<style>
    body {
        width: 95%;
        margin: 30px auto;
    }

    h1 {
        font-size: 2em;
        margin-bottom: 50px;
    }

    .description {
        color: #555;
        margin: 10px 0;
    }

    strong {
        font-weight: bold;
    }

    .step {
        margin: 15px 0;
    }

    .results {
        margin-top: 30px;
    }

    .results h2 {
        font-weight: bold;
        font-size: 0.8em;
    }

    #imgList {
        list-style-type: none;
    }

    #imgList li{
        margin: 10px 10px;
        float: left;
    }
</style>
</head>

<!-- body の中はインタフェースの構造とボタンなどが押された時のアクションの定義 -->
<body>
<h1>同年代人気者グラム</h1>
<div class="step">
    <p class="description">Step1: 自分の気になるワードにマッチする Instagram のタグを検索しよう！</p>
    <strong>キーワード:</strong> <input id="tag" type="text"/><button onclick="startTagSearch('tag',  'tagSearchResults');">タグ検索</button>
</div>
<div class="step">
  <p class="description">Step2: 人気者の画像検索に使用するタグを選択しよう！</p>
  <strong>検索用タグ:</strong> <select id="tagSearchResults"></select>
</div>
<div class="step">
    <p class="description">Step3: 気になる年代を入力しよう！(半角英数)</p>
    <strong>年代:</strong> <input id="minAge" type="text" value="18" maxlength="2" size="4"/>歳 ~ <input id="maxAge" type="text" value="29"  maxlength="2" size="4"/>歳
</div>
<div class="step">
    <p class="description">Step:4 気になる性別を選択しよう！(半角英数)</p>
    <strong>性別:</strong> <select id="gender"><option value="male">男</option><option value="female">女</option></select>
</div>
<div class="step">
     <p class="description">Step5: 検索に使うデータ量を入力しよう！(半角英数)</p>
    <strong>検索ページ数: </strong> <input id="npages" type="text" value="15" maxlength="2" size="4"/>
</div>
<div class="step">
    <button id="imageSearchBtn" onclick="startImageSearch('tagSearchResults',  'gender', 'minAge', 'maxAge', 'npages', 'imgList', 'imageSearchBtn')">写真検索</button>
    <button onclick="clearImageList('imgList');">検索結果クリア</button>
</div>

<div class="results">
<h2>検索結果:</h2>
<ol id="imgList" class="clearfix"></ol>
</div>
</body>
</html>
