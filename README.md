# `bash`

<div dir="rtl">

## اسکریپت نویسی bash

</div>

```bash
echo 'hello dudes!'
```

[github](https://github.com/v-env/bash) • [website](https://venv.ir/bash) 

<div dir="rtl">

## حلقه‌ها

## دستور `seq`

* دستور `seq` دنباله ای از اعداد را ایجاد می‌کند.  مثلا برای اعداد ۱ تا ۵ می‌نویسیم

</div>

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

<div dir="rtl">

* این‌جوری می‌شه گام هم براش تعریف کرد که دوتا دو تا بره جلو مثلاً

</div>

```bash
seq 1 2 5
```

```
1
3
5
```

<div dir="rtl">

## حلقهٔ `for`

</div>

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

<div dir="rtl">

## تفاوت `while` و `until`

**حلقهٔ** `while` تا زمانی که شرط **«درست باشه»** ادامه پیدا می‌کنه

**حلقهٔ** `until` تا وقتی که شرط **«درست بشه»** ادامه پیدا می‌کنه، 

  * یعنی قراره `false` باشه همیشه وقتی `true` شد اون موقع تموم می‌شه

## تفاوت `while` و `until`

</div>

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

<div dir="rtl">

## تفاوت `while` و `until`

</div>

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

<div dir="rtl">

## دستور‌های خط فرمان لینوکس

</div>

## `tr`

<div dir="rtl">

* فرض کنید فایل `sample.txt` با متن داخلی زیر را در اختیار داریم

</div>

```bash
cat ./sample.txt
```

```
April is the cruelest month, breeding
lilacs out of the dead land, mixing
memory and desire, stirring
dull roots with spring rain
```

## `tr`

<div dir="rtl">

* با دستور `tr` می‌تونیم یه سری پترن‌ها را به پترن‌های دیگه ترجمه کنیم

</div>

```bash
cat sample.txt |  tr aeoui AEOUI
```

```
AprIl Is thE crUElEst mOnth, brEEdIng
lIlAcs OUt Of thE dEAd lAnd, mIxIng
mEmOry And dEsIrE, stIrrIng
dUll rOOts wIth sprIng rAIn
```

<div dir="rtl">

* اینجا، هر حرف صدا داری  که با حروف کوچیک نوشته شده باشه را به حروف بزرگ تبدیل می‌کنیم

</div>

---
class: inverse, farsi

## `tr`

<div dir="rtl">

* می‌تونیم بدون `cat` هم از `tr` استفاده کنیم. اینجوری خروجی رو توی stdout می‌بینیم

</div>

```bash
tr aeoui AEOUI  < sample.txt
```

```
AprIl Is thE crUElEst mOnth, brEEdIng
lIlAcs OUt Of thE dEAd lAnd, mIxIng
mEmOry And dEsIrE, stIrrIng
dUll rOOts wIth sprIng rAIn
```

## `tr`

<div dir="rtl">

* یا همون دستور قبلی رو استفاده کنیم ولی خروجی رو توی یه فایل بنویسیم

</div>

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
