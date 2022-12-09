## Kūrėjo versija (Development branch)

<font color="#FF0000"><strong>Dėmesio:</strong></font>
„Kūrėjo versija“ yra skirta tik tolesniam AndroidAPS tobulinimui. Jis gali būti naudojamas tik atskirame išmaniajame telefone bandymo tikslais, <font color="#FF0000"><strong>o ne realiam ciklui</strong></font>

Stabiliausia AndroidAPS versija, kurią galima naudoti [Master branch](https://github.com/nightscout/AndroidAPS/tree/master). Realiam cikui rekomenduojama naudoti tik Master branch.

AndroidAPS kūrėjo versija yra skirta kūrėjams ir testuotojams, kurie gali tvarkyti programos įrašus, žurnalo failus ir galbūt suaktyvinti derinimo įrankį, kad būtų parengtos klaidų ataskaitos, kurios naudingos kūrėjams (trumpai tariant, žmonėms, kurie tai žino ką daro ir dirba savarankiškai). Todėl daugelis nebaigtų funkcijų yra išjungtos. To enable these features enter **Engineering Mode** by creating a file named `engineering_mode` in directory /AAPS/extra . Įjungę inžinerinį režimą, galite visiškai sugadinti ciklą.

Tačiau kūrėjo versija yra gera vieta pamatyti, kokios funkcijos yra tikrinamos, ir padėti pašalinti klaidas bei pateikti atsiliepimus apie tai, kaip naujos funkcijos veikia praktiškai. Dažnai žmonės išbando kūrėjo versiją su senu telefone ir pompa, kol įsitikina, kad versija stabili - už bet kokį jos naudojimą atsakingi esate tik jūs patys. Testuodami bet kokias naujas funkcijas, atminkite, kad nusprendėte išbandyti vis dar kuriamą funkciją. Darykite tai savo rizika, tačiau atsargiai, kad apsaugotumėte save.

Jei radote klaidą arba manote, kad naudojant kūrėjo versiją nutiko kažkas neprimtino, tada peržiūrėkite skirtuką [problemos](https://github.com/nightscout/AndroidAPS/issues) ir patikrinkite, ar kas nors kitas šią problemą rado, arba pridėkite patys, jei esate pirmasis. Kuo daugiau informacijos galite pasidalyti čia, tuo geriau (nepamirškite, kad gali tekti dalintis savo [ žurnalo failais](../Usage/Accessing-logfiles.md). The new features can also be discussed on [discord](https://discord.gg/4fQUWHZ4Mw).

A dev version has an expiration date. This seems inconvenient when using it satisfactorily, but serves a purpose. When a single dev version doing the rounds, it is easier to keep track of bugs that people are reporting. The developers do not want to be in a position where there are three versions of dev in the wild where bugs are fixed in some and not others, and people continue to report the fixed ones.