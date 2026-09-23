ねも探偵局 v0.18

【修正内容】
事件選択画面の下に、
・INVESTIGATION REQUEST
・事件ファイル
・何が起きた？
・今回の任務
・現場にいた人物
など、ゲーム開始後のUIが誤表示されていた問題を修正。

【原因】
PC向けCSSの
.layout { display:grid !important; }
が、
.hidden { display:none !important; }
より後に定義されていたため、
非表示にした gameLayout が強制表示されていた。

【v0.18】
・#gameLayout.hidden を最優先で display:none
・初期表示時は caseSelectPanel だけを表示
・事件ファイルもゲーム開始前は非表示
・DOMContentLoaded 時にも初期状態を強制確認

最初の画面：
「事件を選ぶ」＋事件カードのみ。
