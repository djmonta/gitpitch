# Tips for<br>Git and Github
---

<p style="font-size:50%;">
このスライドは `GitPitch` というアプリケーションで動いています<br>
GitPitch turns <span style="color: #e49436; text-transform: none">PITCHME.md</span> into interactive, online slideshows.
<br>
<span style="color:gray; font-size:50%;">[ JUST LIKE THIS ONE ]</span><br>
No more <span style="color: #666666">Keynote.<br>
No more <span style="color: #666666">Powerpoint.</span>
</p>

----

### Just <span style="color: #e49436">Markdown</span>. Then <span style="color: #e49436">Git-Commit</span>.
For Details : [\[ GitPitch \]](https://gitpitch.com/gitpitch/gitpitch)

---

<span style="color:gray; font-size:50%;">本題に入ります</span>

---

### <span style="color: #e49436">Git</span> is a version control system.
<br>
有名な郵便局メソッドで概要を理解<br>
<span style="color:gray; font-size:50%;">Understanding concepts by "POST office method".</span>

---

![POST Office Method](https://github.com/djmonta/gitpitch/raw/master/public/images/posts-method.png)
<br>
参考: [デザイナーがこうやってGit覚えて大好きになったよ♡ - Qiita](https://qiita.com/yunico-jp/items/87bdd13971e82833f6bb)

---

## Git Tips 1
### git stash
あるある事例:<br>
ローカルでコミットしていない差分があり、 `Pull` でエラーが起きて出来ない<br>
↓
<br>
- 参考: [変更を一時的に退避！キメろgit stash - Qiita](https://qiita.com/fukajun/items/41288806e4733cb9c342)

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

`stash@{0}` には、 `stash list` で先頭に出てくる値を入れる

#### 適用と同時にstashを削除

```
$ git stash pop stash@{0}
```

---

## Git Tips 2
### git reset
あるある事例:<br>
変更前の状態に戻したい、動作確認したい<br>
↓
<br>
- 参考: [git reset についてもまとめてみる - murankの日記](http://d.hatena.ne.jp/murank/20110327/1301224770)
- 参考: [git resetでどのオプション(hard, mixed, soft)を指定すべきか、シチュエーション別に分けてみる - Qiita](https://qiita.com/kmagai/items/6b4bfe3fddb00769aec4)

+++
#### 前回のコミット時点に戻りたい

```
$ git reset --hard HEAD
```

`--hard` オプションは、コミットしていない変更があっても無視します（保存しておきたい場合は、 `stash` か `checkout -b [branch name]` ）

+++
#### あるコミット時点の動作確認をしたい

```
$ git reset --hard [commit hash]
```

<br>

```
$ git checkout [commit hash]
```

一時的なブランチが作成されるため、より安全。

---

## Github Tips 1
### Keyboard shortcut

![Keyboard Shortcut](https://github.com/djmonta/gitpitch/raw/master/public/images/keyboard-shortcut.png)

+++
#### Code browsing
`t` : ファイル検索<br>
`l` : 行に飛ぶ<br>

+++
#### Repository
`g` `c` : Code<br>
`g` `i` : Issues<br>
`g` `p` : Pull Requests<br>
`g` `w` : Wiki<br>

---

## Github Tips 2
### `hub` コマンド

```
$ hub clone tiimgreen/toc
```

↓
<br>
For Details : [github/hub: hub helps you win at git.](https://github.com/github/hub)

+++
#### Installation

```
$ brew install hub
```

---

### Thank you!
![We are gonna great team](https://media.giphy.com/media/g4NuKdLuh0roQ/giphy.gif)
