---
title: "CodeIgniter(コードイグナイター)のset_select()メモ"
date: 2019-02-23T04:12:06+09:00
draft: false
categories: ["CodeIgniter"]
tags: ["CodeIgniter","php"]
---

---

## CodeIgniterのset_select()で少しハマってしまったのでメモ

---  

<br>

CodeIgniter(コードイグナイター)のset_select($field[, $value = ''[, $default = FALSE]])を使うときに  

<br>

```
php:CodeIgniterの公式サイト例文
<select name="myselect">
<option value="one" <?php echo  set_select('myselect', 'one', TRUE); ?> >One</option>
<option value="two" <?php echo  set_select('myselect', 'two'); ?> >Two</option>
<option value="three" <?php echo  set_select('myselect', 'three'); ?> >Three</option>
</select>
```
<br>

valueの値が、int型の ` 0 ` が判定内容に含まれる場合は、比較演算子で型判定までしないと想定しない動作をしてしまう。  ( === )

<br>

```
php:例文1
$config['test'] = array( 0 => '大きい', 1 => '小さい');

<select name="myselect">
echo'<option value="">選択してください</option>';
foreach ($test as $key => $value) {
echo'<option value="'.$key.'" '. set_select('size', $key, ( $data[0]->size == $key ) ? TRUE : '') .'>'.$value.'</option>';
}
</select>
```

<br>

上の例文のパターンで値をPOSTで受け取った場合はその該当するところにselectedをつけてほしいが、そうでない場合は  

<br>

` 選択してください ` になるようにするには下記のように比較演算子で ` === ` で型まで判定するように記述すると良い。

```
php:例文2
$config['test'] = array( 0 => '大きい', 1 => '小さい');

<select name="myselect">
echo'<option value="">選択してください</option>';
foreach ($test as $key => $value) {
echo'<option value="'.$key.'" '. set_select('size', $key, ( $data[0]->size ` === ` $key ) ? TRUE : '') .'>'.$value.'</option>';
}
</select>
```


