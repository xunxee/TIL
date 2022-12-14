# 37μ₯ Setκ³Ό Map

# λͺ©μ°¨

- [Set](#π΄-set)
- [Map](#π΄-map)

# π΄ **Set**

`set` κ°μ²΄λ μ€λ³΅λμ§ μλ μ μΌν κ°λ€μ μ§ν©μ΄λ€. `set` κ°μ²΄λ λ°°μ΄κ³Ό μ μ¬νμ§λ§ λ€μκ³Ό κ°μ μ°¨μ΄κ° μλ€.

![https://user-images.githubusercontent.com/87808288/172766241-f8ce5b81-932f-4e48-bbe5-b74ae61e5988.png](https://user-images.githubusercontent.com/87808288/172766241-f8ce5b81-932f-4e48-bbe5-b74ae61e5988.png)

μ΄λ¬ν `Set` κ°μ²΄μ νΉμ±μ μνμ  μ§ν©μ νΉμ±κ³Ό μΌμΉνλ€. `Set`μ μνμ  μ§ν©μ κ΅¬ννκΈ° μν μλ£κ΅¬μ‘°λ€. λ°λΌμ `Set`μ ν΅ν΄ κ΅μ§ν©, ν©μ§ν©, μ°¨μ§ν©, μ¬μ§ν© λ±μ κ΅¬ν  μ μλ€.

## π  **Set κ°μ²΄μ μμ±**

`Set` κ°μ²΄λ `set` μμ±μ ν¨μλ‘ μμ±νλ€. `set` μμ±μ ν¨μμ μΈμλ₯Ό μ λ¬νμ§ μμΌλ©΄ λΉ `Set` κ°μ²΄κ° μμ±λλ€.

```jsx
const set = new Set();

console.log(set); // Set(0) {}
```

`Set` μμ±μ ν¨μλΒ μ΄ν°λ¬λΈμ μΈμλ‘ μ λ¬λ°μ `Set` μμ±νλ€. μ΄λΒ μ΄ν°λ¬λΈμ μ€λ³΅λ κ°μ `Set` κ°μ²΄μ μμλ‘ μ μ₯λμ§ μλλ€.

```jsx
const set1 = new Set([1, 2, 3, 3]);

console.log(set1); // Set(3) {1, 2, 3}

const set2 = new Set('hello');

console.log(set2); // Set(4) {"h", "e", "l", "o"}
```

μ€λ³΅μ νμ©νμ§ μλ `Set` κ°μ²΄μ νΉμ±μ νμ©νμ¬ λ°°μ΄μμ μ€λ³΅λ μμλ₯Ό μ κ±°ν  μ μλ€.

```jsx
// λ°°μ΄μ μ€λ³΅ μμ μ κ±°
const uniq = array => array.filter((v, i, self) => self.indexOf(v) === i);

console.log(uniq([2, 1, 2, 3, 4, 3, 4])); //[2, 1, 3, 4]

// Setμ μ¬μ©ν λ°°μ΄μ μ€λ³΅ μμ μ κ±°
const uniq = array => [...new Set(array)];

console.log(uniq([2, 1, 2, 3, 4, 3, 4])); //[2, 1, 3, 4]
```

```jsx
let a = [1, 2, 3, 4];
let b = [1, 2, 3, 4, 5, 6];

let set = [...new Set([...a, ...b])]; // [ 1, 2, 3, 4, 5, 6 ]
```

## π  **μμ κ°μ νμΈ**

`Set` κ°μ²΄μ μμ κ°μλ₯Ό νμΈν  λλ `Set.prototype.size` νλ‘νΌν°λ₯Ό μ¬μ©νλ€.

```jsx
const { size } = new Set([1, 2, 3, 3]);

console.log(size); //3
```

`size` νλ‘νΌν°λ `setter` ν¨μ μμ΄Β `getter` ν¨μλ§ μ‘΄μ¬νλ μ κ·Όμ νλ‘νΌν°λ€. λ°λΌμ `size` νλ‘νΌν°μ μ«μλ₯Ό ν λΉνμ¬ `Set` κ°μ²΄μ μμ κ°μλ₯Ό λ³κ²½ν  μ μλ€.

```jsx
const set = new Set([1, 2, 3]);

console.log(Object.getOwnPropertyDescriptor(Set.prototype, 'size'));
// {
//   get: Ζ get size(), 
//   set: undefined,
//   enumerable: false,
//   configurable: true
// }

set.size =  10; // λ¬΄μλλ€.

console.log(set.size); // 3
```

## π  **μμ μΆκ°**

`Set` κ°μ²΄μ μμλ₯Ό μΆκ°ν  λλ `Set.prototype.add` λ©μλλ₯Ό μ¬μ©νλ€.

```jsx
const set = new Set();
console.log(set); //Set(0) {}

set.add(1);
console.log(set); //Set(1) {1}
```

`add` λ©μλλ μλ‘μ΄ μμκ°Β μΆκ°λ `Set` κ°μ²΄λ₯Ό λ°ννλ€. λ°λΌμ `add` λ©μλλ₯Ό νΈμΆν νμ `add` λ©μλλ₯Ό μ°μμ μΌλ‘ νΈμΆν  μ μλ€.

```jsx
const set = new Set();

set.add(1).add(2);
console.log(set); // Set(2) {1, 2}
```

μΌμΉ λΉκ΅ μ°μ°μ `===`μ μ¬μ©νλ©΄ `NaN`κ³Ό `NaN`μ λ€λ₯΄λ€κ³  νκ°νλ€. νμ§λ§ `Set` κ°μ²΄λ `NaN`κ³Ό `NaN`μ κ°λ€κ³  νκ°νμ¬ μ€λ³΅ μΆκ°λ₯Ό νμ©νμ§ μλλ€. `+0`κ³Ό `-0`μ μΌμΉ λΉκ΅ μ°μ°μ `===`μ λ§μ°¬κ°μ§λ‘ κ°λ€κ³  νκ°νμ¬ μ€λ³΅ μΆκ°λ₯Ό νμ©νμ§ μλλ€.

```jsx
const set = new Set();

console.log(NaN === NaN); // false
console.log(0 === -0); // true

// NaNκ³Ό NaNμ κ°λ€κ³  νκ°νμ¬ μ€λ³΅ μΆκ°λ₯Ό νμ©νμ§ μλλ€.
set.add(NaN).add(NaN);

console.log(set); // Set(1) {NaN}

// +0κ³Ό -0μ κ°λ€κ³  νκ°νμ¬ μ€λ³΅ μΆκ°λ₯Ό νμ©νμ§ μλλ€.
set.add(0).add(-0);
console.log(set); // Set(2) {NaN, 0}
```

`Set` κ°μ²΄λ κ°μ²΄λ λ°°μ΄κ³Ό κ°μ΄ μλ°μ€ν¬λ¦½νΈμ λͺ¨λ  κ°μ μμλ‘ μ μ₯ν  μ μλ€.

## π  **μμ μ‘΄μ¬ μ¬λΆ νμΈ**

`Set` κ°μ²΄μ νΉμ  μμκ° μ‘΄μ¬νλμ§ νμΈνλ €λ©΄ `Set.prototype.has` λ©μλλ₯Ό μ¬μ©νλ€. `has` λ©μλλ νΉμ  μμ μ‘΄μ¬ μ¬λΆλ₯Ό λνλ΄λ λΆλ¦¬μΈ κ°μ λ°ννλ€.

```jsx
const set = new Set([1, 2, 3]);

console.log(set.has(2)); // true
console.log(set.has(4)); // false
```

## π  **μμ μ­μ **

`Set` κ°μ²΄μ νΉμ  μμλ₯Ό μ­μ νλ €λ©΄ `Set.prototype.delete` λ©μλλ₯Ό μ¬μ©νλ€. `delete` λ©μλλ μ­μ  μ±κ³΅ μ¬λΆλ₯Ό λνλ΄λ λΆλ¦¬μΈ κ°μ λ°ννλ€.

`Set` κ°μ²΄λ μμμ μλ―Έκ° μλ€. λ€μ λ§ν΄, λ°°μ΄κ³Ό κ°μ΄ μΈλ±μ€λ₯Ό κ°μ§ μλλ€.

```jsx
const set = new Set([1, 2, 3]);

// μμ 2κ°μ μ­μ νλ€.
set.delete(2);
console.log(set); // Set(2) {1, 3}

// μμ 1κ°μ μ­μ νλ€.
set.delete(1);
console.log(set); // Set(1) {3}
```

λ§μ½ μ‘΄μ¬νμ§ μλ `Set` κ°μ²΄μ μμλ₯Ό μ­μ νλ € νλ©΄ μλ¬ μμ΄ λ¬΄μλλ€.

`delete` λ©μλλ μ­μ  μ±κ³΅ μ¬λΆλ₯Ό λνλ΄λ λΆλ¦¬μΈ κ°μ λ°ννλ€. λ°λΌμ `Set.prototype.add` λ©μλμ λ¬λ¦¬ μ°μμ μΌλ‘ νΈμΆν  μ μλ€.

## π Β **μμ μΌκ΄ μ­μ **

`set` κ°μ²΄μ λͺ¨λ  μμλ₯Ό μΌκ΄ μ­μ νλ €λ©΄ `Set.prototpye.clear` λ©μλλ₯Ό μ¬μ©νλ€. `clear` λ©μλλ μΈμ λ `undefined`λ₯Ό λ°ννλ€.

## π  **μμ μν**

`Set` κ°μ²΄μ μμλ₯Ό μννλ €λ©΄ `Set.prototype.forEach` λ©μλλ₯Ό μ¬μ©νλ€. `Set.prototype.forEach` λ©μλλ `Array.prototype.forEach` λ©μλμ μ μ¬νκ² μ½λ°± ν¨μμ `forEach` λ©μλμ μ½λ°± ν¨μ λ΄λΆμμ `this`λ‘ μ¬μ©λ  κ°μ²΄(μ΅μ)λ₯Ό μΈμλ‘ μ λ¬νλ€.

- μ²« λ²μ§Έ μΈμ: νμ¬ μν μ€μΈ μμκ°
- λ λ²μ§Έ μΈμ: νμ¬ μν μ€μΈ μμκ°
- μΈ λ²μ§Έ μΈμ: νμ¬ μν μ€μΈ Set κ°μ²΄ μμ²΄

μ²« λ²μ§Έ μΈμμ λ λ²μ§Έ μΈμλ κ°μ κ°μ΄λ€.(μ΄μ²λΌ λμνλ μ΄μ λ `Array.prototype.forEach` λ©μλμ μΈν°νμ΄μ€λ₯Ό ν΅μΌνκΈ° μν¨)`Array.prototype.forEach` λ©μλμ μ½λ°± ν¨μλ λ λ²μ§Έ μΈμλ‘νμ¬ μν μ€μΈ μμμ μΈλ±μ€λ₯Ό μ λ¬λ°λλ€.

```jsx
const set = new Set([1, 2, 3]);

set.forEach((v, v2, set) => console.log(v, v2, set));
// 1 1 Set(3)
// 2 2 Set(3)
// 3 3 Set(3)
```

`Set` κ°μ²΄λ μ΄ν°λ¬λΈμ΄λ€. λ°λΌμ `forβ¦of`λ¬ΈμΌλ‘ μνν  μ μμΌλ©°, μ€νλ λ λ¬Έλ²κ³Ό λ°°μ΄ λμ€νΈλ­μ²λ§μ λμμ΄ λ  μλ μλ€.

```jsx
const set = new Set([1, 2, 3]);

// Set κ°μ²΄λ Set.prototypeμ Symbol.iterator λ©μλλ₯Ό μμλ°λ μ΄ν°λ¬λΈμ΄λ€.
console.log(Symbol.iterator in set); //true

// μ΄ν°λ¬λΈμΈ Set κ°μ²΄λ for...ofλ¬ΈμΌλ‘ μνν  μ μλ€.
for (const value of set) {
  console.log(value); // 1 2 3
}

// μ΄ν°λ¬λΈμΈ Set κ°μ²΄λ μ€νλ λ λ¬Έλ²μ λμμ΄ λ  μ μλ€.  
console.log([...set]); //[1, 2, 3]

// μ΄ν°λ¬λΈμΈ Set λ°°μ΄ λμ€νΈλ­μ²λ§ ν λΉμ λμμ΄ λ  μ μλ€.  
const [a, ...rest] = set;
console.log(a, rest); //1, [2, 3]
```

## π  **μ§ν© μ°μ°**

`Set` κ°μ²΄λ μνμ  μ§ν©μ κ΅¬ννκΈ° μν μλ£κ΅¬μ‘°λ€.

π₯Β **κ΅μ§ν©**

κ΅μ§ν© A β© Bλ μ§ν© Aμ μ§ν© Bμ κ³΅ν΅ μμλ‘ κ΅¬μ±λλ€.

```jsx
Set.prototype.intersection = function (set) {
  const result = new Set();

  for (const value of set) {
    // 2κ°μ setμ μμκ° κ³΅ν΅λλ μμμ΄λ©΄ κ΅μ§ν©μ λμμ΄λ€.
    if (this.has(value)) result.add(value);
  }

  return result;
};

const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 4]);

//setAμ setBμ κ΅μ§ν©
console.log(setA.intersection(setB)); //Set(2) {2, 4}
console.log(setB.intersection(setA)); //Set(2) {2, 4}
```

`Set.prototype.intersection`μ ν΅ν΄ λ©μλλ₯Ό μμ±νλ€. `for (const value of set)`Β -> `for`λ¬Έμμ `this`λ `intersection`μ νΈμΆν `setA` κ°μ²΄λ₯Ό λνλΈλ€.

λλ μλμ κ°μ λ°©λ²μΌλ‘λ κ°λ₯νλ€.

```jsx
Set.prototype.intersection = function (set) {
  return new Set([...this].filter(v => set.has(v)));
};

const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 4]);

// setAμ setBμ κ΅μ§ν©
console.log(setA.intersection(setB)); //Set(2) {2, 4}
console.log(setB.intersection(setA)); //Set(2) {2, 4}
```

π₯Β **ν©μ§ν©**

ν©μ§ν© A βͺ Bλ μ§ν© Aμ μ§ν© Bμ μ€λ³΅ μλ λͺ¨λ  μμλ‘ κ΅¬μ±λλ€.

```jsx
Set.prototype.union = function (set) {
  // this(Set κ°μ²΄)λ₯Ό λ³΅μ¬
  const result = new Set(this);

  for (const value of set) {
    //ν©μ§ν©μ 2κ°μ Set κ°μ²΄μ λͺ¨λ  μμλ‘ κ΅¬μ±λ μ§ν©μ΄λ€. μ€λ³΅λ μμλ ν¬ν¨λμ§ μλλ€.
    result.add(value);
  }

  return result;
};

const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 4]);

// setAμ setBμ ν©μ§ν©
console.log(setA.union(setB)); //Set(4) {1, 2, 3, 4}
console.log(setB.union(setA)); //Set(4) {2, 4, 1, 3}
```

```jsx
Set.prototype.union = function (set) {
  return new Set([...this, ...set]);
};

const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 4]);

//setAμ setBμ ν©μ§ν©
console.log(setA.union(setB)); //Set(4) {1, 2, 3, 4}
console.log(setB.union(setA)); //Set(4) {2, 4, 1, 3}
```

π₯Β **μ°¨μ§ν©**

μ°¨μ§ν© A - Bλ μ§ν© Aμλ μ‘΄μ¬νμ§λ§ μ§ν© Bμλ μ‘΄μ¬νμ§ μλ μμλ‘ κ΅¬μ±λλ€.

```jsx
Set.prototype.difference = function (set) {
  // this(Set κ°μ²΄)λ₯Ό λ³΅μ¬
  const result = new Set(this);

  for (const value of set) {
    // μ°¨μ§ν©μ μ΄λ νμͺ½ μ§ν©μλ μ‘΄μ¬νμ§λ§ λ€λ₯Έ νμͺ½ μ§ν©μλ μ‘΄μ¬νμ§ μλ μμλ‘ κ΅¬μ±λ μ§ν©μ΄λ€.
    result.delete(value);
  }

  return result;
};

const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 4]);

// setAμ setBμ μ°¨μ§ν©
console.log(setA.difference(setB)); // Set(2) {1, 3}
console.log(setB.difference(setA)); // Set(0) {}
```

```jsx
Set.prototype.difference = function (set) {
  return new Set([...this].filter(v => !set.has(v)));
};

const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 4]);

console.log(setA); // Set(4) {1, 2, 3, 4}
console.log([...setA]); // [1, 2, 3, 4]

//setAμ setBμ μ°¨μ§ν©
console.log(setA.difference(setB)); // Set(2) {1, 3}
console.log(setB.difference(setA)); // Set(0) {}
```

π₯Β **λΆλΆ μ§ν©κ³Ό μμ μ§ν©**

μ§ν© Aκ° μ§ν© Bμ ν¬ν¨λλ κ²½μ° μ§ν© Aλ μ§ν© Bμ λΆλΆ μ§ν©μ΄λ©°, μ§ν© Bλ μ§ν© Aμ μμ μ§ν©μ΄λ€.

```jsx
Set.prototype.isSuperset = function (subset) {
  for (const value of subset) {
    // supersetμ λͺ¨λ  μμκ° subsetμ λͺ¨λ  μμλ₯Ό ν¬ν¨νλμ§ νμΈ
    if (!this.has(value)) return false;
  }

  return true;
};

const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 4]);

//setAκ° setBμ μμ μ§ν©μΈμ§ νμΈνλ€.
console.log(setA.isSuperset(setB)); // true
console.log(setB.isSuperset(setA)); // false
```

```jsx
// thisκ° subsetμ μμ μ§ν©μΈμ§ νμΈνλ€.
Set.prototype.isSuperset = function (subset) {
  const supersetArr = [...this];
  return [...subset].every(v => supersetArr.includes(v));
};

const setA = new Set([1, 2, 3, 4]);
const setB = new Set([2, 4]);

//setAκ° setBμ μμ μ§ν©μΈμ§ νμΈνλ€.
console.log(setA.isSuperset(setB)); // true
console.log(setB.isSuperset(setA)); // false
```

# π΄Β Map

`Map` κ°μ²΄λ ν€μ κ°μ μμΌλ‘ μ΄λ£¨μ΄μ§ μ»¬λ μμ΄λ€. `Map` κ°μ²΄λΒ κ°μ²΄μ μ μ¬νμ§λ§ λ€μκ³Ό κ°μ μ°¨μ΄κ° μλ€.

![https://user-images.githubusercontent.com/87808288/172792538-3c17b25f-6913-44b3-9a3a-622e8f5af965.png](https://user-images.githubusercontent.com/87808288/172792538-3c17b25f-6913-44b3-9a3a-622e8f5af965.png)

## π Β **Map κ°μ²΄μ μμ±**

`Map` κ°μ²΄λ `Map` μμ±μ ν¨μλ‘ μμ±νλ€. `Map` μμ±μ ν¨μμ μΈμλ₯Ό μ λ¬νμ§ μμΌλ©΄ λΉ `Map` κ°μ²΄κ° μμ±λλ€.

```jsx
const map = new Map();

console.log(map); // Map(0) {}
```

`Map` μμ±μ ν¨μλΒ μ΄ν°λ¬λΈμ μΈμλ‘ μ λ¬λ°μ `Map` κ°μ²΄λ₯Ό μμ±νλ€. μ΄λΒ μΈμλ‘ μ λ¬λλ μ΄ν°λ¬λΈμΒ ν€μ κ°μ μμΌλ‘ μ΄λ£¨μ΄μ§ μμλ‘ κ΅¬μ±λμ΄μΌΒ νλ€.

```jsx
const map1 = new Map([['key1', 'value1'], ['key2', 'value2']]);

console.log(map1);
// Map(2) {
//   'key1' => 'value1',
//   'key2' => 'value2',
// }

const map2 = new Map([1, 2]); // TypeError
```

`Map` μμ±μ ν¨μμ μΈμλ‘ μ λ¬νΒ μ΄ν°λ¬λΈμ μ€λ³΅λ ν€λ₯Ό κ°λ μμκ° μ‘΄μ¬νλ©΄ κ°μ΄ λ?μ΄μ¨μ§λ€. λ°λΌμ `Map` κ°μ²΄μλ μ€λ³΅λ ν€λ₯Ό κ°λ μμκ° μ‘΄μ¬ν  μ μλ€.

```jsx
const map = new Map[['key1', 'value1'], ['key1', 'value2']];

console.log(map); //Map(1) {'key1' => 'value2'}
```

## π Β **μμ κ°μ νμΈ**

`Map` κ°μ²΄μ μμ κ°μλ₯Ό νμΈν  λλ `Map.prototype.size` νλ‘νΌν°λ₯Ό μ¬μ©νλ€.

```jsx
const { size } = new Map[['key1', 'value1'], ['key2', 'value2']];

console.log(size); // 2
```

`size` νλ‘νΌν°λ `setter` ν¨μ μμ΄ `getter` ν¨μλ§ μ‘΄μ¬νλ μ κ·Όμ νλ‘νΌν°λ€. λ°λΌμ `size` νλ‘νΌν° μ«μλ₯Ό ν λΉνμ¬ `Map` κ°μ²΄μ μμ κ°μλ₯Ό λ³κ²½ν  μ μλ€.

```jsx
const map = new Map([['key1', 'value1'], ['key2', 'value2']]);

console.log(Object.getOwnPropertyDescriptor(Map.prototype, 'size'));
// {
//   get: Ζ get size(),
//   set: undefined,
//   enumerable: false,
//   configurable: true
// }

map.size = 10; //λ¬΄μλλ€.
```

## π Β **μμ μΆκ°**

`Map` κ°μ²΄μ μμλ₯Ό μΆκ°ν  λλ `Map.prototype.set` λ©μλλ₯Ό μ¬μ©νλ€.

```jsx
const map = new Map();
console.log(map); //Map(0) {}

map.set('key1', 'value1');
console.log(); //Map(1) {'key1' => 'value1'}
```

`set` λ©μλλ μλ‘μ΄ μμκ° μΆκ°λ `Map` κ°μ²΄λ₯Ό λ°ννλ€. λ°λΌμ `set` λ©μλλ₯Ό νΈμΆν νμ `set` λ©μλλ₯Ό μ°μμ μΌλ‘ νΈμΆν  μ μλ€.

```jsx
const map = new Map();

map
  .set('key1', 'value1')
  .set('key2', 'value2');

console.log(map); //Map(2) {'key1' => 'value1', 'key2' => 'value2'}
```

`Map` κ°μ²΄μλ μ€λ³΅λ ν€λ₯Ό κ°λ μμκ° μ‘΄μ¬ν  μ μκΈ° λλ¬Έμ μ€λ³΅λ ν€λ₯Ό κ°λ μμλ₯Ό μΆκ°νλ©΄ κ°μ΄ λ?μ΄ μ¨μ§λ€.

κ°μ²΄λΒ λ¬Έμμ΄ λλ μ¬λ² κ°λ§ ν€λ‘Β μ¬μ©ν  μ μλ€. νμ§λ§Β `Map` κ°μ²΄λΒ ν€ νμμ μ νμ΄ μλ€. λ°λΌμ κ°μ²΄λ₯Ό ν¬ν¨ν λͺ¨λ  κ°μ ν€λ‘ μ¬μ©ν  μ μλ€. μ΄λ `Map` κ°μ²΄μ μΌλ° κ°μ²΄μ κ°μ₯ λλλ¬μ§λ μ°¨μ΄μ μ΄λ€.

```jsx
const map = new Map();

const lee = { name: 'Lee' };
const Kim = { name: 'Kim' };

// κ°μ²΄λ ν€λ‘ μ¬μ©ν  μ μλ€.  
map
  .set(lee, 'developer')
  .set(Kim, 'designer')

console.log(map);
// Map(2) {
//   { name: 'Lee' } => 'developer',
//   { name: 'Kim' } => 'designer',
// }
```

## π Β **μμ μ·¨λ**

`Map` κ°μ²΄μμ νΉμ  μμλ₯Ό μ·¨λνλ €λ©΄ `Map.prototype.get` λ©μλλ₯Ό μ¬μ©νλ€. `get` λ©μλμ μΈμλ‘ ν€λ₯Ό μ λ¬νλ©΄ `Map` κ°μ²΄μμ μΈμλ‘ μ λ¬ν ν€λ₯Ό κ°λ κ°μ λ°ννλ€. `Map` κ°μ²΄μμ μΈμλ‘ μ λ¬ν ν€λ₯Ό κ°λ μμκ° μ‘΄μ¬νμ§ μμΌλ©΄ `undefined`λ₯Ό λ°ννλ€.

```jsx
const map = new Map();

const lee = { name: 'Lee' };
const Kim = { name: 'Kim' };

//κ°μ²΄λ ν€λ‘ μ¬μ©ν  μ μλ€.  
map
  .set(lee, 'developer')
  .set(Kim, 'designer')

console.log(map.get(lee)); // developer
console.log(map.get('key')); // undefined
```

## π Β **μμ μ‘΄μ¬ μ¬λΆ νμΈ**

`Map` κ°μ²΄μ νΉμ  μμκ° μ‘΄μ¬νλμ§ νμΈνλ €λ©΄ `Map.prototype.has` λ©μλλ₯Ό μ¬μ©νλ€. `has` λ©μλλ νΉμ  μμμ μ‘΄μ¬ μ¬λΆλ₯Ό λνλ΄λ λΆλ¦¬μΈ κ°μ λ°ννλ€.

```jsx
const lee = { name: 'Lee' };
const Kim = { name: 'Kim' };

const map = new Map([[lee, 'developer'], [Kim, 'designer']]);

console.log(map.has(lee)); // true
console.log(map.has('key')); // false
```

## π Β **μμ μ­μ **

`Map` κ°μ²΄μ μμλ₯Ό μ­μ νλ €λ©΄ `Map.prototype.delete` λ©μλλ₯Ό μ¬μ©νλ€. `delete` λ©μλλ μ­μ  μ±κ³΅ μ¬λΆλ₯Ό λνλ΄λ λΆλ¦¬μΈ κ°μ λ°ννλ€.

## π  **μμ μΌκ΄ μ­μ **

`Map` κ°μ²΄μ μμλ₯Ό μΌκ΄ μ­μ νλ €λ©΄ `Map.prototype.clear` λ©μλλ₯Ό μ¬μ©νλ€. `clear` λ©μλλ μΈμ λ `undefined`λ₯Ό λ°ννλ€.

## π Β **μμ μν**

`Map` κ°μ²΄μ μμλ₯Ό μννλ €λ©΄ `Map.prototype.forEach` λ©μλλ₯Ό μ¬μ©νλ€. μ΄λ μ½λ°± ν¨μλ λ€μκ³Ό κ°μ΄ 3κ°μ μΈμλ₯Ό μ λ¬λ°λλ€.

- μ²« λ²μ§Έ μΈμ: νμ¬ μν μ€μΈ μμκ°
- μ²« λ²μ§Έ μΈμ: νμ¬ μν μ€μΈ μμν€
- μ²« λ²μ§Έ μΈμ: νμ¬ μν μ€μΈ Map κ°μ²΄ μμ²΄

```jsx
const lee = { name: 'Lee' };
const Kim = { name: 'Kim' };

const map = new Map([[lee, 'developer'], [Kim, 'designer']]);

map.forEach((v, k, map) => console.log(v, k, map));
// 'developer' { name: 'Lee' } Map(2) {
//   { name: 'Lee' } => 'developer',
//   { name: 'Kim' } => 'designer',
// }
// 'designer' { name: 'Kim' } Map(2) {
//   { name: 'Lee' } => 'developer',
//   { name: 'Kim' } => 'designer',
// }
```

`Map` κ°μ²΄λ μ΄ν°λ¬λΈμ΄λ€. λ°λΌμ `forβ¦of`λ¬ΈμΌλ‘ μνν  μ μμΌλ©°, μ€νλ λ λ¬Έλ²κ³Ό λ°°μ΄ λμ€νΈλ­μ²λ§ ν λΉμ λμμ΄ λ  μλ μλ€.

```jsx
const lee = { name: 'Lee' };
const Kim = { name: 'Kim' };

const map = new Map([[lee, 'developer'], [Kim, 'designer']]);

// Map κ°μ²΄λ Map.prototypeμ Symbol.iterator λ©μλλ₯Ό μμλ°λ μ΄ν°λ¬λΈμ΄λ€.
console.log(Symbol.iterator in map); //true

// μ΄ν°λ¬λΈμΈ Map κ°μ²΄λ for...ofλ¬ΈμΌλ‘ μνν  μ μλ€.
for (const entry of map) {
  console.log(entry); //[{name: 'Lee'}, 'developer'] [{name: 'Kim'}, 'desinger']
}

// μ΄ν°λ¬λΈμΈ Map κ°μ²΄λ μ€νλ λ λ¬Έλ²μ λμμ΄ λ  μ μλ€.
console.log([...map]);
//[{ name: 'Lee' }, 'developer'], [{ name: 'Kim' }, 'designer']

const [a, b] = map;
console.log(a, b); 
// [ { name: 'Lee' }, 'developer' ] [ { name: 'Kim' }, 'designer' ]
```

`Map` κ°μ²΄λ μ΄ν°λ¬λΈμ΄λ©΄μ λμμ μ΄ν°λ μ΄μμΈ κ°μ²΄λ₯Ό λ°ννλ λ©μλλ₯Ό μ κ³΅νλ€.

![https://user-images.githubusercontent.com/87808288/172806943-1f01c4e6-4b8e-4208-a39a-a13de56acace.png](https://user-images.githubusercontent.com/87808288/172806943-1f01c4e6-4b8e-4208-a39a-a13de56acace.png)

```jsx
const lee = { name: 'Lee' };
const Kim = { name: 'Kim' };

const map = new Map([[lee, 'developer'], [Kim, 'designer']]);

// Map.prototype.keysλ Map κ°μ²΄μμ μμν€λ₯Ό κ°μΌλ‘ κ°λ μ΄ν°λ μ΄ν°λ₯Ό λ°ννλ€.  
for (const key of map.keys()) {
  console.log(key); // {name: 'Lee'} {name: 'Kim'}
}

// Map.prototype.entriesλ Map κ°μ²΄μμ μμ ν€μ μμ κ°μΌλ‘ κ°λ μ΄ν°λ μ΄ν°λ₯Ό λ°ννλ€.  
for (const entry of map.entries()) {
  console.log(entry); 
	// [{name: 'Lee'}, 'developer'] [{name: 'Kim'}, 'designer']
}
```