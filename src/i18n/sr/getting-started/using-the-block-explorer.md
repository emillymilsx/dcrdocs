# <i class="fa fa-cubes"></i> Коштење Блок Експлорера 

---

## <i class="fa fa-info-circle"></i> Преглед

Блок истраживач базиран на
[Insight](https://github.com/bitpay/insight-ui) је обезбеђен за
Децред мрежу. Сви блокови и трансакције у декодираном блокчејну видљиви су кориштењем овог блок истраживача, који се налази на
[`https://mainnet.decred.org`](https://mainnet.decred.org) и
[`https://testnet.decred.org`](https://testnet.decred.org) за
Тестнет новчаник. Испод је брзи преглед неких информација
то.

Опција         | Објашњење
---            | ---
`Height`       | Број блока.
`Age`          | Прије колико је блок додат у блокчејн
`Transactions` | Број трансакција укључених у блок.
`Votes`        | Број PoS гласова укључених у блок.
`Fresh Stake`  | Број нових карата купљених у овом блока.
`Size`         | Величина (у бајтовима) блока.

Под 'Најновије трансакције', можете видети ИД трансакције (ткид) и вредност (у ДЦР)која се преноси преко мреже.

---

## <i class="fa fa-cube"></i> Блокови 

Блокови се могу пронаћи тако што ћете претраживати њихов број,
кликом на висину вредности са почетне странице или из њихове
`BlockHash` вредност. Старији блокови ће имати ниже бројеве блока. Горња половина прегледа блока показује релевантне информације о томе
. Ова информација укључује: висину блока, блок хеш и неколико кључних мрежних параметара, описаних у наставку:

Опција                   | Објашњење
---                      | ---
`Number of Transactions` | Број стандардних трансакција (ДЦР послао од једног корисника до другог).
`Height`                 | Висина блока у којој се налази овај блок.
`Block Reward`           | Количина новог DCR а кованог у овом блока.
`Timestamp`              | Време када је овај блок створио претраживач и био је укључен у блокчејн.
`Merkle Root`            | Хеш вредност свих трансакција  укључене у овај блок.
`Stake Root`             | Хеш вредност свих хеш трансакција везаних за улоге у овом блока. Ово укључује куповину карата, гласове и ревокације карата.
`VoteBits`               | (1) Блок је одобрен од стране бирача који се баве учешћем. (2) Блок је ставио вето на бираче који се баве учешћем и све невладине трансакције у блоку су неважеће, заједно са претраживањем доказа о раду и субвенцијама за развој.
`Final State`            | Коначно стање генератора псеудо насумичног броја који се користи за избор карата.
`Voters`                 | Број успешних гласова који се доказују у овом сегменту. Максимална вредност је 5.
`Fresh Stake`            | Број куповине улога потврђен у овом блока.
`Revocations`            | Број карата који нису гласали и били су поништени.
`PoolSize`               | Укупан број активних карата за PoW.
`Difficulty`             | Тешкоћа мреже доказа о раду.
`SBits`                  | Цена једне доказне карте.
`Bits`                   | Компактна верзија мрежне тешкоће у тренутку када је блок миниран.
`Size`                   | Величина блока (у бајтовима).
`Version`                | Верзија блока.
`Nonce`                  | Вредност коју рудар користи да би пронашао исправно решење за овај блок.

## <i class="fa fa-exchange"></i> Трансакције 

Овај одељак наводи све трансакције које су претражене у овом
блоку. Трансакције се бирају из мрежног мемпула у распореду
Највиша цијена најпре. Пратите све трансакције у прегледу блока
Налог: Стандардне трансакције (пир-то-пир трансфер), proof-of-stake
Гласова, куповине доказних предмета. У следећем одељку ће бити појашњена свака врста трансакције..

---

### Стандардне трансакције

Ево информација укључених у стандардне трансакције.

Опција              | Објашњење
---                 | ---
`Size`              | Величина трансакције у бајтовима.
`Fee rate`          | Стопа такси прикупљених од стране мреже (per kB).
`Received Time`     | Време када је мрежа потврдила трансакцију.
`Mined Time`        | Време кад је претраживач укључио трансакцију у блок.
`Included in Block` | Број блока у који се одвила трансакција.

Напомена `Received Time`, `Mined Time`, и `Included in Block` неће имати вриједност док претраживач не потврди трансакцију и укључи га у декодирани блок. После потврде у блоку, трансакција се сматра комплетном.


---

### Куповина улазница

За куповину карата (подношење улога) постоји неколико разлика
Из стандардне трансакције приказане.

Забележите разлику у детаљу: Ријеч `Ticket` се појављује изнад
Адреса пошиљаоца на левој страни, и ријечи "Субсиди"
Посвећеност "појављују се десно. Овај корисник је купио а
Улазницу за 8.75411638 ДЦР и примио промјену у износу
Од 7.15994209 ДЦР. Адреса наведена на левој страни испод `Карта` је
Адреса која садржи средства која се користе за куповину овог
Карта. Први излаз на десној страни је адреса која задржава
Право гласа за ову специфичну карту. Други излаз, `Субсиди
Обавеза`, је адреса на којој ће награда ићи. Ово још није
У овом тренутку показује блок истраживач. Трећи и завршни резултат
Адреса где ће се послати промјена за ову трансакцију.

---

### Доказни улог

Примените изразе у одељку детаљи: `Vote`, `Улог
Основа`, `Обавезе блока`, и `Гласови`:

Ове кључне речи указују на то да је ова трансакција гласање које је објављено
Од носиоца доказа о власништву. У овом конкретном примеру,
Корисник је раније купио карту за 8.99472311 ДЦР и био је
Послали су 10.82959184 ДЦР након што је гласање било у овој трансакцији.