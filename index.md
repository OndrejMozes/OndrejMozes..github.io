#Poker Texas hold 'em



##Úvod

Mým maturitním projektem z informatiky je hra Poker Texas hold ‘em.
Program má grafické rozhraní a hraje se proti počítačem řízeným protivníkům.
Celý program je naprogramovaný v c sharpu a grafické rozhraní je uděláno pomocí Windows Forms, což je knihovna tříd obsažená v .NET frameworku


##Pravidla hry poker

Poker Texas hold ‘em je karetní hra, která se hraje s balíčkem 52 karet, kde cílem je vyhrát od ostatních hráčů všechny jejich žetony, a tak je eliminovat. Hráči jdou po sobě ve směru hodinových ručiček.
Když je hráč na tahu, tak má možnosti:
•	zahodit karty tzv. fold, čímž se vzdává v této handě
•	pokud žádný jiný hráč nezvýšil, tak tzv. Check, což znamená nezvýšit
•	pokud jiný hráč zvýšil, tak tzv. Call, což znamená dorovnat sázku
•	zvýšit tzv. raise, pokud už jiný hráč zvýšil, tak se rozumí dorovnat a pak přihodit (je také pravidlo že se zvýšit smí minimálně o hodnotu big blindu)
Na začátku kola tzv. handy proběhnou povinné sázky tzv. blindy které učiní dva hráči: big a small blind (big blind je dvounásobek small blindu), blindy se každé kolo posouvají o jedno místo ve směru hodinových ručiček.
Po blindech se všem hráčům rozdají do ruky dvě karty, tyto karty vidí jen oni sami.
Nyní začne první kolo sázek tzv. pre-flop, jako první hraje hráč po big blindu. 
Když skončí první kolo sázek a ve hře jsou stále alespoň dva hráči, tak se vyloží na stůl tři karty tzv. flop a proběhne druhé kolo sázek, na rozdíl od prvního kola se už nedávají blindy a jako první hraje hráč v pozici small blind.
Po flopu, pokud jsou ve hře stále alespoň dva hráči, se na stůl vyloží jedna další karta tzv. turn a proběhne třetí kolo sázek, které je jinak stejné jako druhé kolo.
Po turnu, pokud jsou ve hře alespoň dva hráči, se na stůl vyloží poslední pátá karta tzv. river a proběhne poslední kolo sázek, stejně jako dvě předchozí.
Pokud i po posledním kole sázek jsou ve hře alespoň dva hráči, tak proběhne tzv. showdown, kde zbývající hráči porovnají svoje kombinace karet a podle nich se určí vítěz, hodnoty kombinací naleznete níže. Vítěz vyhrává vsazené žetony tzv. pot, v případě remízy se žetony dělí.
Pokud jeden hráč nevyhrál v jedné handě všechny žetony, tak se hraje další handa, do té doby, než nebude jen jeden vítěz

##Kombinace karet

Hráč má v tvorbě kombinace přístup k sedmi kartám: dvou v ruce a pěti na stole, avšak kombinace samotná se vždy tvoří maximálně z pěti karet, vždy se z možných sedmi vybírá nejsilnějších pět karet.
Vyšší kombinace vždy přebije nižší, v sestupném pořadí jsou:
•	čistá postupka tzv. straight flush: pět karet stejné barvy, které tvoří postupku (pět po sobě jdoucích hodnot), eso může mít roli nejvyšší i nejnižší karty
•	poker tzv. four of a kind: čtveřice karet se stejnou hodnotou
•	full house: trojice karet se stejnou hodnotou a dvojice karet se stejnou hodnotou
•	barva tzv. flush: pětice karet se stejnou barvou
•	postupka tzv. straight: pět po sobě jdoucích karet, eso může mít roli nejvyšší i nejnižší karty
•	trojice tzv. three of a kind: trojice karet se stejnou hodnotou
•	dva páry tzv. two pair: dvě dvojice karet se stejnou hodnotou
•	pár tzv. pair: dvojice karet se stejnou hodnotou
•	vysoká karta tzv. high card: v případě že hráč není schopen vytvořit žádnou z výše zmíněných kombinací, tak hraje pouze na hodnotu nejvyšší karty, kterou má
Pokud nastane situace, že více hráčů má stejnou kombinaci, tak se porovnává, kdo má vyšší hodnotu této kombinace čili:
•	u čisté postupky se porovnává hodnota nejvyšší karty obsažené v ní
•	u pokeru se porovnává hodnota čtveřice karet
•	u full housu se porovnává hodnota trojice karet a pokud ta je shodná, tak se porovnává hodnota dvojice
•	u barvy se porovnává hodnota nejvyšší karty této barvy a pokud ta je shodná, tak se porovnává druhá, třetí atd. nejvyšší karta
•	u postupky se porovnává hodnota nejvyšší karty obsažené v ní
•	u trojice se porovnává hodnota trojice karet
•	u dvou párů se porovnává hodnota vyššího z párů, popřípadě nižšího z párů
•	u páru se porovnává hodnota páru
•	u vysoké karty se porovnává hodnota vysoké karty
Pokud i porovnání hodnoty kombinace vyšlo u více hráčů stejně a jedná se o kombinaci, která využila všech pět karet (tedy čistá postupka, full house, barva, postupka), tak se rozdělí peníze v potu mezi zbývajícími hráči.
Pokud se jedná o kombinaci, která nevyužila všech pět karet (tedy poker, trojice, dva páry, pár, vysoká karta), tak se požívá tzv. kicker. Kicker je karta, která je mimo samotnou kombinaci, s nejvyšší hodnotou. U zbývajících hráčů se porovná kicker a ten s nejvyšším kickerem vyhraje, pokud je první kicker u zbývajících hráčů shodný, a do pěti karet je ještě vejde další (v případě trojice, páru a vysoké karty), tak se použije druhý kicker, pokud i ten je shodný tak se může použít i třetí kicker (u páru a vysoké karty), pokud i ten je shodný tak se může použít i čtvrtý kicker (u vysoké karty), pokud i čtvrtý kicker je u zbývajících hráčů shodný, tak se žetony mezi zbývajícími hráči rozdělí.





