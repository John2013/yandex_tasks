# yandex_tasks
https://habr.com/ru/company/yandex/blog/493966/

![](https://habrastorage.org/webt/5d/rh/fo/5drhfost9i2nmn9onzzyiy_ixli.jpeg)

Хабр, это снова я, Алексей Рак (фото не мое). В прошлом году, помимо основной работы, 
мне довелось стать одним из авторов задач для кандидатов в Яндекс. Сегодня наша команда 
впервые за долгое время публикует на Хабре реальные задачи для разработчиков, которые 
устраиваются в компанию. Эти задачи использовались до февраля 2020 года при отборе на 
стажировку для бэкендеров. Решения проверял компьютер. Сейчас кандидатам достаются 
похожие задания.  

Разборы и код сознательно спрятаны в спойлеры. Если вы готовитесь к собеседованиям 
в большие IT-компании, попробуйте решить одну или несколько задач, прежде чем смотреть 
разбор. Отправить решение для проверки можно на Codeforces — ответ придёт сразу же 
([ссылка на Codeforces](https://codeforces.com/gym/102558) и 
<abbr title="На Codeforces невозможно выставить разные ограничения по времени и 
памяти для разных языков, поэтому там эти ограничения одинаковые, в отличие от 
задач в этом посте.">примечание</abbr>). Код представлен на Python, C++ и Java. 
Важно: авторский «олимпиадный» код не предназначен для продакшена, он написан 
исходя из того, что система будет проверять его автоматически.  
<a name="habracut"></a>  
Авторы и мои коллеги: задача A — Павел Дорошкевич, B и F — Егор Чунаев, E — Андрей Халявин, 
C и D — я.  

[A. День рождения Васи](#a)  
　[Решение и код](#ar)  

[B. Закрытый ключ](#b)  
　[Решение и код](#br)  

[C. Программист на пляже](#c)  
　[Решение и код](#cr)  

[D. Перемещение чанков](#d)  
　[Решение и код](#dr)  

[E. Разделение графа](#e)  
　[Решение и код](#er)  

[F. Поиск](#f)  
　[Решение и код](#fr)  

<a name="a"></a>

## A. День рождения Васи

|||
|--------------------------------|-------------------|
| Ограничение по времени на тест | 3 с               |
| Ограничение по памяти на тест  | 256 МБ            |
| Ввод                           | стандартный ввод  |
| Вывод                          | стандартный вывод |

Вася и его друзья очень любят вкусно поесть. На свой день рождения каждый обязан удивить 
других, приготовив новые вкусные и полезные блюда.  

Сегодня у Васи день рождения, и он позвал своих друзей отведать n своих самых лучших блюд. 
Название каждого из них состоит из строчных букв английского алфавита, цифр и знака подчеркивания.  

Для приготовления блюда с номером i требуется z<sub>i</sub> ингредиентов. Для каждого 
ингредиента известно его название, требуемое количество для одной порции блюда, а также 
единица измерения, в которой это количество задано. Помимо этого, Васе известно, что 
i-й кулинарный шедевр захотят попробовать c<sub>i</sub> друзей.  

Используются следующие единицы измерения:  

*   g, kg — граммы и килограммы соответственно;
*   l, ml — литры и миллилитры соответственно;
*   cnt, tens — одна штука и десять штук соответственно.

В одном килограмме 1000 грамм и в одном литре 1000 миллилитров. Делать перевод из одной 
единицы измерения в другую можно тогда и только тогда, когда они одновременно обозначают 
или массу, или объем, или количество.  

У Васи есть два справочника ингредиентов. В первом для каждого ингредиента указано его 
количество в упаковке и цена за упаковку. Во втором справочнике для каждого ингредиента 
указано содержание белков, жиров, углеводов и энергетическая ценность некоторого количества 
данного ингредиента.  

Васе нужно приготовить все блюда, при этом не купить ничего лишнего. Для этого ему нужно 
определить, какие ингредиенты и в каком количестве необходимо приобрести в магазине.  

Так как друзья именинника очень следят за питанием, то они, перед тем как попробовать 
Васины блюда, захотят узнать всё: как Вася готовил блюда, их энергетическую ценность и 
содержание белков, жиров и углеводов. Васе нужно подготовить эту информацию.  

Необходимо помочь имениннику подсчитать, сколько требуется потратить денег на покупку 
продуктов в магазине, какие ингредиенты и в каком количестве нужно купить, а также для 
каждого блюда посчитать содержание белков, жиров, углеводов и энергетическую ценность, 
если его съесть полностью.  

#### Входные данные

Первая строка содержит целое число n (1 ⩽ n ⩽ 1000) — количество блюд, которое решил 
приготовить Вася.  

Затем следует описание n блюд. В первой строке содержатся строка d<sub>i</sub> и целые 
числа с<sub>i</sub>, z<sub>i</sub> (1 ⩽ с<sub>i</sub>, z<sub>i</sub> ⩽ 100) — название 
блюда, количество друзей, желающих отведать данное блюдо, и количество ингредиентов 
необходимых для приготовления. Название блюда состоит из строчных букв английского 
алфавита, цифр и знака подчеркивания. Его длина не превосходит 20 символов.  

В следующих z<sub>i</sub> строках содержатся описания ингредиентов. В строке с номером j 
содержатся строка s<sub>i, j</sub> — название ингредиента, целое число a<sub>i, j</sub> 
(1 ⩽ a<sub>i, j</sub> ⩽ 1000) — требуемое количество ингредиента и строка u<sub>i, j</sub> — 
название единицы измерения количества. Название ингредиента состоит из строчных букв английского 
алфавита, цифр и знака подчеркивания. Длина строки не превосходит 20 символов.  

Следующая строка содержит целое число k (1 ⩽ k ⩽ 1000) — количество ингредиентов в каталоге цен.  

В каждой из следующих k строк содержатся четыре значения t<sub>i</sub> p<sub>i</sub> 
a<sub>i</sub> u<sub>i</sub>, описывающих ингредиент.  

*   t<sub>i</sub> — название ингредиента, состоящее из строчных букв английского алфавита, цифр и 
знака подчеркивания. Длина строки не превосходит 20 символов;
*   p<sub>i</sub> — стоимость ингредиента, заданная целым числом (1 ⩽ p<sub>i</sub> ⩽ 1000);
*   a<sub>i</sub> — количество ингредиента в упаковке в единицах, заданное целым числом 
(1 ⩽ a<sub>i</sub> ⩽ 1000);
*   u<sub>i</sub> — единица измерения количества (l, ml, g, kg, cnt или tens).

Следующая строка содержит число m (1 ⩽ m ⩽ 1000) — количество ингредиентов в каталоге еды.  

Далее расположены m строк, в каждой из которых содержатся семь значений t<sub>i</sub> 
a<sub>i</sub> u<sub>i</sub> pr<sub>i</sub> f<sub>i</sub> ch<sub>i</sub> fv<sub>i</sub>, 
описывающих ингредиент.  

*   t<sub>i</sub> — название ингредиента, состоящее из строчных букв английского алфавита, 
цифр и знака подчеркивания. Длина строки не превосходит 20 символов;
*   a<sub>i</sub> — количество ингредиента, для которого указаны характеристики ингредиента, 
заданное целым числом (1 ⩽ a<sub>i</sub> ⩽ 1000);
*   u<sub>i</sub> — единица измерения (l, ml, g, kg, cnt или tens);
*   pr<sub>i</sub> f<sub>i</sub> ch<sub>i</sub> fv<sub>i</sub> — содержание белков, жиров, 
углеводов и энергетическая ценность ингредиента соответственно, заданные вещественными числами 
с не более чем шестью знаками после запятой (0 ⩽ pr<sub>i</sub>, f<sub>i</sub>, ch<sub>i</sub> 
⩽ 1000, 0 ⩽ fv<sub>i</sub> ⩽ 10 000).

Гарантируется, что:  

*   в каталогах перечислены все ингредиенты, необходимые для приготовления блюд;
*   не существует двух блюд с одинаковым названием;
*   не существует двух ингредиентов в одном каталоге с одинаковым названием;
*   не существует двух ингредиентов в одном блюде с одинаковым названием;
*   для любых двух упоминаний ингредиента единицы измерения, в которых заданы его количества,
можно перевести друг в друга.

#### Выходные данные

Первая строка должна содержать одно целое число: сумма, которую нужно потратить Васе на 
подготовку к празднику.  

Далее должны следовать k строк, в каждой из которых через пробел указано название ингредиента 
и целое число — количество упаковок, которое необходимо купить. Ингредиенты, выведенные в этих 
k строках, должны соответствовать ингредиентам, описанным в первом справочнике.  

В следующих n строках через пробел должны быть указаны название блюда и его характеристики, 
описанные четырьмя вещественными числами: белки, жиры, углеводы и энергетическая ценность.  

Ингредиенты и блюда разрешается выводить в любом порядке.  

Ваш ответ будет считаться правильным, если все целые числа совпадают с соответствующими числами 
в ответе жюри, а для всех вещественных чисел в ответе их абсолютная или относительная погрешность 
не превосходит 10<sup>-3</sup>. Более формально, пусть вещественное число в вашем ответе равно A, 
а соответствующее число в ответе жюри равно B. Тогда число A будет считаться корректным, если 
<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-1-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mfrac><mrow><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mi>A</mi><mo>−</mo><mi>B</mi><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow></mrow><mrow><mi>m</mi><mi>a</mi><mi>x</mi><mo stretchy="false">(</mo><mn>1</mn><mo>,</mo><mi>B</mi><mo stretchy="false">)</mo></mrow></mfrac><mo>⩽</mo><msup><mn>10</mn><mrow class="MJX-TeXAtom-ORD"><mo>−</mo><mn>3</mn></mrow></msup></math></span><mfrac><mrow><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mi>A</mi><mo>&amp;#x2212;</mo><mi>B</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow></mrow><mrow><mi>m</mi><mi>a</mi><mi>x</mi><mo stretchy=&quot;false&quot;>(</mo><mn>1</mn><mo>,</mo><mi>B</mi><mo stretchy=&quot;false&quot;>)</mo></mrow></mfrac><mo>&amp;#x2A7D;</mo><msup><mn>10</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x2212;</mo><mn>3</mn></mrow></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-1">\frac{|A - B|}{max(1,B)}⩽10^{-3}</script>.  

#### Пример

<div class="scrollable-table">

<table>

<tr>

<th>Входные данные</th>

<th>Выходные данные</th>

</tr>

<tr>

<td>
<pre>
2
sandwich 7 3
butter 10 g
toasted_bread 2 cnt
sausage 30 g
omelet 9 4
egg 4 cnt
milk 120 ml
salt 1 g
sausage 50 g
7
egg 61 1 tens
milk 58 1 l
sausage 100 480 g
butter 120 180 g
cream 100 350 g
salt 14 1000 g
toasted_bread 40 20 cnt
8
egg 1 cnt 13 12 1 16.4
milk 1 l 3 4.5 4.7 60
chocolate 90 g 6.8 36.3 47.1 546
salt 1 kg 0 0 0 0
strawberry 100 g 0.4 0.1 7 35
sausage 100 g 10 18 1.5 210
toasted_bread 5 cnt 7.3 1.6 52.3 248
butter 100 g 0.8 72.5 1.3 661
</pre>
</td>

<td>
<pre>
734  
egg 4  
milk 2  
sausage 2  
butter 1  
cream 0  
salt 1  
toasted_bread 1  
sandwich 6.00 13.29 21.50 228.3  
omelet 57.360 57.540 5.314 177.800
</pre>
</td>

</tr>

</table>

</div>

#### Примечание

В первом примере Васе необходимо приготовить 7 бутербродов и 9 омлетов.  

Для приготовления всех первых блюд необходимо 10 ⋅ 7 грамм масла, 2 1 7 кусочков хлеба и 
30 ⋅ 7 грамм колбасы. В каждом из бутерброде будет содержаться 
<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-2-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0.8</mn><mo>⋅</mo><mfrac><mn>10</mn><mn>100</mn></mfrac><mo>+</mo><mn>7.3</mn><mo>⋅</mo><mfrac><mn>2</mn><mn>5</mn></mfrac><mo>+</mo><mn>10</mn><mo>⋅</mo><mfrac><mn>30</mn><mn>100</mn></mfrac><mo>=</mo><mn>6</mn></math></span><mn>0.8</mn><mo>&amp;#x22C5;</mo><mfrac><mn>10</mn><mn>100</mn></mfrac><mo>+</mo><mn>7.3</mn><mo>&amp;#x22C5;</mo><mfrac><mn>2</mn><mn>5</mn></mfrac><mo>+</mo><mn>10</mn><mo>&amp;#x22C5;</mo><mfrac><mn>30</mn><mn>100</mn></mfrac><mo>=</mo><mn>6</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-2">0.8 ⋅ \frac {10}{100} + 7.3 ⋅ \frac {2}{5} + 10 ⋅ \frac {30}{100} =6</script> грамм белков, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-3-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>72.5</mn><mo>⋅</mo><mfrac><mn>10</mn><mn>100</mn></mfrac><mo>+</mo><mn>1.6</mn><mo>⋅</mo><mfrac><mn>2</mn><mn>5</mn></mfrac><mo>+</mo><mn>18</mn><mo>⋅</mo><mfrac><mn>30</mn><mn>100</mn></mfrac><mo>=</mo><mn>13.29</mn></math></span><mn>72.5</mn><mo>&amp;#x22C5;</mo><mfrac><mn>10</mn><mn>100</mn></mfrac><mo>+</mo><mn>1.6</mn><mo>&amp;#x22C5;</mo><mfrac><mn>2</mn><mn>5</mn></mfrac><mo>+</mo><mn>18</mn><mo>&amp;#x22C5;</mo><mfrac><mn>30</mn><mn>100</mn></mfrac><mo>=</mo><mn>13.29</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-3">72.5 ⋅ \frac {10}{100} + 1.6 ⋅ \frac {2}{5} + 18 ⋅ \frac {30}{100} =13.29</script> грамм жиров и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-4-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1.3</mn><mo>⋅</mo><mfrac><mn>10</mn><mn>100</mn></mfrac><mo>+</mo><mn>52.3</mn><mo>⋅</mo><mfrac><mn>2</mn><mn>5</mn></mfrac><mo>+</mo><mn>1.5</mn><mo>⋅</mo><mfrac><mn>30</mn><mn>100</mn></mfrac><mo>=</mo><mn>21.5</mn></math></span><mn>1.3</mn><mo>&amp;#x22C5;</mo><mfrac><mn>10</mn><mn>100</mn></mfrac><mo>+</mo><mn>52.3</mn><mo>&amp;#x22C5;</mo><mfrac><mn>2</mn><mn>5</mn></mfrac><mo>+</mo><mn>1.5</mn><mo>&amp;#x22C5;</mo><mfrac><mn>30</mn><mn>100</mn></mfrac><mo>=</mo><mn>21.5</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-4">1.3 ⋅ \frac {10}{100} + 52.3 ⋅ \frac {2}{5} + 1.5 ⋅ \frac {30}{100} =21.5</script> грамм углеводов. Энергетическаая ценность составит <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-5-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><svg xmlns:xlink="http://www.w3.org/1999/xlink" width="41.526ex" height="3.383ex" style="vertical-align: -1.089ex;" viewBox="0 -987.6 17879.3 1456.5" role="img" focusable="false" aria-hidden="true"><g stroke="currentColor" fill="currentColor" stroke-width="0" transform="matrix(1 0 0 -1 0 0)"><g transform="translate(16291,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">к</text></g><g transform="translate(16694,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">к</text></g><g transform="translate(17096,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">а</text></g><g transform="translate(17465,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">л</text></g></g></svg><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>661</mn><mo>⋅</mo><mfrac><mn>10</mn><mn>100</mn></mfrac><mo>+</mo><mn>248</mn><mo>⋅</mo><mfrac><mn>2</mn><mn>5</mn></mfrac><mo>+</mo><mn>210</mn><mo>⋅</mo><mfrac><mn>30</mn><mn>100</mn></mfrac><mo>=</mo><mn>228.3</mn><mrow class="MJX-TeXAtom-ORD"><mo>к</mo></mrow><mrow class="MJX-TeXAtom-ORD"><mo>к</mo></mrow><mrow class="MJX-TeXAtom-ORD"><mo>а</mo></mrow><mrow class="MJX-TeXAtom-ORD"><mo>л</mo></mrow></math></span><mn>661</mn><mo>&amp;#x22C5;</mo><mfrac><mn>10</mn><mn>100</mn></mfrac><mo>+</mo><mn>248</mn><mo>&amp;#x22C5;</mo><mfrac><mn>2</mn><mn>5</mn></mfrac><mo>+</mo><mn>210</mn><mo>&amp;#x22C5;</mo><mfrac><mn>30</mn><mn>100</mn></mfrac><mo>=</mo><mn>228.3</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x43A;</mo></mrow><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x43A;</mo></mrow><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x430;</mo></mrow><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x43B;</mo></mrow></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-5">661 ⋅ \frac {10}{100} + 248 ⋅ \frac {2}{5} + 210 ⋅ \frac {30}{100} =228.3 ккал</script>.  

Для приготовления всех вторых блюд необходимо 4 ⋅ 9 = 36 яиц, 120 ⋅ 9 = 1080 миллилитров молока, 
9 грамм соли, 50 ⋅ 9 = 450 грамм колбасы. В каждом омлете будет содержаться 
<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-6-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>13</mn><mo>⋅</mo><mn>4</mn><mo>+</mo><mn>3</mn><mo>⋅</mo><mfrac><mn>120</mn><mn>1000</mn></mfrac><mo>+</mo><mn>10</mn><mo>⋅</mo><mfrac><mn>50</mn><mn>100</mn></mfrac><mo>=</mo><mn>57.36</mn></math></span><mn>13</mn><mo>&amp;#x22C5;</mo><mn>4</mn><mo>+</mo><mn>3</mn><mo>&amp;#x22C5;</mo><mfrac><mn>120</mn><mn>1000</mn></mfrac><mo>+</mo><mn>10</mn><mo>&amp;#x22C5;</mo><mfrac><mn>50</mn><mn>100</mn></mfrac><mo>=</mo><mn>57.36</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-6">13 ⋅ 4+ 3 ⋅ \frac {120}{1000} + 10 ⋅ \frac {50}{100} =57.36</script> грамм белков, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-7-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><svg xmlns:xlink="http://www.w3.org/1999/xlink" width="40.917ex" height="3.383ex" style="vertical-align: -1.089ex;" viewBox="0 -987.6 17617.1 1456.5" role="img" focusable="false" aria-hidden="true"><g stroke="currentColor" fill="currentColor" stroke-width="0" transform="matrix(1 0 0 -1 0 0)"><g transform="translate(15375,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">ж</text></g><g transform="translate(15948,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">и</text></g><g transform="translate(16392,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">р</text></g><g transform="translate(16810,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">о</text></g><g transform="translate(17225,0)"><text font-family="STIXGeneral,'Arial Unicode MS',serif" stroke="none" transform="scale(51.874) matrix(1 0 0 -1 0 0)">в</text></g></g></svg><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>12</mn><mo>⋅</mo><mn>4</mn><mo>+</mo><mn>4.5</mn><mo>⋅</mo><mfrac><mn>120</mn><mn>1000</mn></mfrac><mo>+</mo><mn>18</mn><mo>⋅</mo><mfrac><mn>50</mn><mn>100</mn></mfrac><mo>=</mo><mn>57</mn><mo>,</mo><mn>54</mn><mrow class="MJX-TeXAtom-ORD"><mo>ж</mo></mrow><mrow class="MJX-TeXAtom-ORD"><mo>и</mo></mrow><mrow class="MJX-TeXAtom-ORD"><mo>р</mo></mrow><mrow class="MJX-TeXAtom-ORD"><mo>о</mo></mrow><mrow class="MJX-TeXAtom-ORD"><mo>в</mo></mrow></math></span><mn>12</mn><mo>&amp;#x22C5;</mo><mn>4</mn><mo>+</mo><mn>4.5</mn><mo>&amp;#x22C5;</mo><mfrac><mn>120</mn><mn>1000</mn></mfrac><mo>+</mo><mn>18</mn><mo>&amp;#x22C5;</mo><mfrac><mn>50</mn><mn>100</mn></mfrac><mo>=</mo><mn>57</mn><mo>,</mo><mn>54</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x436;</mo></mrow><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x438;</mo></mrow><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x440;</mo></mrow><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x43E;</mo></mrow><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo>&amp;#x432;</mo></mrow></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-7">12 ⋅ 4+ 4.5 ⋅ \frac {120}{1000} + 18 ⋅ \frac {50}{100} =57,54 жиров</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-8-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>⋅</mo><mn>4</mn><mo>+</mo><mn>4.7</mn><mo>⋅</mo><mfrac><mn>120</mn><mn>1000</mn></mfrac><mo>+</mo><mn>1.5</mn><mo>⋅</mo><mfrac><mn>50</mn><mn>100</mn></mfrac><mo>=</mo><mn>5.314</mn></math></span><mn>1</mn><mo>&amp;#x22C5;</mo><mn>4</mn><mo>+</mo><mn>4.7</mn><mo>&amp;#x22C5;</mo><mfrac><mn>120</mn><mn>1000</mn></mfrac><mo>+</mo><mn>1.5</mn><mo>&amp;#x22C5;</mo><mfrac><mn>50</mn><mn>100</mn></mfrac><mo>=</mo><mn>5.314</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-8">1 ⋅ 4+ 4.7 ⋅ \frac {120}{1000} + 1.5 ⋅ \frac {50}{100} =5.314</script> углеводов. Энергетическая ценность составит <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-9-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>16</mn><mo>⋅</mo><mn>4</mn><mo>+</mo><mn>60</mn><mo>⋅</mo><mfrac><mn>120</mn><mn>1000</mn></mfrac><mo>+</mo><mn>210</mn><mo>⋅</mo><mfrac><mn>50</mn><mn>100</mn></mfrac><mo>=</mo><mn>177.8</mn></math></span><mn>16</mn><mo>&amp;#x22C5;</mo><mn>4</mn><mo>+</mo><mn>60</mn><mo>&amp;#x22C5;</mo><mfrac><mn>120</mn><mn>1000</mn></mfrac><mo>+</mo><mn>210</mn><mo>&amp;#x22C5;</mo><mfrac><mn>50</mn><mn>100</mn></mfrac><mo>=</mo><mn>177.8</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-9">16 ⋅ 4+ 60 ⋅ \frac {120}{1000} + 210 ⋅ \frac {50}{100} =177.8</script> ккал.  

Всего необходимо 70 грамм масла, 36 яиц, 1080 литров молока, 9 грамм соли, 210 + 450 = 660 грамм 
колбасы и 14 кусочков тостового хлеба.  

Таким образом, в магазине нужно купить одну упаковку масла, 4 десятка яиц, 2 упаковки колбасы и 
молока, по одной упаковке соли и тостового хлеба, заплатив 
120 + 61 ⋅ 4 + 100 ⋅ 2 + 58 ⋅ 2 + 14 + 40 = 734 рубля.  

<a name="ar"></a>

<a name="b"></a>

## B. Закрытый ключ

|||
|--------------------------------|-------------------|
| Ограничение по времени на тест | 2 с               |
| Ограничение по памяти на тест  | 256 МБ            |
| Ввод                           | стандартный ввод  |
| Вывод                          | стандартный вывод |

Во всех крупных IT-компаниях немалое внимание уделяется вопросам информационной безопасности, и 
Яндекс  — не исключение.

Дима и Егор разрабатывают новый сервис YD (Yandex Dorogi) и в данный момент проводят аудит его 
безопасности. Для шифрования пользовательских данных в YD используется алгоритм шифрования с 
открытым ключом YS (Yandex Shifrovatel).

Схема работы YS такова: для каждого сервиса генерируется закрытый ключ 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-11-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi><mo>,</mo><mi>q</mi></math></span><mi>p</mi><mo>,</mo><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-11">p, q</script>), где <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-12-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi></math></span><mi>p</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-12">p</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-13-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-13">q</script> — натуральные числа. По закрытому ключу (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-14-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi><mo>,</mo><mi>q</mi></math></span><mi>p</mi><mo>,</mo><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-14">p, q</script>) генерируется открытый ключ (НОД(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-15-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi><mo>,</mo><mi>q</mi></math></span><mi>p</mi><mo>,</mo><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-15">p, q</script>), НОК(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-16-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi><mo>,</mo><mi>q</mi></math></span><mi>p</mi><mo>,</mo><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-16">p, q</script>)), 
который доступен всем пользователям. Если злоумышленник сможет по открытому ключу получить 
закрытый ключ, то он получит доступ ко всем данным YD и принесет сервису непоправимый вред. 
Конечно же, Егор и Дима не могут этого допустить, поэтому они хотят сделать так, чтобы 
злоумышленнику пришлось перебрать очень много вариантов открытого ключа, прежде чем он сможет 
его угадать.

Дима уже сгенерировал закрытый ключ для YD и получил на его основе открытый ключ 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-17-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>,</mo><mi>y</mi></math></span><mi>x</mi><mo>,</mo><mi>y</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-17">x, y</script>). 
Егору сразу же стало интересно, сколько вариантов закрытого ключа придется перебрать 
злоумышленнику для взлома YD в худшем случае, иными словами, сколько существует закрытых ключей 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-18-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi><mo>,</mo><mi>q</mi></math></span><mi>p</mi><mo>,</mo><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-18">p, q</script>) 
таких, что открытым ключом для них является 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-19-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>,</mo><mi>y</mi></math></span><mi>x</mi><mo>,</mo><mi>y</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-19">x, y</script>). 
К сожалению, у Егора есть много других задач, очень важных для запуска YD, поэтому он просит вас 
вычислить это количество за него.

#### Входные данные

В первой строке содержатся два целых числа 
<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-20-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-20">x</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-21-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi></math></span><mi>y</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-21">y</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-22-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><mi>x</mi><mo>≤</mo><mi>y</mi><mo>≤</mo><msup><mn>10</mn><mrow class="MJX-TeXAtom-ORD"><mn>12</mn></mrow></msup></math></span><mn>1</mn><mo>&amp;#x2264;</mo><mi>x</mi><mo>&amp;#x2264;</mo><mi>y</mi><mo>&amp;#x2264;</mo><msup><mn>10</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mn>12</mn></mrow></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-22">1 \leq x \leq y \leq 10^{12}</script>) — описание открытого ключа.

#### Выходные данные

Выведите одно целое число — количество закрытых ключей, для которых данный ключ является открытым.

#### Примеры

Входные данные

```
5 10
```

Выходные данные

```
2
```

Входные данные

```
10 11
```

Выходные данные

```
0
```

Входные данные

```
527 9486
```

Выходные данные

```
4
```

#### Примечание

В первом примере существует два закрытых ключа, для которых 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-23-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>5</mn><mo>,</mo><mn>10</mn></math></span><mn>5</mn><mo>,</mo><mn>10</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-23">5, 10</script>) является открытым ключом: (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-24-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>5</mn><mo>,</mo><mn>10</mn></math></span><mn>5</mn><mo>,</mo><mn>10</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-24">5, 10</script>) 
и 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-25-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>10</mn><mo>,</mo><mn>5</mn></math></span><mn>10</mn><mo>,</mo><mn>5</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-25">10, 5</script>).

Во втором примере Дима ошибся, потому что ни один закрытый ключ не порождает открытый ключ 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-26-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>10</mn><mo>,</mo><mn>11</mn></math></span><mn>10</mn><mo>,</mo><mn>11</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-26">10, 11</script>).

В третьем примере подходящими закрытыми ключами являются 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-27-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>527</mn><mo>,</mo><mn>9486</mn></math></span><mn>527</mn><mo>,</mo><mn>9486</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-27">527, 9486</script>), 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-28-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1054</mn><mo>,</mo><mn>4743</mn></math></span><mn>1054</mn><mo>,</mo><mn>4743</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-28">1054, 4743</script>), 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-29-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>4743</mn><mo>,</mo><mn>1054</mn></math></span><mn>4743</mn><mo>,</mo><mn>1054</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-29">4743, 1054</script>), 
(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-30-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>9486</mn><mo>,</mo><mn>527</mn></math></span><mn>9486</mn><mo>,</mo><mn>527</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-30">9486, 527</script>).

НОД (наибольшим общим делителем) двух натуральных чисел <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-31-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi></math></span><mi>p</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-31">p</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-32-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-32">q</script> называется наибольшее число <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-33-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-33">k</script> такое, что <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-34-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi></math></span><mi>p</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-34">p</script> делится на <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-35-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-35">k</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-36-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-36">q</script> делится на <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-37-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-37">k</script>. Например, НОД(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-38-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>6</mn><mo>,</mo><mn>15</mn></math></span><mn>6</mn><mo>,</mo><mn>15</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-38">6, 15</script>) равен <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-39-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-39">3</script>, а НОД(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-40-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>16</mn><mo>,</mo><mn>8</mn></math></span><mn>16</mn><mo>,</mo><mn>8</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-40">16, 8</script>) равен <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-41-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>8</mn></math></span><mn>8</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-41">8</script>.

НОК (наименьшим общим кратным) двух натуральных чисел <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-42-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi></math></span><mi>p</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-42">p</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-43-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-43">q</script> называется наименьшее число <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-44-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-44">k</script> такое, что <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-45-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-45">k</script> делится на <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-46-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi></math></span><mi>p</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-46">p</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-47-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-47">k</script> делится на <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-48-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-48">q</script>. Например, НОК(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-49-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn><mo>,</mo><mn>3</mn></math></span><mn>2</mn><mo>,</mo><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-49">2, 3</script>) равен <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-50-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>6</mn></math></span><mn>6</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-50">6</script>, а НОК(<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-51-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>10</mn><mo>,</mo><mn>20</mn></math></span><mn>10</mn><mo>,</mo><mn>20</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-51">10, 20</script>) равен 20.

<a name="br"></a>

<a name="c"></a>

## C. Программист на пляже

<div class="scrollable-table">

<table>

<tbody>

<tr>

<td></td>

<td>Все языки</td>

<td>Python</td>

<td>Java</td>

</tr>

<tr>

<td>Ограничение по времени на тест</td>

<td>2 с</td>

<td colspan="2">3 c</td>

</tr>

<tr>

<td>Ограничение по памяти на тест</td>

<td colspan="3">256 МБ</td>

</tr>

<tr>

<td>Ввод</td>

<td colspan="3">стандартный ввод</td>

</tr>

<tr>

<td>Вывод</td>

<td colspan="3">стандартный вывод</td>

</tr>

</tbody>

</table>

</div>

Однажды программист Алексей из Яндекса взял отпуск и уехал отдыхать на море. В один из дней он пошел на пляж, причем пошел туда не один. Возможно, он пошел туда с мамой, возможно, с бабушкой, а, возможно, с другом или подругой. Важно, что пошел он туда не один.

На пляже программист Алексей обнаружил, что осталось всего <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-99-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-99">n</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-100-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn><mo>≤</mo><mi>n</mi><mo>≤</mo><msup><mn>10</mn><mn>6</mn></msup></math></span><mn>2</mn><mo>&amp;#x2264;</mo><mi>n</mi><mo>&amp;#x2264;</mo><msup><mn>10</mn><mn>6</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-100">2 \leq n \leq 10^6</script>) свободных лежаков. Но среди всего этого множества лежаков программисту Алексею нужно было всего лишь 2: для него самого и для того (или той), с кем он пришел. Так как программист Алексей очень любил порядок, то он хотел, чтобы лежаки были как можно более похожи друг на друга. Похожесть лежаков можно вычислить следующим образом:

*   Каждому лежаку каким-то образом по его внешним признакам назначается некоторое число <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-101-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>a</mi><mi>i</mi></msub></math></span><msub><mi>a</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-101">a_i</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-102-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><mi>i</mi><mo>≤</mo><mi>n</mi></math></span><mn>1</mn><mo>&amp;#x2264;</mo><mi>i</mi><mo>&amp;#x2264;</mo><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-102">1 \leq i \leq n</script>, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-103-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn><mo>≤</mo><msub><mi>a</mi><mi>i</mi></msub><mo>≤</mo><msup><mn>10</mn><mn>9</mn></msup></math></span><mn>0</mn><mo>&amp;#x2264;</mo><msub><mi>a</mi><mi>i</mi></msub><mo>&amp;#x2264;</mo><msup><mn>10</mn><mn>9</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-103">0 \leq a_i \leq 10^9</script>).
*   Затем непохожесть двух лежаков вычисляется как XOR (побитовое исключающее ИЛИ) чисел назначенных этим лежакам. Чем значение непохожести меньше, тем более похожи лежаки.

Помогите программисту Алексею понять, какого минимального значения непохожести лежаков он может достичь, сравнив попарно все свободные лежаки.

#### Входные данные

В первой строке задано число <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-104-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>T</mi></math></span><mi>T</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-104">T</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-105-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><mi>T</mi><mo>≤</mo><mn>1000</mn></math></span><mn>1</mn><mo>&amp;#x2264;</mo><mi>T</mi><mo>&amp;#x2264;</mo><mn>1000</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-105">1 \leq T \leq 1000</script>) – количество тестов. Каждый тест состоит из двух строк.

В первой строке каждого теста задано число <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-106-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-106">n</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-107-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn><mo>≤</mo><mi>n</mi><mo>≤</mo><msup><mn>10</mn><mn>6</mn></msup></math></span><mn>2</mn><mo>&amp;#x2264;</mo><mi>n</mi><mo>&amp;#x2264;</mo><msup><mn>10</mn><mn>6</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-107">2 \leq n \leq 10^6</script>) – количество лежаков.

Во второй строке каждого теста заданы <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-108-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-108">n</script> чисел <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-109-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>a</mi><mi>i</mi></msub></math></span><msub><mi>a</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-109">a_i</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-110-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><mi>i</mi><mo>≤</mo><mi>n</mi></math></span><mn>1</mn><mo>&amp;#x2264;</mo><mi>i</mi><mo>&amp;#x2264;</mo><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-110">1 \leq i \leq n</script>, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-111-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn><mo>≤</mo><msub><mi>a</mi><mi>i</mi></msub><mo>≤</mo><msup><mn>10</mn><mn>9</mn></msup></math></span><mn>0</mn><mo>&amp;#x2264;</mo><msub><mi>a</mi><mi>i</mi></msub><mo>&amp;#x2264;</mo><msup><mn>10</mn><mn>9</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-111">0 \leq a_i \leq 10^9</script>) – значения, которые были поставлены лежакам в соответствие по внешним признакам.

Сумма <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-112-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-112">n</script> по всем тестам не превосходит <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-113-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mn>10</mn><mn>6</mn></msup></math></span><msup><mn>10</mn><mn>6</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-113">10^6</script>.

#### Выходные данные

Для каждого теста выведите по одной строке, в которой должно быть единственное число – минимальное значение непохожести.

#### Примеры

Входные данные

```
1
5
1 2 4 8 16
```

Выходные данные

```
3
```

Входные данные

```
2
2
2 4
4
2 4 6 8
```

Выходные данные

```
6
2
```

#### Примечание

В первом примере Алексей выберет лежаки со значениями 1 и 2.

В первой части второго примера Алексей может взять только лежаки со значениями 2 и 4\. Во второй части он выберет лежаки со значениями 4 и 6.

<a name="cr"></a>

<a name="d"></a>

## D. Перемещение чанков

<div class="scrollable-table">

<table>

<tbody>

<tr>

<td></td>

<td>Все языки</td>

<td>Python</td>

<td>Java</td>

</tr>

<tr>

<td>Ограничение по времени на тест</td>

<td>1 с</td>

<td>5 c</td>

<td>1 с</td>

</tr>

<tr>

<td>Ограничение по памяти на тест</td>

<td colspan="3">256 МБ</td>

</tr>

<tr>

<td>Ввод</td>

<td colspan="3">стандартный ввод</td>

</tr>

<tr>

<td>Вывод</td>

<td colspan="3">стандартный вывод</td>

</tr>

</tbody>

</table>

</div>

Хранение данных в распределенном хранилище является крайне сложной задачей, однако инженеры Яндекса успешно с ней справляются.

Один из кластеров хранилища состоит из <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-130-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi></math></span><mi>m</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-130">m</script> серверов, на которых хранятся данные, разбитые на <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-131-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-131">n</script> чанков. Для дефрагментации кластера и возможности отключения старых серверов чанки периодически приходится перемещать между серверами. Перемещение чанков по одному неэффективно, поэтому они перемещают группами. Запрос на перемещение описывается четырьмя числами <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-132-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>b</mi><mo>,</mo><mi>l</mi><mo>,</mo><mi>r</mi></math></span><mi>a</mi><mo>,</mo><mi>b</mi><mo>,</mo><mi>l</mi><mo>,</mo><mi>r</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-132">a, b, l, r</script> и обозначает заказ на перемещение всех чанков с номерами от <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-133-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>l</mi></math></span><mi>l</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-133">l</script> до <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-134-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></span><mi>r</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-134">r</script> включительно с сервера с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-135-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></span><mi>a</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-135">a</script> на сервер с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-136-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></span><mi>b</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-136">b</script>. После перемещения соотвествующие чанки с сервера с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-137-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></span><mi>a</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-137">a</script> стираются. Таким образом, каждый чанк находится всегда ровно на одном сервере.

При построении распределенных систем очень важно избегать возможности конфликта изменений на кластере. Перед выполнением каждого из запросов необходимо убедиться, что все чанки, участвующие в запросе, находятся на ожидаемом сервере. Иными словами, перед выполнением запроса, описываемого параметрами <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-138-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>b</mi><mo>,</mo><mi>l</mi><mo>,</mo><mi>r</mi></math></span><mi>a</mi><mo>,</mo><mi>b</mi><mo>,</mo><mi>l</mi><mo>,</mo><mi>r</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-138">a, b, l, r</script>, необходимо убедиться, что все чанки с номерами от <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-139-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>l</mi></math></span><mi>l</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-139">l</script> до <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-140-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></span><mi>r</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-140">r</script> включительно расположены на сервере с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-141-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></span><mi>a</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-141">a</script>. В случае, если это неверно, запрос на перемещение чанков отменяется и система переходит к обработке следующего запроса. Если же это верно, то запрос осуществляется и все чанки от <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-142-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>l</mi></math></span><mi>l</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-142">l</script> до <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-143-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>r</mi></math></span><mi>r</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-143">r</script> включительно перемещаются с сервера <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-144-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></span><mi>a</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-144">a</script> на сервер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-145-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></span><mi>b</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-145">b</script>.

По заданному начальному состоянию кластера и списку запросов перемещения чанков определите, какие запросы будут выполнены.

#### Входные данные

В первой строке заданы три целых числа <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-146-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>,</mo><mi>m</mi></math></span><mi>n</mi><mo>,</mo><mi>m</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-146">n, m</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-147-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-147">q</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-148-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><mi>n</mi><mo>,</mo><mi>q</mi><mo>≤</mo><mn>100</mn><mn>000</mn><mo>,</mo><mn>2</mn><mo>≤</mo><mi>m</mi><mo>≤</mo><mn>100</mn><mn>000</mn></math></span><mn>1</mn><mo>&amp;#x2264;</mo><mi>n</mi><mo>,</mo><mi>q</mi><mo>&amp;#x2264;</mo><mn>100</mn><mspace width=&quot;thinmathspace&quot; /><mn>000</mn><mo>,</mo><mn>2</mn><mo>&amp;#x2264;</mo><mi>m</mi><mo>&amp;#x2264;</mo><mn>100</mn><mspace width=&quot;thinmathspace&quot; /><mn>000</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-148">1 \leq n, q \leq 100\,000, 2 \leq m \leq 100\,000</script>) — количество чанков на кластере, количество серверов, на которых располагаются чанки, и количество запросов, соответственно.

Во второй строке содержатся <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-149-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-149">n</script> чисел <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-150-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>p</mi><mi>i</mi></msub></math></span><msub><mi>p</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-150">p_i</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-151-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><msub><mi>p</mi><mi>i</mi></msub><mo>≤</mo><mi>m</mi></math></span><mn>1</mn><mo>&amp;#x2264;</mo><msub><mi>p</mi><mi>i</mi></msub><mo>&amp;#x2264;</mo><mi>m</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-151">1 \leq p_i \leq m</script>), <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-152-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></span><mi>i</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-152">i</script>-е из которых обозначает номер сервера, где изначально располагается чанк с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-153-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></span><mi>i</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-153">i</script>.

В следующих <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-154-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-154">q</script> строках содержатся описания запросов перемещения чанков в хронологическом порядке.

Каждый запрос описывается четверкой чисел <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-155-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><msub><mi>b</mi><mi>i</mi></msub><mo>,</mo><msub><mi>l</mi><mi>i</mi></msub><mo>,</mo><msub><mi>r</mi><mi>i</mi></msub></math></span><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><msub><mi>b</mi><mi>i</mi></msub><mo>,</mo><msub><mi>l</mi><mi>i</mi></msub><mo>,</mo><msub><mi>r</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-155">a_i, b_i, l_i, r_i</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-156-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><msub><mi>b</mi><mi>i</mi></msub><mo>≤</mo><mi>m</mi><mo>,</mo><msub><mi>a</mi><mi>i</mi></msub><mo>≠</mo><msub><mi>b</mi><mi>i</mi></msub><mo>,</mo><mn>1</mn><mo>≤</mo><msub><mi>l</mi><mi>i</mi></msub><mo>≤</mo><msub><mi>r</mi><mi>i</mi></msub><mo>≤</mo><mi>n</mi></math></span><mn>1</mn><mo>&amp;#x2264;</mo><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><msub><mi>b</mi><mi>i</mi></msub><mo>&amp;#x2264;</mo><mi>m</mi><mo>,</mo><msub><mi>a</mi><mi>i</mi></msub><mo>&amp;#x2260;</mo><msub><mi>b</mi><mi>i</mi></msub><mo>,</mo><mn>1</mn><mo>&amp;#x2264;</mo><msub><mi>l</mi><mi>i</mi></msub><mo>&amp;#x2264;</mo><msub><mi>r</mi><mi>i</mi></msub><mo>&amp;#x2264;</mo><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-156">1 \leq a_i, b_i \leq m, a_i \neq b_i, 1 \leq l_i \leq r_i \leq n</script>) и обозначает заказ на перемещение чанков с номерами с <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-157-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>l</mi><mi>i</mi></msub></math></span><msub><mi>l</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-157">l_i</script> по <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-158-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>r</mi><mi>i</mi></msub></math></span><msub><mi>r</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-158">r_i</script> (включительно) с сервера <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-159-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>a</mi><mi>i</mi></msub></math></span><msub><mi>a</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-159">a_i</script> на сервер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-160-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>b</mi><mi>i</mi></msub></math></span><msub><mi>b</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-160">b_i</script>.

#### Выходные данные

Выведите <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-161-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-161">q</script> строк. В строке с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-162-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></span><mi>i</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-162">i</script> выведите <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-163-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-163">1</script>, если запрос с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-164-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></span><mi>i</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-164">i</script> будет выполнен, и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-165-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn></math></span><mn>0</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-165">0</script>, если нет.

#### Примеры

Входные данные

```
1 2 1
1
1 2 1 1
```

Выходные данные

```
1
```

Входные данные

```
1 2 1
1
2 1 1 1
```

Выходные данные

```
0
```

Входные данные

```
5 5 6
1 2 3 4 5
1 2 1 1
2 3 1 3
4 2 4 4
2 5 1 4
3 2 2 3
3 2 3 3
```

Выходные данные

```
1
0
1
0
0
1
```

#### Примечание

Рассмотрим третий пример. Изначально расположение чанков на серверах описывается массивом <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-166-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>1</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo>,</mo><mn>4</mn><mo>,</mo><mn>5</mn><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mn>1</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo>,</mo><mn>4</mn><mo>,</mo><mn>5</mn><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-166">[1, 2, 3, 4, 5]</script>.

В первом запросе требуется переместить чанк с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-167-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-167">1</script> с сервера <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-168-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-168">1</script> на сервер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-169-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-169">2</script>. Чанк с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-170-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-170">1</script> находится на сервере <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-171-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-171">1</script>, поэтому перемещение будет произведено. После выполнения запроса расположение чанков на серверах описывается массивом <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-172-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo>,</mo><mn>4</mn><mo>,</mo><mn>5</mn><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo>,</mo><mn>4</mn><mo>,</mo><mn>5</mn><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-172">[2, 2, 3, 4, 5]</script>.

Во втором запросе требуется переместить чанки <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-173-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>,</mo><mn>2</mn></math></span><mn>1</mn><mo>,</mo><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-173">1, 2</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-174-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-174">3</script> с сервера <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-175-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-175">2</script> на сервер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-176-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-176">3</script>. Чанк <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-177-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-177">3</script> расположен не на сервере <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-178-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-178">2</script>, а на сервере <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-179-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-179">3</script>, поэтому операция не будет выполнена. Расположение чанков на серверах останется прежним.

В третьем запросе требуется переместить чанк <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-180-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>4</mn></math></span><mn>4</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-180">4</script> с сервера <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-181-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>4</mn></math></span><mn>4</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-181">4</script> на сервер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-182-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-182">2</script>. Чанк <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-183-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>4</mn></math></span><mn>4</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-183">4</script> находится на сервере <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-184-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>4</mn></math></span><mn>4</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-184">4</script>, поэтому перемещение будет произведено. После выполнения запроса расположение чанков на серверах будет описываться массивом <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-185-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>5</mn><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>5</mn><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-185">[2, 2, 3, 2, 5]</script>.

В четвертом запросе требуется переместить чанки <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-186-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn></math></span><mn>1</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-186">1, 2, 3</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-187-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>4</mn></math></span><mn>4</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-187">4</script> с сервера <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-188-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-188">2</script> на сервер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-189-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>5</mn></math></span><mn>5</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-189">5</script>. Так как чанк <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-190-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-190">3</script> расположен на сервере <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-191-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-191">3</script>, а не на сервере <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-192-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-192">2</script>, запрос не будет выполнен и расположение чанков останется прежним.

В пятом запросе требуется переместить чанки <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-193-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-193">2</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-194-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-194">3</script> с сервера <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-195-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-195">3</script> на сервер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-196-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-196">2</script>, но чанк <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-197-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-197">2</script> расположен на сервере <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-198-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-198">2</script>, поэтому запрос не будет выполнен и расположение чанков останется прежним.

В шестом запросе требуется переместить чанк <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-199-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-199">3</script> с сервера <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-200-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-200">3</script> на сервер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-201-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-201">2</script>. Чанк с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-202-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-202">3</script> находится на сервере <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-203-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-203">3</script>, поэтому перемещение будет произведено и расположение чанков станет описываться массивом <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-204-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>5</mn><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>5</mn><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-204">[2, 2, 2, 2, 5]</script>.

<a name="dr"></a>

<a name="e"></a>

## E. Разделение графа

<div class="scrollable-table">

<table>

<tbody>

<tr>

<td></td>

<td>Все языки</td>

<td>Python</td>

<td>Java</td>

</tr>

<tr>

<td>Ограничение по времени на тест</td>

<td>1 с</td>

<td>3 c</td>

<td>2 с</td>

</tr>

<tr>

<td>Ограничение по памяти на тест</td>

<td colspan="3">256 МБ</td>

</tr>

<tr>

<td>Ввод</td>

<td colspan="3">стандартный ввод</td>

</tr>

<tr>

<td>Вывод</td>

<td colspan="3">стандартный вывод</td>

</tr>

</tbody>

</table>

</div>

Дан взвешенный неориентированный граф <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-225-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>G</mi></math></span><mi>G</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-225">G</script>, содержащий <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-226-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-226">n</script> вершин и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-227-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi></math></span><mi>m</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-227">m</script> ребер.

Разбейте вершины графа на два не пустых множества так, чтобы ребро минимального веса, соединяющее вершины из одного множества, имело максимально большой вес.

Гарантируется, что граф не содержит петель и его нельзя разбить так, чтобы такого ребра не существовало.

#### Входные данные

В первой строке задано число вершин <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-228-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-228">n</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-229-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn><mo>≤</mo><mi>n</mi><mo>≤</mo><msup><mn>10</mn><mn>5</mn></msup></math></span><mn>3</mn><mo>&amp;#x2264;</mo><mi>n</mi><mo>&amp;#x2264;</mo><msup><mn>10</mn><mn>5</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-229">3 \leq n \leq 10^5</script>) и число ребер <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-230-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi></math></span><mi>m</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-230">m</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-231-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn><mo>≤</mo><mi>m</mi><mo>≤</mo><msup><mn>10</mn><mn>5</mn></msup></math></span><mn>3</mn><mo>&amp;#x2264;</mo><mi>m</mi><mo>&amp;#x2264;</mo><msup><mn>10</mn><mn>5</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-231">3\leq m \leq 10^5</script>) графа.

В следующих <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-232-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi></math></span><mi>m</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-232">m</script> строках заданы ребра в формате <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-233-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>u</mi></math></span><mi>u</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-233">u</script>, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-234-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>v</mi></math></span><mi>v</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-234">v</script>, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-235-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>w</mi></math></span><mi>w</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-235">w</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-236-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><mi>u</mi><mo>,</mo><mi>v</mi><mo>≤</mo><mi>n</mi></math></span><mn>1</mn><mo>&amp;#x2264;</mo><mi>u</mi><mo>,</mo><mi>v</mi><mo>&amp;#x2264;</mo><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-236">1\leq u, v \leq n</script>, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-237-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>u</mi><mo>≠</mo><mi>v</mi></math></span><mi>u</mi><mo>&amp;#x2260;</mo><mi>v</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-237">u\neq v</script>, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-238-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><mi>w</mi><mo>≤</mo><msup><mn>10</mn><mn>5</mn></msup></math></span><mn>1</mn><mo>&amp;#x2264;</mo><mi>w</mi><mo>&amp;#x2264;</mo><msup><mn>10</mn><mn>5</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-238">1 \leq w \leq 10^5</script>), где <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-239-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>u</mi></math></span><mi>u</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-239">u</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-240-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>v</mi></math></span><mi>v</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-240">v</script> задают начальную и конечную вершину ребра, а <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-241-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>w</mi></math></span><mi>w</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-241">w</script> — его вес.

#### Выходные данные

В единственной строке выведите максимальный возможный вес ребра, которое имеет минимальный вес среди тех, что соединяют вершины, принадлежащие одному множеству.

#### Примеры

Входные данные

<pre>3 4
1 2 1
1 2 2
1 3 3
3 2 4
</pre>

Выходные данные

<pre>4

</pre>

Входные данные

<pre>4 5
1 2 1
2 3 1
3 4 1
4 1 1
2 4 2
</pre>

Выходные данные

<pre>2
</pre>

#### Примечание

Рассмотрим первый пример из условия. В нем возможно всего 3 различных разбиения, удовлетворяющих условию, рассмотрим каждое из них:  

*   <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-242-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo fence="false" stretchy="false">{</mo><mo fence="false" stretchy="false">{</mo><mn>1</mn><mo>,</mo><mn>2</mn><mo fence="false" stretchy="false">}</mo><mo>,</mo><mo fence="false" stretchy="false">{</mo><mn>3</mn><mo fence="false" stretchy="false">}</mo><mo fence="false" stretchy="false">}</mo></math></span><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mn>1</mn><mo>,</mo><mn>2</mn><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo><mo>,</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mn>3</mn><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-242">\{\{1, 2\}, \{3\}\}</script>, в таком случае ребра <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-243-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-243">1</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-244-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>2</mn></math></span><mn>2</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-244">2</script> будут будут соединять вершины из одного множества, то есть ответ <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-245-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-245">1</script>;
*   <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-246-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo fence="false" stretchy="false">{</mo><mo fence="false" stretchy="false">{</mo><mn>1</mn><mo>,</mo><mn>3</mn><mo fence="false" stretchy="false">}</mo><mo>,</mo><mo fence="false" stretchy="false">{</mo><mn>2</mn><mo fence="false" stretchy="false">}</mo><mo fence="false" stretchy="false">}</mo></math></span><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mn>1</mn><mo>,</mo><mn>3</mn><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo><mo>,</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mn>2</mn><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-246">\{\{1, 3\}, \{2\}\}</script>, в таком случае только ребро <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-247-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-247">3</script> будет соединять вершины из одного множества, то есть ответ <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-248-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>3</mn></math></span><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-248">3</script>;
*   <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-249-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo fence="false" stretchy="false">{</mo><mo fence="false" stretchy="false">{</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo fence="false" stretchy="false">}</mo><mo>,</mo><mo fence="false" stretchy="false">{</mo><mn>1</mn><mo fence="false" stretchy="false">}</mo><mo fence="false" stretchy="false">}</mo></math></span><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo><mo>,</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mn>1</mn><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-249">\{\{2, 3\}, \{1\}\}</script>, в таком случае только ребро <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-250-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>4</mn></math></span><mn>4</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-250">4</script> будет соединять вершины из одного множества, то есть ответ <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-251-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>4</mn></math></span><mn>4</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-251">4</script>.

Получаем, что ответ на тест достигается при третьем варианте разбиения.

Во втором тесте ответ достигается на разбиении <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-252-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo fence="false" stretchy="false">{</mo><mo fence="false" stretchy="false">{</mo><mn>1</mn><mo>,</mo><mn>3</mn><mo fence="false" stretchy="false">}</mo><mo>,</mo><mo fence="false" stretchy="false">{</mo><mn>2</mn><mo>,</mo><mn>4</mn><mo fence="false" stretchy="false">}</mo><mo fence="false" stretchy="false">}</mo></math></span><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mn>1</mn><mo>,</mo><mn>3</mn><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo><mo>,</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>{</mo><mn>2</mn><mo>,</mo><mn>4</mn><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo><mo fence=&quot;false&quot; stretchy=&quot;false&quot;>}</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-252">\{\{1, 3\}, \{2, 4\}\}</script>. Легко убедиться, расписав все возможные разбиения, что не существует разбиения данного графа, на котором ответ был бы больше.

<a name="er"></a>

<div class="spoiler">**Решение**

<div class="spoiler_text">

Решить задачу можно с помощью бинарного поиска по ответу.

Предположим, что ответ — <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-253-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-253">x</script>. Тогда все ребра, вес которых меньше либо равен <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-254-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-254">x</script>, должны соединять вершины из разных множеств, то есть двудольным является граф, построенный на ребрах с весом, меньшим либо равным <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-255-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-255">x</script>. Покажем монотонность результата построения в зависимости от <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-256-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-256">x</script>. Так, если для некоторого <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-257-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-257">x</script> можно построить граф, удовлетворяющий условию, то граф можно построить и для всех <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-258-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi><mo><</mo><mi>x</mi></math></span><mi>y</mi><mo>&amp;lt;</mo><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-258">y < x</script>. Это следствие того, что для <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-259-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>y</mi></math></span><mi>y</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-259">y</script> можно взять такое же разбиение на множества, как и для <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-260-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-260">x</script>, а в таком случае ребра между вершинами из одного множества будут иметь вес, больше либо равный <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-261-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>></mo><mi>y</mi></math></span><mi>x</mi><mo>&amp;gt;</mo><mi>y</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-261">x > y</script>. Если же для некоторого <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-262-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-262">x</script> нельзя построить граф, удовлетворяющий условию, то его нельзя построить и для <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-263-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>z</mi><mo>></mo><mi>x</mi></math></span><mi>z</mi><mo>&amp;gt;</mo><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-263">z > x</script>, так как граф, построенный на ребрах весом меньше <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-264-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span><mi>x</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-264">x</script>, не является двудольным (то есть существует ребро между вершинами из одного множества), а добавлением ребер нельзя восстановить двудольность графа.

Теперь опишем проверку того, что граф удовлетворяет условию, то есть является двудольным. Для этого нужно запустить обход всех вершин (например, в глубину либо в ширину) для каждой компоненты связности. Во время обхода каждой вершине нужно поставить в соответствие <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-265-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn></math></span><mn>0</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-265">0</script> либо <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-266-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-266">1</script>. Это делается так:  

*   Начинаем обход с некоторой вершины, в соответствие которой ставится <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-267-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn></math></span><mn>0</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-267">0</script>.
*   При переходе по ребру от вершины <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-268-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></span><mi>a</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-268">a</script> к вершине <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-269-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></span><mi>b</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-269">b</script> вершине <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-270-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></span><mi>b</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-270">b</script> ставится в соответствие число, противоположное поставленному в соответствие вершине <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-271-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></span><mi>a</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-271">a</script> (например, если <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-272-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>v</mi><mi>a</mi><mi>l</mi><mo stretchy="false">[</mo><mi>a</mi><mo stretchy="false">]</mo><mo>=</mo><mn>0</mn></math></span><mi>v</mi><mi>a</mi><mi>l</mi><mo stretchy=&quot;false&quot;>[</mo><mi>a</mi><mo stretchy=&quot;false&quot;>]</mo><mo>=</mo><mn>0</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-272">val[a] = 0</script>, то <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-273-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>v</mi><mi>a</mi><mi>l</mi><mo stretchy="false">[</mo><mi>b</mi><mo stretchy="false">]</mo><mo>=</mo><mn>1</mn></math></span><mi>v</mi><mi>a</mi><mi>l</mi><mo stretchy=&quot;false&quot;>[</mo><mi>b</mi><mo stretchy=&quot;false&quot;>]</mo><mo>=</mo><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-273">val[b] = 1</script>, и наоборот).

После обхода нужно проверить, что не существует ребра между вершинами, которым соответствует одно и то же число. Если это так, то заданный граф является двудольным.  

Сложность одной итерации бинарного поиска равна <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-274-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>O</mi><mo stretchy="false">(</mo><mi>n</mi><mo>+</mo><mi>m</mi><mo stretchy="false">)</mo></math></span><mi>O</mi><mo stretchy=&quot;false&quot;>(</mo><mi>n</mi><mo>+</mo><mi>m</mi><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-274">O(n + m)</script>, а решение целиком имеет сложность <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-275-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>O</mi><mo stretchy="false">(</mo><mo stretchy="false">(</mo><mi>n</mi><mo>+</mo><mi>m</mi><mo stretchy="false">)</mo><mi>log</mi><mo>⁡</mo><mo movablelimits="true" form="prefix">max</mo><mi>w</mi><mo stretchy="false">)</mo></math></span><mi>O</mi><mo stretchy=&quot;false&quot;>(</mo><mo stretchy=&quot;false&quot;>(</mo><mi>n</mi><mo>+</mo><mi>m</mi><mo stretchy=&quot;false&quot;>)</mo><mi>log</mi><mo>&amp;#x2061;</mo><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>max</mo><mi>w</mi><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-275">O((n + m) \log \max w)</script>.

</div>

</div>

<div class="spoiler">**Код на Python**

<div class="spoiler_text">

    import sys

    def bfs(g, cl, m, v):
        qu = [v]
        cl[v] = 1

        l = 0
        while l != len(qu):
            v = qu[l]
            l += 1

            for u, w in g[v]:
                if w > m:
                    continue
                if cl[u] == 0:
                    cl[u] = 3 - cl[v]
                    qu.append(u)
                elif cl[v] == cl[u]:
                    return False

        return True

    def check(g, m):
        cl = [0 for i in range(len(g))]

        for i in range(len(g)):
            if cl[i] == 0 and not bfs(g, cl, m, i):
                return False

        return True

    def main():
        n, m = map(int, sys.stdin.readline().split())
        ed = [tuple(map(int, sys.stdin.readline().split())) for i in range(m)]

        g = [[] for i in range(n)]
        mx = 0
        for v, u, w in ed:
            g[v - 1].append((u - 1, w))
            g[u - 1].append((v - 1, w))
            mx = max(mx, w)

        if check(g, mx):
            sys.stdout.write(str(mx) + "\n")
            return

        l = 0
        r = mx + 1

        while r - l > 1:
            m = (l + r) // 2
            if check(g, m):
                l = m
            else:
                r = m

        sys.stdout.write(str(r) + "\n")

    main()

</div>

</div>

<div class="spoiler">**Код на C++**

<div class="spoiler_text">

    #include <algorithm>
    #include <string>
    #include <iostream>
    #include <vector>
    #include <utility>

    struct Solution {
        int n, m;
        std::vector<std::vector<std::pair<int, int>>> graph;
        std::vector<int> colors;

        bool dfs(int v, int color, int bound) {
            colors[v] = color;
            for (const auto &edge : graph[v]) {
                if (edge.second >= bound) {
                    continue;
                }
                if (colors[edge.first] == color) {
                    return false;
                }
                if (colors[edge.first] == -1) {
                    if (!dfs(edge.first, 1 - color, bound)) {
                        return false;
                    }
                }
            }
            return true;
        }

        bool check(int bound) {
            for (int i = 0; i < n; i++) {
                if (colors[i] == -1) {
                    if (!dfs(i, 0, bound)) {
                        return false;
                    }
                }
            }
            return true;
        }

        void run(std::istream &in, std::ostream &out) {
            in >> n >> m;
            graph.assign(n, std::vector<std::pair<int, int>>());
            for (int i = 0; i < m; i++) {
                int u, v, w;
                in >> u >> v >> w;
                u--;
                v--;
                graph[u].emplace_back(v, w);
                graph[v].emplace_back(u, w);
            }
            int l = 0;
            int r = 1000000001;
            while (r - l > 1) {
                int m = (l + r) / 2;
                colors.assign(n, -1);
                if (!check(m)) {
                    r = m;
                } else {
                    l = m;
                }
            }
            out << l << "\n";
        }
    };

    int main() {
        std::cin.sync_with_stdio(false);
        std::cin.tie(nullptr);
        Solution().run(std::cin, std::cout);
        return 0;
    }

</div>

</div>

<div class="spoiler">**Код на Java**

<div class="spoiler_text">

    import java.io.OutputStream;
    import java.io.IOException;
    import java.io.InputStream;
    import java.io.OutputStream;
    import java.io.PrintWriter;
    import java.util.Arrays;
    import java.io.BufferedWriter;
    import java.util.InputMismatchException;
    import java.io.IOException;
    import java.util.ArrayList;
    import java.util.List;
    import java.io.Writer;
    import java.io.OutputStreamWriter;
    import java.io.InputStream;

    /**
     * Built using CHelper plug-in
     * Actual solution is at the top
     */
    public class Graph_AD_Correct {
        public static void main(String[] args) {
            InputStream inputStream = System.in;
            OutputStream outputStream = System.out;
            InputReader in = new InputReader(inputStream);
            OutputWriter out = new OutputWriter(outputStream);
            Graph solver = new Graph();
            solver.solve(1, in, out);
            out.close();
        }

        static class Graph {
            public void solve(int testNumber, InputReader in, OutputWriter out) {
                int n = in.readInt();
                int m = in.readInt();
                //noinspection unchecked
                List<Graph.Edge>[] g = new List[n];
                for (int i = 0; i < n; i++) {
                    g[i] = new ArrayList<>();
                }
                int left = Integer.MAX_VALUE;
                int right = Integer.MIN_VALUE;
                for (int i = 0; i < m; i++) {
                    int x = in.readInt() - 1;
                    int y = in.readInt() - 1;
                    int w = in.readInt();
                    g[x].add(new Graph.Edge(y, w));
                    g[y].add(new Graph.Edge(x, w));
                    left = Math.min(left, w);
                    right = Math.max(right, w);
                }
                int[] color = new int[n];
                int ans = -1;
                while (left <= right) {
                    int mid = (left + right) / 2;
                    if (isBipartite(n, color, g, mid)) {
                        ans = mid;
                        left = mid + 1;
                    } else {
                        right = mid - 1;
                    }
                }
                if (ans == -1) {
                    throw new AssertionError();
                }
                out.printLine(ans);
            }

            private boolean isBipartite(int n, int[] color, List<Graph.Edge>[] g, int mid) {
                Arrays.fill(color, -1);
                for (int i = 0; i < n; i++) {
                    if (color[i] == -1) {
                        if (!dfs(i, -1, 0, color, g, mid)) {
                            return false;
                        }
                    }
                }
                return true;
            }

            private boolean dfs(int x, int p, int curColor, int[] color, List<Graph.Edge>[] g, int mid) {
                color[x] = curColor;
                for (Graph.Edge e : g[x]) {
                    if (e.w >= mid) {
                        continue;
                    }
                    int y = e.to;
                    if (y == p) {
                        continue;
                    }
                    if (color[y] == color[x]) {
                        return false;
                    }
                    if (color[y] == -1 && !dfs(y, x, 1 - curColor, color, g, mid)) {
                        return false;
                    }
                }
                return true;
            }

            static class Edge {
                int to;
                int w;

                Edge(int to, int w) {
                    this.to = to;
                    this.w = w;
                }

            }

        }

        static class OutputWriter {
            private final PrintWriter writer;

            public OutputWriter(OutputStream outputStream) {
                writer = new PrintWriter(new BufferedWriter(new OutputStreamWriter(outputStream)));
            }

            public OutputWriter(Writer writer) {
                this.writer = new PrintWriter(writer);
            }

            public void close() {
                writer.close();
            }

            public void printLine(int i) {
                writer.println(i);
            }

        }

        static class InputReader {
            private InputStream stream;
            private byte[] buf = new byte[1024];
            private int curChar;
            private int numChars;
            private InputReader.SpaceCharFilter filter;

            public InputReader(InputStream stream) {
                this.stream = stream;
            }

            public int read() {
                if (numChars == -1) {
                    throw new InputMismatchException();
                }
                if (curChar >= numChars) {
                    curChar = 0;
                    try {
                        numChars = stream.read(buf);
                    } catch (IOException e) {
                        throw new InputMismatchException();
                    }
                    if (numChars <= 0) {
                        return -1;
                    }
                }
                return buf[curChar++];
            }

            public int readInt() {
                int c = read();
                while (isSpaceChar(c)) {
                    c = read();
                }
                int sgn = 1;
                if (c == '-') {
                    sgn = -1;
                    c = read();
                }
                int res = 0;
                do {
                    if (c < '0' || c > '9') {
                        throw new InputMismatchException();
                    }
                    res *= 10;
                    res += c - '0';
                    c = read();
                } while (!isSpaceChar(c));
                return res * sgn;
            }

            public boolean isSpaceChar(int c) {
                if (filter != null) {
                    return filter.isSpaceChar(c);
                }
                return isWhitespace(c);
            }

            public static boolean isWhitespace(int c) {
                return c == ' ' || c == '\n' || c == '\r' || c == '\t' || c == -1;
            }

            public interface SpaceCharFilter {
                public boolean isSpaceChar(int ch);

            }

        }
    }

</div>

</div>

<a name="f"></a>

## F. Поиск

<div class="scrollable-table">

<table>

<tbody>

<tr>

<td></td>

<td>Все языки</td>

<td>Python</td>

<td>Java</td>

</tr>

<tr>

<td>Ограничение по времени на тест</td>

<td>2 с</td>

<td>4 c</td>

<td>2 c</td>

</tr>

<tr>

<td>Ограничение по памяти на тест</td>

<td colspan="3">512 МБ</td>

</tr>

<tr>

<td>Ввод</td>

<td colspan="3">стандартный ввод</td>

</tr>

<tr>

<td>Вывод</td>

<td colspan="3">стандартный вывод</td>

</tr>

</tbody>

</table>

</div>

Разработчики Яндекс.Поиска постоянно работают над улучшением алгоритмов ранжирования. Один из алгоритмов, который хотят опробовать, таков.

Поисковый алгоритм состоит из трех этапов: поиск по базе, отбор документов и фильтрация. Во время поиска по базе отбираются <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-276-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-276">n</script> документов-кандидатов для показа пользователю. Каждому документу сопоставляется целое число — релевантность, показывающее, насколько документ подходит пользователю. Чем выше релевантность, тем лучше документ подходит по данному запросу. Обратите внимание, что релевантность может быть даже отрицательной в случае, если документ не имеет никакого отношения к запросу.

Ранжирующий алгоритм хранит данные в закольцованном списке, таким образом, после документа с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-277-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi></math></span><mi>i</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-277">i</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-278-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi><mo><</mo><mi>n</mi></math></span><mi>i</mi><mo>&amp;lt;</mo><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-278">i < n</script>) следующим в списке является документ с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-279-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>i</mi><mo>+</mo><mn>1</mn></math></span><mi>i</mi><mo>+</mo><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-279">i + 1</script>, а следующим после документа с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-280-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-280">n</script> будет документ с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-281-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn></math></span><mn>1</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-281">1</script>. Во время отбора документов алгоритм выберет некоторый документ (назовем его начальным) и сколько-то следующих за начальным документов, которые будут переданы на фильтрацию.

Во время фильтрации из списка документов, полученных при отборе, может быть удалено несколько документов, но не более <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-282-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-282">k</script>. Кроме того, после фильтрации должен остаться хотя бы один документ. Оставшиеся после фильтрации документы показываются пользователю.

Релевантностью выдачи назовем сумму релевантностей документов в ней. По релевантностям документов, полученных во время поиска, определите, какую наибольшую релевантность выдачи можно получить при оптимальной работе алгоритма.

#### Входные данные

В первой строке задано целое число <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-283-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>t</mi></math></span><mi>t</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-283">t</script> — количество тестовых случаев. Далее следует описание тестовых случаев.

Описание каждого теста состоит из двух строк.

В первой строке задано два целых числа <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-284-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-284">n</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-285-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-285">k</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-286-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>1</mn><mo>≤</mo><mi>n</mi><mo>≤</mo><mn>100</mn><mn>000</mn></math></span><mn>1</mn><mo>&amp;#x2264;</mo><mi>n</mi><mo>&amp;#x2264;</mo><mn>100</mn><mspace width=&quot;thinmathspace&quot; /><mn>000</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-286">1 \leq n \leq 100\,000</script>, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-287-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn><mo>≤</mo><mi>k</mi><mo>≤</mo><mi>m</mi><mi>i</mi><mi>n</mi><mo stretchy="false">(</mo><mi>n</mi><mo>−</mo><mn>1</mn><mo>,</mo><mn>100</mn><mo stretchy="false">)</mo></math></span><mn>0</mn><mo>&amp;#x2264;</mo><mi>k</mi><mo>&amp;#x2264;</mo><mi>m</mi><mi>i</mi><mi>n</mi><mo stretchy=&quot;false&quot;>(</mo><mi>n</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mn>100</mn><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-287">0 \leq k \leq min(n - 1, 100)</script>) — количество документов, полученных во время поиска, и максимальное количество документов, которые могут быть удалены после фильтрации соответственно.

Во второй строке содержатся <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-288-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-288">n</script> целых чисел <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-289-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><msub><mi>a</mi><mi>i</mi></msub></math></span><msub><mi>a</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-289">a_i</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-290-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><msup><mn>10</mn><mn>9</mn></msup><mo>≤</mo><msub><mi>a</mi><mi>i</mi></msub><mo>≤</mo><msup><mn>10</mn><mn>9</mn></msup></math></span><mo>&amp;#x2212;</mo><msup><mn>10</mn><mn>9</mn></msup><mo>&amp;#x2264;</mo><msub><mi>a</mi><mi>i</mi></msub><mo>&amp;#x2264;</mo><msup><mn>10</mn><mn>9</mn></msup></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-290">-10^9 \leq a_i \leq 10^9</script>) — релевантности документов.

Гарантируется что сумма <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-291-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></span><mi>n</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-291">n</script> по всем тестовым случаям не превосходит <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-292-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>100</mn><mn>000</mn></math></span><mn>100</mn><mspace width=&quot;thinmathspace&quot; /><mn>000</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-292">100\,000</script>.

#### Выходные данные

Для каждого тестового случая выведите одно целое число — ответ на задачу.

#### Пример

Входные данные

<pre>6
4 0
1 -2 9 10
6 1
5 -5 5 -5 5 -5
6 2
5 -5 5 -5 5 -5
4 3
5 -5 5 -5
8 1
-3 -1 5 6 -200 -200 5 -1
3 1
-1 -2 -3
</pre>

Выходные данные

<pre>20
10
15
10
14
-1
</pre>

#### Примечание

В первом примере выгодно выбрать в качестве начального документ с релевантностью <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-293-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>9</mn></math></span><mn>9</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-293">9</script> и отправить на фильтрацию его и следующие 2 документа. На стадии фильтрации необходимо оставить все документы.

Во втором примере выгодно выбрать в качестве начального любой документ с релевантностью <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-294-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>5</mn></math></span><mn>5</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-294">5</script>, отправить на стадию фильтрации его и следующие за ним 2 документа. На стадии фильтрации необходимо удалить документ с релевантностью <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-295-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>5</mn></math></span><mo>&amp;#x2212;</mo><mn>5</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-295">-5</script>, таким образом, на выдачу попадут два документа с релевантностью <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-296-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>5</mn></math></span><mn>5</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-296">5</script>.

В пятом примере выгодно выбрать в качестве начального документ с номером <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-297-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>7</mn></math></span><mn>7</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-297">7</script> и отправить на стадию фильтрации его и следующие <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-298-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>5</mn></math></span><mn>5</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-298">5</script> документов. Таким образом, на стадию фильтрации попадут документы с релевантностями <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-299-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>5</mn><mo>,</mo><mo>−</mo><mn>1</mn><mo>,</mo><mo>−</mo><mn>3</mn><mo>,</mo><mo>−</mo><mn>1</mn><mo>,</mo><mn>5</mn><mo>,</mo><mn>6</mn><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mn>5</mn><mo>,</mo><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mo>&amp;#x2212;</mo><mn>3</mn><mo>,</mo><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mn>5</mn><mo>,</mo><mn>6</mn><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-299">[5, -1, -3, -1, 5, 6]</script>. На стадии фильтрации выгодно удалить документ с релевантностью <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-300-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>3</mn></math></span><mo>&amp;#x2212;</mo><mn>3</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-300">-3</script>, в результате чего на выдачу попадут документы с релевантностями <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-301-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>5</mn><mo>,</mo><mo>−</mo><mn>1</mn><mo>,</mo><mo>−</mo><mn>1</mn><mo>,</mo><mn>5</mn><mo>,</mo><mn>6</mn><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mn>5</mn><mo>,</mo><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mn>5</mn><mo>,</mo><mn>6</mn><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-301">[5, -1, -1, 5, 6]</script> с суммарной релевантностью <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-302-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>14</mn></math></span><mn>14</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-302">14</script>.

В последнем примере релевантность выдачи получится отрицательной, так как пользователю необходимо показать хотя бы один документ.

<a name="fr"></a>

<div class="spoiler">**Решение**

<div class="spoiler_text">

Если все релевантности документов отрицательны, то ответ — максимум по всем числам. Поскольку нам запрещено брать пустое множество, лучше обработать этот случай отдельно. Все последующие состояния динамики могут соответствовать пустому подотрезку с суммой <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-303-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn></math></span><mn>0</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-303">0</script>, но это не улучшит ответ, поскольку мы всегда можем взять какой-то один неотрицательный элемент и это будет не хуже.

Решим задачу, если нет цикличности массива.

Пусть <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-304-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><msub><mi>p</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></math></span><mi>d</mi><msub><mi>p</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-304">dp_{i, j}</script> — максимальная сумма, которая может быть на каком-то подотрезке <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-305-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mi>l</mi><mo>;</mo><mi>i</mi><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mi>l</mi><mo>;</mo><mi>i</mi><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-305">[l; i]</script> (<span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-306-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>l</mi></math></span><mi>l</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-306">l</script> тут не фиксировано и выбирается так, чтобы ответ был максимален), если из него удалили не более <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-307-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-307">k</script> элементов.

Пересчет: <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-308-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><msub><mi>p</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>=</mo><mo movablelimits="true" form="prefix">max</mo><mo stretchy="false">(</mo><mrow class="MJX-TeXAtom-ORD"><mn>0</mn><mo>,</mo><mi>d</mi><msub><mi>p</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>−</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><mi>d</mi><msub><mi>p</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>−</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>−</mo><mn>1</mn></mrow></msub></mrow><mo stretchy="false">)</mo></math></span><mi>d</mi><msub><mi>p</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>=</mo><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>max</mo><mo stretchy=&quot;false&quot;>(</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mn>0</mn><mo>,</mo><mi>d</mi><msub><mi>p</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><mi>d</mi><msub><mi>p</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>&amp;#x2212;</mo><mn>1</mn></mrow></msub></mrow><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-308">dp_{i, j} = \max({0, dp_{i - 1, j} + a_i, dp_{i - 1, j - 1}})</script>, что соответствует:

1.  <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-309-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn></math></span><mn>0</mn></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-309">0</script> — попробовать начать новый «пустой» отрезок в этом месте.
2.  <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-310-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><msub><mi>p</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>−</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub></math></span><mi>d</mi><msub><mi>p</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-310">dp_{i - 1, j} + a_i</script> — продолжить какой-то оптимальный отрезок, добавив в него i-й элемент.
3.  <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-311-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><msub><mi>p</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>−</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>−</mo><mn>1</mn></mrow></msub></math></span><mi>d</mi><msub><mi>p</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>&amp;#x2212;</mo><mn>1</mn></mrow></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-311">dp_{i - 1, j - 1}</script> — продолжить какой-то оптимальный отрезок, удалив из него i-й элемент.

Такая динамика считается за <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-312-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>O</mi><mo stretchy="false">(</mo><mi>n</mi><mi>k</mi><mo stretchy="false">)</mo></math></span><mi>O</mi><mo stretchy=&quot;false&quot;>(</mo><mi>n</mi><mi>k</mi><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-312">O(nk)</script>, и ответом на задачу в этом случае является <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-313-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><munder><mo form="prefix">max</mo><mrow class="MJX-TeXAtom-ORD"><mstyle scriptlevel="1"><mtable rowspacing="0.1em" columnspacing="0em" displaystyle="false"><mtr><mtd><mn>1</mn><mo>≤</mo><mi>i</mi><mo>≤</mo><mi>n</mi></mtd></mtr><mtr><mtd><mn>0</mn><mo>≤</mo><mi>j</mi><mo>≤</mo><mi>k</mi></mtd></mtr></mtable></mstyle></mrow></munder><mrow class="MJX-TeXAtom-ORD"><mi>d</mi><msub><mi>p</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></mrow></math></span><munder><mo form=&quot;prefix&quot;>max</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mstyle scriptlevel=&quot;1&quot;><mtable rowspacing=&quot;0.1em&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;false&quot;><mtr><mtd><mn>1</mn><mo>&amp;#x2264;</mo><mi>i</mi><mo>&amp;#x2264;</mo><mi>n</mi></mtd></mtr><mtr><mtd><mn>0</mn><mo>&amp;#x2264;</mo><mi>j</mi><mo>&amp;#x2264;</mo><mi>k</mi></mtd></mtr></mtable></mstyle></mrow></munder><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>d</mi><msub><mi>p</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></mrow></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-313">\max\limits_{\substack{1 \leq i \leq n \\ 0 \leq j \leq k}}{dp_{i, j}}</script>.

Таким образом, мы учли все подотрезки массива, которые не проходят через стык первого и n-го элемента.

Теперь учтем оставшиеся отрезки.

Пусть <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-314-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></math></span><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-314">dpl_{i, j}</script> — максимальная сумма, которая может быть на некотором подотрезке <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-315-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mn>1</mn><mo>;</mo><mi>i</mi><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mn>1</mn><mo>;</mo><mi>i</mi><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-315">[1; i]</script>, если из него удалили ровно <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-316-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-316">k</script> элементов.

Пересчет: <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-317-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>=</mo><mo movablelimits="true" form="prefix">max</mo><mo stretchy="false">(</mo><mrow class="MJX-TeXAtom-ORD"><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>−</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>−</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>−</mo><mn>1</mn></mrow></msub></mrow><mo stretchy="false">)</mo></math></span><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>=</mo><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>max</mo><mo stretchy=&quot;false&quot;>(</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>&amp;#x2212;</mo><mn>1</mn></mrow></msub></mrow><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-317">dpl_{i, j} = \max({dpl_{i - 1, j} + a_i, dpl_{i - 1, j - 1}})</script>, что соответствует:

1.  <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-318-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>−</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub></math></span><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-318">dpl_{i - 1, j} + a_i</script> — продолжить отрезок, добавив в него i-й элемент.
2.  <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-319-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>−</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>−</mo><mn>1</mn></mrow></msub></math></span><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>&amp;#x2212;</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>&amp;#x2212;</mo><mn>1</mn></mrow></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-319">dpl_{i - 1, j - 1}</script> — продолжить отрезок, удалив из него i-й элемент.

В отличие от первой динамики, нет необходимости начинать новый отрезок, поскольку левая граница фиксирована.

Аналогично, <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-320-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></math></span><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-320">dpr_{i, j}</script> — максимальная сумма, которая может быть на некотором подотрезке <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-321-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo stretchy="false">[</mo><mi>i</mi><mo>;</mo><mi>n</mi><mo stretchy="false">]</mo></math></span><mo stretchy=&quot;false&quot;>[</mo><mi>i</mi><mo>;</mo><mi>n</mi><mo stretchy=&quot;false&quot;>]</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-321">[i; n]</script>, если из него удалили ровно <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-322-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi></math></span><mi>k</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-322">k</script> элементов.

Пересчет: <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-323-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>=</mo><mo movablelimits="true" form="prefix">max</mo><mo stretchy="false">(</mo><mrow class="MJX-TeXAtom-ORD"><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>−</mo><mn>1</mn></mrow></msub></mrow><mo stretchy="false">)</mo></math></span><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>=</mo><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>max</mo><mo stretchy=&quot;false&quot;>(</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub><mo>,</mo><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>&amp;#x2212;</mo><mn>1</mn></mrow></msub></mrow><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-323">dpr_{i, j} = \max({dpr_{i + 1, j} + a_i, dpr_{i + 1, j - 1}})</script>, что соответствует:

1.  <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-324-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub></math></span><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>+</mo><msub><mi>a</mi><mi>i</mi></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-324">dpr_{i +1, j} + a_i</script> — продолжить отрезок, добавив в него i-й элемент.
2.  <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-325-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>−</mo><mn>1</mn></mrow></msub></math></span><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi><mo>&amp;#x2212;</mo><mn>1</mn></mrow></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-325">dpr_{i + 1, j - 1}</script> — продолжить отрезок, удалив из него i-й элемент.

Обе эти динамики можно посчитать за <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-326-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>O</mi><mo stretchy="false">(</mo><mi>n</mi><mi>k</mi><mo stretchy="false">)</mo></math></span><mi>O</mi><mo stretchy=&quot;false&quot;>(</mo><mi>n</mi><mi>k</mi><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-326">O(nk)</script>.

Как теперь учесть все отрезки, проходящие через стык первого и n-го элемента? Переберем префикс <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-327-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi></math></span><mi>p</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-327">p</script>, который войдет в ответ, а также количество элементов <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-328-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-328">q</script>, которое мы удалили на этом префиксе. Самое оптимальное состояние — это <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-329-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class="MJX-TeXAtom-ORD"><mi>p</mi><mo>,</mo><mi>q</mi></mrow></msub></math></span><mi>d</mi><mi>p</mi><msub><mi>l</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>p</mi><mo>,</mo><mi>q</mi></mrow></msub></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-329">dpl_{p, q}</script>. Теперь нужно соеденить это состояние с самым оптимальным суффиксом — если точнее, с <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-330-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><munder><mo form="prefix">max</mo><mrow class="MJX-TeXAtom-ORD"><mstyle scriptlevel="1"><mtable rowspacing="0.1em" columnspacing="0em" displaystyle="false"><mtr><mtd><mi>p</mi><mo><</mo><mi>i</mi><mo>≤</mo><mi>n</mi></mtd></mtr><mtr><mtd><mn>0</mn><mo>≤</mo><mi>j</mi><mo>≤</mo><mi>k</mi><mo>−</mo><mi>q</mi></mtd></mtr></mtable></mstyle></mrow></munder><mrow class="MJX-TeXAtom-ORD"><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></mrow></math></span><munder><mo form=&quot;prefix&quot;>max</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mstyle scriptlevel=&quot;1&quot;><mtable rowspacing=&quot;0.1em&quot; columnspacing=&quot;0em&quot; displaystyle=&quot;false&quot;><mtr><mtd><mi>p</mi><mo>&amp;lt;</mo><mi>i</mi><mo>&amp;#x2264;</mo><mi>n</mi></mtd></mtr><mtr><mtd><mn>0</mn><mo>&amp;#x2264;</mo><mi>j</mi><mo>&amp;#x2264;</mo><mi>k</mi><mo>&amp;#x2212;</mo><mi>q</mi></mtd></mtr></mtable></mstyle></mrow></munder><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub></mrow></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-330">\max\limits_{\substack{p < i \leq n \\ 0 \leq j \leq k - q}}{dpr_{i, j}}</script>.

Этот максимум можно предпросчитать еще одной динамикой <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-331-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>d</mi><mi>p</mi><mi>r</mi><mi mathvariant="normal">_</mi><mi>m</mi><mi>a</mi><msub><mi>x</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>=</mo><mo movablelimits="true" form="prefix">max</mo><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">(</mo><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>,</mo><mi>d</mi><mi>p</mi><mi>r</mi><mi mathvariant="normal">_</mi><mi>m</mi><mi>a</mi><msub><mi>x</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>,</mo><mi>d</mi><mi>p</mi><mi>r</mi><mi mathvariant="normal">_</mi><mi>m</mi><mi>a</mi><msub><mi>x</mi><mrow class="MJX-TeXAtom-ORD"><mi>i</mi><mo>,</mo><mi>j</mi><mo>−</mo><mn>1</mn></mrow></msub><mo stretchy="false">)</mo></mrow></math></span><mi>d</mi><mi>p</mi><mi>r</mi><mi mathvariant=&quot;normal&quot;>&amp;#x005F;</mi><mi>m</mi><mi>a</mi><msub><mi>x</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>=</mo><mo movablelimits=&quot;true&quot; form=&quot;prefix&quot;>max</mo><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>(</mo><mi>d</mi><mi>p</mi><msub><mi>r</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi></mrow></msub><mo>,</mo><mi>d</mi><mi>p</mi><mi>r</mi><mi mathvariant=&quot;normal&quot;>&amp;#x005F;</mi><mi>m</mi><mi>a</mi><msub><mi>x</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>+</mo><mn>1</mn><mo>,</mo><mi>j</mi></mrow></msub><mo>,</mo><mi>d</mi><mi>p</mi><mi>r</mi><mi mathvariant=&quot;normal&quot;>&amp;#x005F;</mi><mi>m</mi><mi>a</mi><msub><mi>x</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>i</mi><mo>,</mo><mi>j</mi><mo>&amp;#x2212;</mo><mn>1</mn></mrow></msub><mo stretchy=&quot;false&quot;>)</mo></mrow></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-331">dpr\_max_{i, j} = \max{(dpr_{i, j}, dpr\_max_{i + 1, j}, dpr\_max_{i, j - 1})}</script>. Сложность такого предпросчета — <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-332-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>O</mi><mo stretchy="false">(</mo><mi>n</mi><mi>k</mi><mo stretchy="false">)</mo></math></span><mi>O</mi><mo stretchy=&quot;false&quot;>(</mo><mi>n</mi><mi>k</mi><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-332">O(nk)</script>, и после него можно находить оптимальный суффикс для каждой фиксированной пары <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-333-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>p</mi></math></span><mi>p</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-333">p</script> и <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-334-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>q</mi></math></span><mi>q</mi></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-334">q</script> за <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-335-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>O</mi><mo stretchy="false">(</mo><mn>1</mn><mo stretchy="false">)</mo></math></span><mi>O</mi><mo stretchy=&quot;false&quot;>(</mo><mn>1</mn><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-335">O(1)</script>.

Получаем решение за <span class="MathJax_Preview" style="color: inherit; display: none;"></span><span style="font-size: 100%; display: inline-block; position: relative;" class="MathJax_SVG" id="MathJax-Element-336-Frame" tabindex="0" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>O</mi><mo stretchy="false">(</mo><mi>n</mi><mi>k</mi><mo stretchy="false">)</mo></math></span><mi>O</mi><mo stretchy=&quot;false&quot;>(</mo><mi>n</mi><mi>k</mi><mo stretchy=&quot;false&quot;>)</mo></math>" role="presentation"></span><script type="math/tex" id="MathJax-Element-336">O(nk)</script> времени и памяти.

</div>

</div>

<div class="spoiler">**Код на Python**

<div class="spoiler_text">

    import sys

    def solve():
        n, k = map(int, sys.stdin.readline().split())
        arr = list(map(int, sys.stdin.readline().split()))

        ans = max(arr)
        if ans <= 0:
            return ans

        dp_l = [[0 for j in range(k + 2)] for i in range(n + 2)]
        dp_r = [[0 for j in range(k + 2)] for i in range(n + 2)]

        for i in range(1, n + 1):
            for j in range(k + 1):
                dp_l[i][j] = max(0, dp_l[i - 1][j] + arr[i - 1])
                if j: dp_l[i][j] = max(dp_l[i][j], dp_l[i - 1][j - 1])
                ans = max(ans, dp_l[i][j])

        for i in range(1, n + 1):
            for j in range(k + 1):
                dp_l[i][j] = dp_l[i - 1][j] + arr[i - 1]
                if j: dp_l[i][j] = max(dp_l[i][j], dp_l[i - 1][j - 1])

        for i in range(n, 0, -1):
            for j in range(k + 1):
                dp_r[i][j] = dp_r[i + 1][j]  + arr[i - 1]
                if j: dp_r[i][j] = max(dp_r[i][j], dp_r[i + 1][j - 1])

        for i in range(1, n + 1):
            for j in range(k + 1):
                if i != 1: dp_l[i][j] = max(dp_l[i][j], dp_l[i - 1][j])
                if j: dp_l[i][j] = max(dp_l[i][j], dp_l[i][j - 1])

        for i in range(n, 0, -1):
            for j in range(k + 1):
                if i != n: dp_r[i][j] = max(dp_r[i][j], dp_r[i + 1][j])
                if j: dp_r[i][j] = max(dp_r[i][j], dp_r[i][j - 1])

        for i in range(1, n):
            for j in range(k + 1):
                ans = max(ans, dp_l[i][j] + dp_r[i + 1][k - j])

        return ans

    def main():
        t = int(sys.stdin.readline())

        ans = []
        for i in range(t):
            ans.append(str(solve()))

        sys.stdout.write("\n".join(ans) + "\n")

    main()

</div>

</div>

<div class="spoiler">**Код на C++**

<div class="spoiler_text">

    #include <stdio.h>
    #include <iostream>
    #include <stdlib.h>
    #include <string>
    #include <string.h>
    #include <vector>
    #include <stack>
    #include <queue>
    #include <deque>
    #include <set>
    #include <map>
    #include <assert.h>
    #include <algorithm>
    #include <iomanip>
    #include <time.h>
    #include <math.h>
    #include <bitset>

    #pragma comment(linker, "/STACK:256000000")

    using namespace std;

    typedef long long int ll;
    typedef long double ld;

    const int INF = 1000 * 1000 * 1000 + 21;
    const ll LLINF = (1ll << 60) + 5;
    const int MOD = 1000 * 1000 * 1000 + 7;

    const int MAX_N = 100 * 1000 + 227;
    const int MAX_K = 105;

    int n, k;
    int arr[MAX_N];
    ll dp_l[MAX_N][MAX_K];
    ll dp_r[MAX_N][MAX_K];

    void solve() {
        scanf("%d%d", &n, &k);

        ll ans = -LLINF;
        for (int i = 0; i < n; ++i) {
            scanf("%d", &arr[i]);
            ans = max(ans, (ll)arr[i]);
        }

        if (ans <= 0) {
            printf("%lld\n", ans);
            return;
        }

        for (int i = 0; i <= k; ++i) {
            dp_l[n + 1][i] = 0;
            dp_r[n + 1][i] = 0;
        }

        for (int i = 1; i <= n; ++i) {
            for (int j = 0; j <= k; ++j) {
                dp_l[i][j] = max(0ll, dp_l[i - 1][j] + arr[i - 1]);
                if (j) {
                    dp_l[i][j] = max(dp_l[i][j], dp_l[i - 1][j - 1]);
                }

                ans = max(ans, dp_l[i][j]);
            }
        }

        for (int i = 1; i <= n; ++i) {
            for (int j = 0; j <= k; ++j) {
                dp_l[i][j] = dp_l[i - 1][j] + arr[i - 1];
                if (j) {
                    dp_l[i][j] = max(dp_l[i][j], dp_l[i - 1][j - 1]);
                }
            }
        }

        for (int i = n; i >= 1; --i) {
            for (int j = 0; j <= k; ++j) {
                dp_r[i][j] = dp_r[i + 1][j] + arr[i - 1];
                if (j) {
                    dp_r[i][j] = max(dp_r[i][j], dp_r[i + 1][j - 1]);
                }
            }
        }

        for (int i = 1; i <= n; ++i) {
            for (int j = 0; j <= k; ++j) {
                if (i != 1) {
                    dp_l[i][j] = max(dp_l[i][j], dp_l[i - 1][j]);
                }
                if (j) {
                    dp_l[i][j] = max(dp_l[i][j], dp_l[i][j - 1]);
                }
            }
        }

        for (int i = n; i >= 1; --i) {
            for (int j = 0; j <= k; ++j) {
                if (i != n) {
                    dp_r[i][j] = max(dp_r[i][j], dp_r[i + 1][j]);
                }
                if (j) {
                    dp_r[i][j] = max(dp_r[i][j], dp_r[i][j - 1]);
                }
            }
        }

        for (int i = 1; i < n; ++i) {
            for (int j = 0; j <= k; ++j) {
                ans = max(ans, dp_l[i][j] + dp_r[i + 1][k - j]);
            }
        }

        printf("%lld\n", ans);
    }

    int main() {
    #ifdef CH_EGOR
        freopen("input.txt", "r", stdin);
        //freopen("output.txt", "w", stdout);
    #else
        //freopen("", "r", stdin);
        //freopen("", "w", stdout);
    #endif

        int t;
        scanf("%d", &t);
        while (t--) {
            solve();
        }

        return 0;
    }

</div>

</div>

<div class="spoiler">**Код на Java**

<div class="spoiler_text">

    import java.io.OutputStream;
    import java.io.IOException;
    import java.io.InputStream;
    import java.io.OutputStream;
    import java.io.PrintWriter;
    import java.io.BufferedWriter;
    import java.io.Writer;
    import java.io.OutputStreamWriter;
    import java.io.IOException;
    import java.io.InputStream;

    /**
     * Built using CHelper plug-in
     * Actual solution is at the top
     *
     * @author ch_egor
     */
    public class Main {
        public static void main(String[] args) {
            InputStream inputStream = System.in;
            OutputStream outputStream = System.out;
            InputReader in = new InputReader(inputStream);
            OutputWriter out = new OutputWriter(outputStream);
            MaxSum solver = new MaxSum();
            int testCount = Integer.parseInt(in.next());
            for (int i = 1; i <= testCount; i++)
                solver.solve(i, in, out);
            out.close();
        }

        static class MaxSum {
            static final long LLINF = (1L << 60) + 5;

            public void solve(int testNumber, InputReader in, OutputWriter out) {
                int n = in.nextInt();
                int k = in.nextInt();

                int[] arr = new int[n];
                long[][] dp_l = new long[n + 2][k + 2];
                long[][] dp_r = new long[n + 2][k + 2];

                long ans = -LLINF;
                for (int i = 0; i < n; ++i) {
                    arr[i] = in.nextInt();
                    ans = Math.max(ans, arr[i]);
                }

                if (ans <= 0) {
                    out.println(ans);
                    return;
                }

                for (int i = 0; i <= k; ++i) {
                    dp_l[n + 1][i] = 0;
                    dp_r[n + 1][i] = 0;
                }

                for (int i = 1; i <= n; ++i) {
                    for (int j = 0; j <= k; ++j) {
                        dp_l[i][j] = Math.max(0L, dp_l[i - 1][j] + arr[i - 1]);
                        if (j != 0) {
                            dp_l[i][j] = Math.max(dp_l[i][j], dp_l[i - 1][j - 1]);
                        }

                        ans = Math.max(ans, dp_l[i][j]);
                    }
                }

                for (int i = 1; i <= n; ++i) {
                    for (int j = 0; j <= k; ++j) {
                        dp_l[i][j] = dp_l[i - 1][j] + arr[i - 1];
                        if (j != 0) {
                            dp_l[i][j] = Math.max(dp_l[i][j], dp_l[i - 1][j - 1]);
                        }
                    }
                }

                for (int i = n; i >= 1; --i) {
                    for (int j = 0; j <= k; ++j) {
                        dp_r[i][j] = dp_r[i + 1][j] + arr[i - 1];
                        if (j != 0) {
                            dp_r[i][j] = Math.max(dp_r[i][j], dp_r[i + 1][j - 1]);
                        }
                    }
                }

                for (int i = 1; i <= n; ++i) {
                    for (int j = 0; j <= k; ++j) {
                        if (i != 1) {
                            dp_l[i][j] = Math.max(dp_l[i][j], dp_l[i - 1][j]);
                        }
                        if (j != 0) {
                            dp_l[i][j] = Math.max(dp_l[i][j], dp_l[i][j - 1]);
                        }
                    }
                }

                for (int i = n; i >= 1; --i) {
                    for (int j = 0; j <= k; ++j) {
                        if (i != n) {
                            dp_r[i][j] = Math.max(dp_r[i][j], dp_r[i + 1][j]);
                        }
                        if (j != 0) {
                            dp_r[i][j] = Math.max(dp_r[i][j], dp_r[i][j - 1]);
                        }
                    }
                }

                for (int i = 1; i < n; ++i) {
                    for (int j = 0; j <= k; ++j) {
                        ans = Math.max(ans, dp_l[i][j] + dp_r[i + 1][k - j]);
                    }
                }

                out.println(ans);
            }

        }

        static class OutputWriter {
            private final PrintWriter writer;

            public OutputWriter(OutputStream outputStream) {
                writer = new PrintWriter(new BufferedWriter(new OutputStreamWriter(outputStream)));
            }

            public OutputWriter(Writer writer) {
                this.writer = new PrintWriter(writer);
            }

            public void close() {
                writer.close();
            }

            public void println(long i) {
                writer.println(i);
            }

        }

        static class InputReader {
            private InputStream stream;
            private byte[] buf = new byte[1024];
            private int curChar;
            private int numChars;
            private InputReader.SpaceCharFilter filter;

            public InputReader(InputStream stream) {
                this.stream = stream;
            }

            public int read() {
                if (numChars == -1) {
                    throw new UnknownError();
                }
                if (curChar >= numChars) {
                    curChar = 0;
                    try {
                        numChars = stream.read(buf);
                    } catch (IOException e) {
                        throw new UnknownError();
                    }
                    if (numChars <= 0) {
                        return -1;
                    }
                }
                return buf[curChar++];
            }

            public int nextInt() {
                int c = read();
                while (isSpaceChar(c)) {
                    c = read();
                }
                int sgn = 1;
                if (c == '-') {
                    sgn = -1;
                    c = read();
                }
                int res = 0;
                do {
                    if (c < '0' || c > '9') {
                        throw new UnknownError();
                    }
                    res *= 10;
                    res += c - '0';
                    c = read();
                } while (!isSpaceChar(c));
                return res * sgn;
            }

            public String nextString() {
                int c = read();
                while (isSpaceChar(c)) {
                    c = read();
                }
                StringBuilder res = new StringBuilder();
                do {
                    if (Character.isValidCodePoint(c)) {
                        res.appendCodePoint(c);
                    }
                    c = read();
                } while (!isSpaceChar(c));
                return res.toString();
            }

            public boolean isSpaceChar(int c) {
                if (filter != null) {
                    return filter.isSpaceChar(c);
                }
                return isWhitespace(c);
            }

            public static boolean isWhitespace(int c) {
                return c == ' ' || c == '\n' || c == '\r' || c == '\t' || c == -1;
            }

            public String next() {
                return nextString();
            }

            public interface SpaceCharFilter {
                public boolean isSpaceChar(int ch);

            }

        }
    }

</div>

</div>