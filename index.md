<h1>Poker Texas hold 'em</h1>
<br>
<br>
<h2>Úvod</h2>
<p>Mým maturitním projektem z informatiky je hra Poker Texas hold ‘em.
Program má grafické rozhraní a hraje se proti počítačem řízeným protivníkům.
Celý program je naprogramovaný v c sharpu a grafické rozhraní je uděláno pomocí Windows Forms, což je knihovna tříd obsažená v .NET frameworku</p>
<br>
<h2>Pravidla hry poker</h2>
<br>
<p>Poker Texas hold ‘em je karetní hra, která se hraje s balíčkem 52 karet, kde cílem je vyhrát od ostatních hráčů všechny jejich žetony, a tak je eliminovat. Hráči jdou po sobě ve směru hodinových ručiček.</p>
<p>Když je hráč na tahu, tak má možnosti:</p>
<ul>
  <li>	zahodit karty tzv. fold, čímž se vzdává v této handě</li>
  <li>	pokud žádný jiný hráč nezvýšil, tak tzv. check, což znamená nezvýšit</li>
  <li>	pokud jiný hráč zvýšil, tak tzv. call, což znamená dorovnat sázku</li>
  <li>	zvýšit tzv. raise, pokud už jiný hráč zvýšil, tak se rozumí dorovnat a pak přihodit (je také pravidlo že se zvýšit smí minimálně o hodnotu big blindu)</li>
</ul>
<p>Na začátku kola tzv. handy proběhnou povinné sázky tzv. blindy které učiní dva hráči: big a small blind (big blind je dvounásobek small blindu), blindy se každé kolo posouvají o jedno místo ve směru hodinových ručiček.</p>
  <p>Po blindech se všem hráčům rozdají do ruky dvě karty, tyto karty vidí jen oni sami.</p>
  <p>Nyní začne první kolo sázek tzv. pre-flop, jako první hraje hráč po big blindu.</p>
<p>Když skončí první kolo sázek a ve hře jsou stále alespoň dva hráči, tak se vyloží na stůl tři karty tzv. flop a proběhne druhé kolo sázek, na rozdíl od prvního kola se už nedávají blindy a jako první hraje hráč v pozici small blind.</p>
<p>Po flopu, pokud jsou ve hře stále alespoň dva hráči, se na stůl vyloží jedna další karta tzv. turn a proběhne třetí kolo sázek, které je jinak stejné jako druhé kolo.</p>
<p>Po turnu, pokud jsou ve hře alespoň dva hráči, se na stůl vyloží poslední pátá karta tzv. river a proběhne poslední kolo sázek, stejně jako dvě předchozí.</p>
<p>Pokud i po posledním kole sázek jsou ve hře alespoň dva hráči, tak proběhne tzv. showdown, kde zbývající hráči porovnají svoje kombinace karet a podle nich se určí vítěz, hodnoty kombinací naleznete níže. Vítěz vyhrává vsazené žetony tzv. pot, v případě remízy se žetony dělí.</p>
<p>Pokud jeden hráč nevyhrál v jedné handě všechny žetony, tak se hraje další handa, do té doby, než nebude jen jeden vítěz</p>
<br>
<h2>Kombinace karet</h2>
<br>
<p>Hráč má v tvorbě kombinace přístup k sedmi kartám: dvou v ruce a pěti na stole, avšak kombinace samotná se vždy tvoří maximálně z pěti karet, vždy se z možných sedmi vybírá nejsilnějších pět karet.</p>
<p>Vyšší kombinace vždy přebije nižší, v sestupném pořadí jsou:</p>
<ul>
<li>čistá postupka tzv. straight flush: pět karet stejné barvy, které tvoří postupku (pět po sobě jdoucích hodnot), eso může mít roli nejvyšší i nejnižší karty</li>
<li>poker tzv. four of a kind: čtveřice karet se stejnou hodnotou</li>
<li>full house: trojice karet se stejnou hodnotou a dvojice karet se stejnou hodnotou</li>
<li>barva tzv. flush: pětice karet se stejnou barvou</li>
<li>postupka tzv. straight: pět po sobě jdoucích karet, eso může mít roli nejvyšší i nejnižší karty</li>
<li>trojice tzv. three of a kind: trojice karet se stejnou hodnotou</li>
<li>dva páry tzv. two pair: dvě dvojice karet se stejnou hodnotou</li>
<li>pár tzv. pair: dvojice karet se stejnou hodnotou</li>
<li>vysoká karta tzv. high card: v případě že hráč není schopen vytvořit žádnou z výše zmíněných kombinací, tak hraje pouze na hodnotu své nejvyšší karty</li>
  </ul>
<p>Pokud nastane situace, že více hráčů má stejnou kombinaci, tak se porovnává, kdo má vyšší hodnotu této kombinace čili:</p>
<ul>
<li>u čisté postupky se porovnává hodnota nejvyšší karty obsažené v ní</li>
<li>u pokeru se porovnává hodnota čtveřice karet</li>
<li>u full housu se porovnává hodnota trojice karet a pokud ta je shodná, tak se porovnává hodnota dvojice</li>
<li>u barvy se porovnává hodnota nejvyšší karty této barvy a pokud ta je shodná, tak se porovnává druhá, třetí atd. nejvyšší karta</li>
<li>u postupky se porovnává hodnota nejvyšší karty obsažené v ní</li>
<li>u trojice se porovnává hodnota trojice karet</li>
<li>u dvou párů se porovnává hodnota vyššího z párů, popřípadě nižšího z párů</li>
<li>u páru se porovnává hodnota páru</li>
<li>u vysoké karty se porovnává hodnota vysoké karty</li>
  </ul>
<p>Pokud i porovnání hodnoty kombinace vyšlo u více hráčů stejně a jedná se o kombinaci, která využila všech pět karet (tedy čistá postupka, full house, barva, postupka), tak se rozdělí peníze v potu mezi zbývajícími hráči.</p>
<p>Pokud se jedná o kombinaci, která nevyužila všech pět karet (tedy poker, trojice, dva páry, pár, vysoká karta), tak se požívá tzv. kicker. Kicker je karta, která je mimo samotnou kombinaci, s nejvyšší hodnotou. U zbývajících hráčů se porovná kicker a ten s nejvyšším kickerem vyhraje, pokud je první kicker u zbývajících hráčů shodný, a do pěti karet je ještě vejde další (v případě trojice, páru a vysoké karty), tak se použije druhý kicker, pokud i ten je shodný tak se může použít i třetí kicker (u páru a vysoké karty), pokud i ten je shodný tak se může použít i čtvrtý kicker (u vysoké karty), pokud i čtvrtý kicker je u zbývajících hráčů shodný, tak se žetony mezi zbývajícími hráči rozdělí.</p>





