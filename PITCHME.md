# Tips for<br><span style="color: #e49436">Git</span> and <span style="color: #e49436">Github</span>
---

<span style="font-size:0.45em;">このスライドは `GitPitch` というアプリケーションで動いています</span><br>
GitPitch turns <span style="color: #e49436; text-transform: none">PITCHME.md</span> into interactive, online slideshows.
<br>
<span style="color:gray; font-size:0.45em;">[ JUST LIKE THIS ONE ]</span><br>
No more <span style="color: #666666">Keynote.<br>
No more <span style="color: #666666">Powerpoint.</span>
</p>

----

### Just <span style="color: #e49436">Markdown</span>. Then <span style="color: #e49436">Git-Commit</span>.
<span style="color:gray; font-size:0.45em;">For Details : [\[ GitPitch \]](https://gitpitch.com/gitpitch/gitpitch)</span>

---

<span style="font-size:0.75em">本題に入ります</span>

---

### <span style="color: #e49436">Git</span> is a version control system.
<br>
有名な郵便局メソッドで概要を理解<br>
<span style="color:gray; font-size:0.45em;">Understanding concepts by "POST office method".</span>

---

![POST Office Method](https://github.com/djmonta/gitpitch/raw/master/public/images/posts-method.png)<br>
<span style="color:gray; font-size:0.45em;">参考: [デザイナーがこうやってGit覚えて大好きになったよ♡ - Qiita](https://qiita.com/yunico-jp/items/87bdd13971e82833f6bb)</span>

---

## Git Tips 1
### <span style="color: #e49436">git stash</span>
あるある事例:<br>
ローカルでコミットしていない差分があり、 `Pull` でエラーが起きて出来ない<br>
↓

+++
#### 保存

```
$ git stash save
```

+++
#### リスト

```
$ git stash list
```

#### 変更の内容も見る

```
$ git stash list -p
```

+++
#### 適用

```
$ git stash apply stash@{0}
```

<span style="color:gray; font-size:0.45em;">`stash@{0}` には、 `stash list` で先頭に出てくる値を入れる</span><br>

#### 適用と同時にstashを削除

```
$ git stash pop stash@{0}
```

+++

<span style="color:gray; font-size:0.45em;">参考: [変更を一時的に退避！キメろgit stash - Qiita](https://qiita.com/fukajun/items/41288806e4733cb9c342)</span>

---

## Git Tips 2
### <span style="color: #e49436">git reset</span>
あるある事例:<br>
変更前の状態に戻したい、動作確認したい<br>
↓

+++
#### 前回のコミット時点に戻りたい

```
$ git reset --hard HEAD
```

<span style="color:gray; font-size:0.45em;">`--hard` オプションは、コミットしていない変更があっても無視<br>
保存しておきたい場合は、 `stash` か `checkout -b [branch name]`</span>

+++
#### あるコミット時点の動作確認をしたい

```
$ git reset --hard [commit hash]
```

<br>

#### あるコミット時点でブランチを切る

```
$ git checkout [commit hash]
```

<span style="color:gray; font-size:0.45em;">こちらの方が、より安全。</span>

+++

<span style="color:gray; font-size:0.45em;">参考: [git reset についてもまとめてみる - murankの日記](http://d.hatena.ne.jp/murank/20110327/1301224770)<br>
参考: [git resetでどのオプション(hard, mixed, soft)を指定すべきか、シチュエーション別に分けてみる - Qiita](https://qiita.com/kmagai/items/6b4bfe3fddb00769aec4)</span>

---

## Github Tips 1
### <span style="color: #e49436">Keyboard shortcut</span>

![Keyboard Shortcut](https://github.com/djmonta/gitpitch/raw/master/public/images/keyboard-shortcut.png)

+++
#### Code browsing
- `t` : ファイル検索
- `l` : 行に飛ぶ

+++
#### Repository
- `g` `c` : Code
- `g` `i` : Issues
- `g` `p` : Pull Requests
- `g` `w` : Wiki

---

## Github Tips 2
### <span style="color: #e49436">`hub` コマンド</span>

```
$ hub clone tiimgreen/toc
```

↓

+++
#### Installation

```
$ brew install hub
```

+++

<span style="color:gray; font-size:0.45em;">For Details : [github/hub: hub helps you win at git.](https://github.com/github/hub)</span>

---

## Thank you!
![We are gonna great team](https://media.giphy.com/media/g4NuKdLuh0roQ/giphy.gif)

<span style="color:gray; font-size:0.45em;">参考: [github-cheat-sheet/README.ja.md at master · tiimgreen/github-cheat-sheet](https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.ja.md)</span>

