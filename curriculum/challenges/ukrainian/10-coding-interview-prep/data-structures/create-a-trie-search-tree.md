---
id: 587d8259367417b2b2512c84
title: Створіть префіксне дерево пошуку
challengeType: 1
forumTopicId: 301634
dashedName: create-a-trie-search-tree
---

# --description--

У цьому завданні відійдемо від бінарного дерева пошуку та розглянемо іншу структуру дерева: префіксне. Префіксне дерево — це впорядковане дерево пошуку, яке зазвичай містить рядки; досить часто дозволяє зберігати асоціативні масиви або динамічні набори даних, ключами яких є рядки. Їхньою перевагою є зберігання наборів даних у тих випадках, коли багато ключів мають однакові префікси, як-от усі слова у словнику. На відміну від бінарного дерева, вузли не пов’язані з фактичними значеннями. Натомість шлях до вузла визначає певний ключ. Наприклад, якщо у префіксному дереві потрібно зберегти код у вигляді рядка, ми отримаємо чотири вузли, по одному на кожну букву: c — o — d — e. Застосовуючи цей шлях до всіх вузлів, ми отримаємо код у вигляді рядка, а сам шлях є ключем, який ми зберегли. Далі, якби ми хотіли додати кодування рядка, він би розділив перші три вузли коду перед тим, як розгалузитись після d. Таким чином великі набори даних можуть зберігатися дуже компактно. Окрім цього, пошук може відбуватися дуже швидко, оскільки він практично обмежений довжиною рядка, який ми зберігаємо. А ще, на відміну від бінарних дерев, вузол може зберігати будь-яку кількість дочірніх вузлів. Як можна було здогадатися із наведеного вище прикладу, деякі метадані зазвичай зберігаються у вузлах, які містять кінець ключа, тому під час наступних обходів дерева цей ключ все ще можна відновити. Наприклад, якби ми додали коди у зазначений вище приклад, нам потрібно було б якось дізнатися, що «е» в коді означає кінець введеного раніше ключа. В іншому випадку ця інформація буде втрачена при додаванні кодів.

# --instructions--

Створимо префіксне дерево пошуку для зберігання слів. Воно буде отримувати слова за допомогою методу `add` і зберігати їх у структурі даних префіксного дерева пошуку. А також за допомогою методу `isWord` дозволить дізнатися, чи наданий рядок є словом, а за допомогою методу `print` надасть всі слова, введені у префіксне дерево. Метод `isWord` має повернути булеве значення, а метод `print` має повернути масив всіх цих слів у вигляді рядків. Щоб переконатись, що ця структура даних реалізована правильно, ми надали структуру `Node` для кожного вузла у дереві. Кожен вузол буде об’єктом із властивістю `keys`, що є об’єктом Map від JavaScript. Він міститиме окремі літери, які виступають дійсними ключами кожного вузла. Також ми створили для вузлів властивість `end`, яка може мати значення `true`, якщо вузол являє собою закінчення слова.

# --hints--

Структура `Trie` повинна мати метод `add`.

```js
assert(
  (function testTrie() {
    var test = false;
    if (typeof Trie !== 'undefined') {
      test = new Trie();
    } else {
      return false;
    }
    return typeof test.add == 'function';
  })()
);
```

Структура `Trie` повинна мати метод `print`.

```js
assert(
  (function testTrie() {
    var test = false;
    if (typeof Trie !== 'undefined') {
      test = new Trie();
    } else {
      return false;
    }
    return typeof test.print == 'function';
  })()
);
```

Структура `Trie` повинна мати метод `isWord`.

```js
assert(
  (function testTrie() {
    var test = false;
    if (typeof Trie !== 'undefined') {
      test = new Trie();
    } else {
      return false;
    }
    return typeof test.isWord == 'function';
  })()
);
```

Метод `print` має повернути всі елементи, додані до префіксного дерева, у вигляді рядків в масиві.

```js
assert(
  (function testTrie() {
    var test = false;
    if (typeof Trie !== 'undefined') {
      test = new Trie();
    } else {
      return false;
    }
    test.add('jump');
    test.add('jumps');
    test.add('jumped');
    test.add('house');
    test.add('mouse');
    var added = test.print();
    return (
      added.indexOf('jump') != -1 &&
      added.indexOf('jumps') != -1 &&
      added.indexOf('jumped') != -1 &&
      added.indexOf('house') != -1 &&
      added.indexOf('mouse') != -1 &&
      added.length == 5
    );
  })()
);
```

Метод `isWord` має повернути `true` лише для слів, доданих до дерева, та `false` для всіх інших.

```js
assert(
  (function testTrie() {
    var test = false;
    if (typeof Trie !== 'undefined') {
      test = new Trie();
    } else {
      return false;
    }
    test.add('hop');
    test.add('hops');
    test.add('hopped');
    test.add('hoppy');
    test.add('hope');
    return (
      test.isWord('hop') &&
      !test.isWord('ho') &&
      test.isWord('hopped') &&
      !test.isWord('hopp') &&
      test.isWord('hoppy') &&
      !test.isWord('hoping')
    );
  })()
);
```

# --seed--

## --seed-contents--

```js
var displayTree = tree => console.log(JSON.stringify(tree, null, 2));
var Node = function() {
  this.keys = new Map();
  this.end = false;
  this.setEnd = function() {
    this.end = true;
  };
  this.isEnd = function() {
    return this.end;
  };
};
var Trie = function() {
  // Only change code below this line

  // Only change code above this line
};
```

# --solutions--

```js
// solution required
```
