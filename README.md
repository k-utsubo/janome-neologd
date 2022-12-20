# janome-neologd

User dictionary for [janome](https://github.com/mocobeta/janome) using [neologd](https://github.com/neologd/mecab-ipadic-neologd) dictionary 


Example for janome
=========
.. code:: python

 from janome.tokenizer import Tokenizer
 t = Tokenizer("../dic/neologd")
 for token in t.tokenize('8月3日に放送された「中居正広の金曜日のスマイルたちへ」(TBS系)で、1日たった5分でぽっこりおなかを解消するというダイエット方法を紹介。キンタロー。のダイエットにも密着。'):
       print(token)
 # Output exceeds the size limit. Open the full output data in a text editor
8月3日	名詞,固有名詞,一般,*,*,*,8月3日,ハチガツミッカ,ハチガツミッカ
 #に	助詞,格助詞,一般,*,*,*,に,ニ,ニ
 #放送	名詞,サ変接続,*,*,*,*,放送,ホウソウ,ホーソー
 #さ	動詞,自立,*,*,サ変・スル,未然レル接続,する,サ,サ
 #れ	動詞,接尾,*,*,一段,連用形,れる,レ,レ
 #た	助動詞,*,*,*,特殊・タ,基本形,た,タ,タ
 #「	記号,括弧開,*,*,*,*,「,「,「
 #中居正広の金曜日のスマイルたちへ	名詞,固有名詞,一般,*,*,*,中居正広の金曜日のスマイルたちへ,ナカイマサヒロノキンヨウビノスマイルタチヘ,ナカイマサヒロノキンヨービノスマイルタチヘ
 #」	記号,括弧閉,*,*,*,*,」,」,」
 #(	名詞,サ変接続,*,*,*,*,(,*,*
 #TBS	名詞,固有名詞,一般,*,*,*,TBS,ティービーエス,ティービーエス
 #系	名詞,接尾,一般,*,*,*,系,ケイ,ケイ
 #)	名詞,サ変接続,*,*,*,*,),*,*
 #で	助詞,格助詞,一般,*,*,*,で,デ,デ
 #、	記号,読点,*,*,*,*,、,、,、
 #1日	名詞,固有名詞,一般,*,*,*,1日,ツイタチ,ツイタチ
 #たった	副詞,助詞類接続,*,*,*,*,たった,タッタ,タッタ
 #5分	名詞,固有名詞,一般,*,*,*,5分,ゴフン,ゴフン
 #で	助詞,格助詞,一般,*,*,*,で,デ,デ
 #ぽっこりおなか	名詞,固有名詞,一般,*,*,*,ぽっこりおなか,ポッコリオナカ,ポッコリオナカ
 #を	助詞,格助詞,一般,*,*,*,を,ヲ,ヲ
 #解消	名詞,サ変接続,*,*,*,*,解消,カイショウ,カイショー
 #する	動詞,自立,*,*,サ変・スル,基本形,する,スル,スル
 #という	助詞,格助詞,連語,*,*,*,という,トイウ,トユウ
 #ダイエット方法	名詞,固有名詞,一般,*,*,*,ダイエット方法,ダイエットホウホウ,ダイエットホウホー
 #...
 #に	助詞,格助詞,一般,*,*,*,に,ニ,ニ
 #も	助詞,係助詞,*,*,*,*,も,モ,モ
 #密着	名詞,サ変接続,*,*,*,*,密着,ミッチャク,ミッチャク
 #。	記号,句点,*,*,*,*,。,。,。

Example for pymlask
=========
modified pymlask is [here](https://github.com/k-utsubo/pymlask)
.. code:: python

 from mlask import MLAsk
 emotion_analyzer = MLAsk("../neologd") # user dictionary directory
 emotion_analyzer.analyze('彼のことは嫌いではない！(;´Д`)')
 # => {'text': '彼のことは嫌いではない！(;´Д`)',
 #     'emotion': defaultdict(<class 'list'>,{'yorokobi': ['嫌い*CVS'], 'suki': ['嫌い*CVS']}),
 #     'orientation': 'POSITIVE',
 #     'activation': 'NEUTRAL',
 #     'emoticon': ['(;´Д`)'],
 #     'intension': 2,
 #     'intensifier': {'exclamation': ['！'], 'emotikony': ['´Д`', 'Д`', '´Д', '(;´Д`)']},
 #     'representative': ('yorokobi', ['嫌い*CVS'])
 #     }

