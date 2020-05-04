# 【62】大きな丸いボールという誤った考え{#e62}

<div class="author">デイビッド・ウッド（David Wood）</div>
<div class="author_address">アメリカ、バージニア州フレデリックスバーグ</div>

　完全に球形で、完全になめらかに作られたボールを想像してみましょう。このボールにある唯一の設計要求は、どこを測定しても直径がぴったり同じであることです。ボールは完全な球になるまで、何度も何度も磨かれます。問題がひとつもなくなれば、作業はすべて終了します。これ以降の変更はありません。それが完全というものです。

　これはあなたがこれまで取り組んできたソフトウェアプロジェクトのように聞こえましたか？　私はそうは思いませんでした。ソフトウェアはこんな風にはいかないのです。

　ソフトウェアはそのライフサイクルを通して絶えず変化するものです。設計判断は初期の要求に基づいてなされる場合が多いですが、新しい要求が出てくると突如としてそれらは制約になります。コードを新しい要求に合わせて改修していくと、設計は乱されて、コードは徐々にメンテナンス不能になっていきます。ボールは丸くなるよう作られましたが、徐々にぼろぼろであざだらけになっていくのです。

　大きな丸いボールという誤った考えとは、ソフトウェアシステムに対する要求は納品後あまり変化しないとか、さらにわるいことに、要件はコントロールできるといった妄想のことです。

　初期のソフトウェア工学の研究者らは、コーディングを始める前に要件が十分理解できていれば、メンテナンス危機は起こらないだろうと考えていました。納品後の要求変更によって起こる問題を取り上げて、それを悪者にする人もいました。要求を固定することで安定したシステムが生み出せると考えていたのです。ユーザーが変更を要求する権利を制限しようとする人もいました（例えば「ユーザーの追加機能を計画してコントロールすることで、変更管理の必要性を減らす」ことは、ジェームズ・マーチンとカーマ・マックルーアが 1983 年に提案した「メンテナンスに対する解決策」のひとつに挙げられていました）。

　残念ながら、このような厳格なコントロールは、ソフトウェアシステムをエンドユーザーにとって使えないものにするという意図せぬ副作用があります。こうした判断は目先の損得勘定に基づいていることが多く、1990 年代におけるユーザーと IT 部門の疎遠をもたらし、機能追加と称した小規模でコピーだらけの部内ソフトウェアシステム開発が続く大きな原因となりました。

　要求は絶えず移り変わるものです。ソフトウェアプロジェクトに対する要求は非常にもっともな、非常に単純な理由で変わります。第一に、ソフトウェアは変更可能である、ということです。ソフトウェアは融通が利きます。一般的にハードウェアを変更するよりもソフトウェアを変更する方が、コストの上ではるかに効果的です。

　第二に、ほとんどのユーザーは競争環境にいます。彼らはお互いに組織同士で競い合っています。必死に競争していると、新たな強みを得ようとシステムで最も融通の利くところに頼ります。ソフトウェアの柔軟性は魅力的なのです。

　もし私たちが大きな丸いボールという誤った考えに見切りをつけられれば、要求を変更するのがもっと楽になり、ソフトウェアの柔軟性をありのままに享受することができます。これは私たちがコントロールできる大きな強みになります。要求は変化します。私たちはコードをメンテナンスする必要があります。設計を乱すような新しい要求を追加する必要があります。これはフィーチャーであって、俗にいうところのバグではないのです。

　私たちは順応性のあるソフトウェアを設計できますが、それは最初から順応性をもった考え方をした場合に限ります。順応性、設計の柔軟性、変更への準備は、どんな新しいソフトウェアプロジェクトにとっても不可欠であるべきです。