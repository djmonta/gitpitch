# Tips for<br>Git and Github
---

このスライドは `GitPitch` というアプリケーションで動いています<br>
### GitPitch turns <span style="color: #e49436; text-transform: none">PITCHME.md</span> into interactive, online slideshows.
<br>
<span style="color:gray; font-size:0.6em;">[ JUST LIKE THIS ONE ]</span><br>
No more <span style="color: #666666">Keynote.</span><br>
No more <span style="color: #666666">Powerpoint.</span>

----

### Just <span style="color: #e49436">Markdown</span>. Then <span style="color: #e49436">Git-Commit</span>.
For Details [\[ GitPitch \]](https://gitpitch.com/gitpitch/gitpitch)

---

## 本題に入ります
### <span style="color: #e49436">Git</span> is a version control system.
<br>
有名な郵便局メソッドで概要を理解<br>
Understanding concepts by the famous POST office method.

---

![POST Office Method](https://github.com/djmonta/gitpitch/raw/master/public/images/posts-method.png)
<br>
<span style="color:gray; font-size:0.6em;">[デザイナーがこうやってGit覚えて大好きになったよ♡ - Qiita](https://qiita.com/yunico-jp/items/87bdd13971e82833f6bb)</span><br>

---

## Git Tips 1
### git stash
あるある事例: ローカルでコミットしていない差分があり、 `Pull` でエラーが起きて出来ない
↓

<span style="color:gray; font-size:0.6em;">参考: [変更を一時的に退避！キメろgit stash - Qiita](https://qiita.com/fukajun/items/41288806e4733cb9c342)</span><br>

+++
#### 保存

```
$ git stash save
```

+++
#### リスト

```
$ git stash show
```

+++
#### 適用

```
$ git stash apply stash@{0}
```

#### 適用と同時にstashを削除

```
$ git stash pop stash@{0}
```

---

## Git Tips 2
### git reset
あるある事例: 変更前の状態に戻したい、動作確認したい<br>
↓

<span style="color:gray; font-size:0.6em;">参考: [git reset についてもまとめてみる - murankの日記](http://d.hatena.ne.jp/murank/20110327/1301224770)</span><br>
<span style="color:gray; font-size:0.6em;">参考: [git resetでどのオプション(hard, mixed, soft)を指定すべきか、シチュエーション別に分けてみる - Qiita](https://qiita.com/kmagai/items/6b4bfe3fddb00769aec4)</span><br>

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

```
$ git checkout [commit hash]
```

一時的なブランチが作成されるため、より安全。

---

## Github Tips 1
### Keyboard shortcut

![Keyboard Shortcut](https://github.com/djmonta/gitpitch/raw/master/public/images/keyboard-shortcut.png)
<br>
↓

+++
#### Code browsing
`t` : ファイル検索
`l` : 行に飛ぶ

+++
#### Repository
`g``c` : Code
`g``i` : Issues
`g``p` : Pull Requests
`g``w` : Wiki

---

## Github Tips 2
### `hub` コマンド

```
$ hub clone tiimgreen/toc
```

↓
<br>
<span style="color:gray; font-size:0.6em;">[github/hub: hub helps you win at git.](https://github.com/github/hub)</span>

+++
#### Installation

```
$ brew install hub
```

---

### Thank you!
![We are gonna great team](https://media.giphy.com/media/g4NuKdLuh0roQ/giphy.gif)
