# 【1-75】映像系プログラマが音の世界に飛び込んで

<div class="author">土田 善紀</div>

　ゲーム業界に入って以降、映像系プログラム専門の経歴が長かった私ですが、2006 年末にサウンド担当となった時、予想以上のハードな世界に驚いたものです。ここではその体験の一部を皆さんにお伝えできればと思います。

　現世代のゲームプラットフォームの多くは、サウンド発音においてデジタル信号処理を必要としています。昔ながらの MIDI 的な譜面演奏処理・専用ハードウェアでの波形合成処理は減り、メイン CPU でストリームデータを直接加工生成するというのが主流になっています。チャンネル数の違いはあれど、携帯機やモバイルでもこのあたりの事情は変わりません。

　サウンド担当になって驚いたのは、そのデータ量です。48khz・5.1ch・float のストリームデータ処理では 1 秒間に 28 万 8 千もの float を演算操作しなければなりません、しかも 1 発音あたりでこの量なのです！ 例えば骨 100 本の大型モンスターの各関節について回転・移動・拡縮モーションを 60fps で計算しても秒間 5 万 4 千 float にしかなりません。サウンドの場合、複雑な音響効果には FFT や IFFT が必要となりますから、3D マトリクス演算どころの比では無い処理量が必要となるのです。そして据え置きゲーム機ではこれらの音が同時 80 近くも発音されるのですから大変な物量です。

　タイミングのシビアさにも驚きました。1/60 秒、msec（1/1,000 秒）あたりまでは映像でも良く出る単位でしたが、サウンドでは μsec（1/1,000,000 秒）が処理単位となる場面もあります。全体データ量と一時メモリ量の兼ね合いもあり、下位層では非常に細かい単位での分断処理が要求されます。サウンドプログラマという職業で割り込みやスレッド制御、排他制御が重要項目になるとは思いませんでした。しかも音声出力デバイスは決して処理遅延を許してくれません。映像の場合は間に合わなければフレーム落ちで滑らかさを失う程度で済みますし、あえて最初からレートを落とす選択もあるでしょうが、音声の場合処理落ちは即「ガガガガ！」というループ爆音ノイズとして顕在化してしまいますので、たとえ一瞬でも絶対に遅延は許されない、という厳しい世界です。

　空間音像処理に関しても特徴があります。まず音は視野カリングが出来ません。見ている画面方向だけでなく、後ろからも上下からも耳に届きますから、常に全方位の演算が必要なのです。建物の裏だからといって枝刈りするわけにも行きません。光と違い、音には直進だけでなく回折するという厄介な性質があります。しかもただ廻り込むだけでなく、折れ曲がるたびに高周波域の減衰と音量の減衰を伴うという演算処理の上乗せオマケまで付いてきます。遮蔽も単なる遮音ではなく壁越しの透過がありますし、これまたフィルタ演算を伴います。反射も次数を重ねればそれは残響となって表現手法の根本からの転換を迫られますし、到達距離での発音遅延や周波数特性変化、時空間変化でのドップラー、人間の聴覚認識特性など、正直言って光源を操る事にはある程度長けた気になっていた自分でも、音の世界の奥の深さにはただただ感嘆するばかりです。

　「Pause は停止にあらず、フェードだ」「絵は重ねても白飽和するだけだが、爆音はスピーカーを壊す」「音声圧縮は世界の難題、テクスチャを 1/4 にする方がはるかに楽」など、サウンド開発の現場からは色々語り尽くせぬ程の貴重なノウハウが得られましたし、これからも新たな発見や挑戦は続いていくのだと思います。

　プログラマの中にはサウンドに興味を示さない人も多いですが、音は映像よりはるかにエキサイティングな分野だと私は思いますよ？ みなさんも音に対する理解と知識を深めていって下さいね。