# searchJava
<h2>About</h2>
PC内のjavaを検索、バージョンを取得しパスなどを返す
<h2>Method</h2>
<h4>・searchJava.search_path(way, priority ,bit) -> dict</h4>
javaを検索、結果のリストを返す　<br>
返り値: {"ver":{"path":(path: str), "detail": (ver: str), "bit": (64 or 32: str)}}<br>
example: {"17":{"path": "C:\Program Files\Java\jdk-17.0.1\bin\", "detail": "0.1", "bit": "64"}}<br>
<br>
引数:<br>
way (省略可): SearchJava.QUICK (デフォルト) or SearchJava.FULL or ファイルパス指定(str, example: "C:\\Program Files*\\**\\java.exe")　を使用可能<br>
どこを検索するかを指定<br>
SearchJava.QUICK -> CドライブProgramFiles内を検索<br>
SearchJava.FULL -> すべてのドライブ内を検索<br>
<br>
priority (省略可): SearchJava.NEW (デフォルト) or SearchJava.OLD を使用可能<br>
同じバージョンのjavaがあった場合、新しい方と古いほうどちらを使用するか選択<br>
SearchJava.NEW -> 新しいjavaを取得する<br>
SearchJava.OLD -> 古いjavaを取得する<br>
<br>
bit (省略可): SearchJava.ALL (デフォルト) or 64 (int) or 32 (int) を使用可能<br>
指定したbitのjavaのみを取得するようにする<br>
SearchJava.ALL -> 32bit、64bit両方を取得し、64bit版を優先する<br>
32 (int) -> 32bit版のみを取得する<br>
64 (int) -> 64bit版のみを取得する<br>
<br>
<h4>・searchJava.compound_javaLists(paths1, paths2, priority, bit) -> dict</h4>
paths1、paths2に渡された2つのリストを合成したリストを返す<br>
priority、bitによって優先度合が変わる<br>
<br>
bitを64にしても32bit版が必ず消えるわけではなく、あくまで64bit版が"優先"されるだけで32bit版も入る<br>
今後別の処理を検討中<br>
