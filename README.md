

class: center, middle , inverse, farsi
# `bash`
## اسکریپت نویسی bash

```bash
echo 'hello dudes!'
```
    





[github](https://github.com/v-env/bash) • [website](https://venv.ir/bash) 


---
class: center, middle , inverse, farsi

## حلقه‌ها

---
class:  farsi

## دستور `seq`

* دستور `seq` دنباله ای از اعداد را ایجاد می‌کند.  مثلا برای اعداد ۱ تا ۵ می‌نویسیم

```bash
seq 1 5
```

```
1
2
3
4
5
```

* این‌جوری می‌شه گام هم براش تعریف کرد که دوتا دو تا بره جلو مثلاً

```bash
seq 1 2 5
```

```
1
3
5
```

---
class: inverse, farsi

## حلقهٔ `for`

```bash
for i in $( seq 1 5 )
do
  echo $i
done
```

```
1
2
3
4
5
```

---
class: inverse, farsi

## تفاوت `while` و `until`

**حلقهٔ** `while` تا زمانی که شرط **«درست باشه»** ادامه پیدا می‌کنه

**حلقهٔ** `until` تا وقتی که شرط **«درست بشه»** ادامه پیدا می‌کنه، 

  * یعنی قراره `false` باشه همیشه وقتی `true` شد اون موقع تموم می‌شه


---
class: inverse, farsi

## تفاوت `while` و `until`

```bash
COUNTER=0
while [ $COUNTER -lt 5 ]; do
    echo counter is $COUNTER
    let COUNTER+=1 
done
```

```
counter is 0
counter is 1
counter is 2
counter is 3
counter is 4
```

---
class: inverse, farsi

## تفاوت `while` و `until`

```bash
COUNTER=10
until [ $COUNTER -lt 5 ]; do
    echo counter is $COUNTER
    let COUNTER-=1 
done
```

```
counter is 10
counter is 9
counter is 8
counter is 7
counter is 6
counter is 5
```


---
class: center, middle , inverse, farsi

## دستور‌های خط فرمان لینوکس

---
class: inverse, farsi

## `tr`

* فرض کنید فایل `sample.txt` با متن داخلی زیر را در اختیار داریم

```bash
cat ./sample.txt
```

```
April is the cruelest month, breeding
lilacs out of the dead land, mixing
memory and desire, stirring
dull roots with spring rain
```

---
class: inverse, farsi

## `tr`

* با دستور `tr` می‌تونیم یه سری پترن‌ها را به پترن‌های دیگه ترجمه کنیم

```bash
cat sample.txt |  tr aeoui AEOUI
```

```
AprIl Is thE crUElEst mOnth, brEEdIng
lIlAcs OUt Of thE dEAd lAnd, mIxIng
mEmOry And dEsIrE, stIrrIng
dUll rOOts wIth sprIng rAIn
```

* اینجا، هر حرف صدا داری  که با حروف کوچیک نوشته شده باشه را به حروف بزرگ تبدیل می‌کنیم


---
class: inverse, farsi

## `tr`

* می‌تونیم بدون `cat` هم از `tr` استفاده کنیم. اینجوری خروجی رو توی stdout می‌بینیم

```bash
tr aeoui AEOUI  < sample.txt
```

```
AprIl Is thE crUElEst mOnth, brEEdIng
lIlAcs OUt Of thE dEAd lAnd, mIxIng
mEmOry And dEsIrE, stIrrIng
dUll rOOts wIth sprIng rAIn
```


---
class: inverse, farsi

## `tr`

* یا همون دستور قبلی رو استفاده کنیم ولی خروجی رو توی یه فایل بنویسیم

```bash
tr aeoui AEOUI  < sample.txt > output.txt
```

```bash
cat output.txt
```

```
AprIl Is thE crUElEst mOnth, brEEdIng
lIlAcs OUt Of thE dEAd lAnd, mIxIng
mEmOry And dEsIrE, stIrrIng
dUll rOOts wIth sprIng rAIn
```
