---
author: Smári McCarthy
date: 2015-04-15
language: is
tags: [Ríkisútgjöld, Hugbúnaður]
title: Sokkinn kostnaður ríkisins í hugbúnaðargerð
---

Kastljósið varpaði ljósi á gríðarlega spillingu í fyrradag, þar sem fyrirtækkið Forsvar ehf. hafði tekið að sér mörg verkefni fyrir ríkisstofnanir, og skilaði aðeins einu þeirra af sér, í hálfkláruðu lagi. Spillingin fólst í því að verkefnið var ekki boðið út, og það var sett í hendurnar á fyrirtæki í eigu manns sem var vel tengdur inn í kerfið.

Þessi frásögn er merkileg fyrir margar sakir, en kannski ekki síst vegna þess hvað þetta er dæmigerð saga af hugbúnaðarverkefnum, bæði almennt, og sér í lagi innan ríkja. Það er með ólíkindum annars vegar hversu miklum peningum er kastað á glæ í hugbúnaðargerð, og hversu mörg hugbúnaðarverkefni floppa algjörlega. Þeir sem vinna í tæknigeiranum hafa ýmist séð jafnvel dýr, framsýn og vinsæl verkefni floppa, eða ekki verið lengi að. Það eru ýmsar ástæður fyrir því.

Hugbúnaður er búinn til með því að fólk skrifar langar ræmur af texta í einhverju forritunarmáli -- þessi texti er kallaður "kóði". Forritunarmál svipa til mannamáls að mörgu leyti, en eru frekar formföst og rökræn. Tölvur gera ekki mistök, þær gera bara nákvæmlega það sem forritarar segja þeim að gera. Því skiptir höfuðmáli að forritarar séu gríðarlega vandvirkir, og lýsi mjög nákvæmlega fyrir tölvunni hver ætlunin er.

En forritarar eru brigðulir eins og annað fólk. Það er því ótrúlega mikilvægt að vanda eins vel til verka við hönnun kerfa og hægt er, til að vandamál komi síður upp. Í fyrstu þarf að ákveða hvað forritinu er ætlað að gera. Þetta kann að hljóma einfalt, en það er oft sem þetta grundvallaratriði gleymist, eða, sem er verra, fólk heldur að það sé búið að ákveða það, en er í rauninni enn með óljósa hugmynd um það.

Í gamla daga þá lagði fólk oft upp með illa skilgreind verkefni, sem gerði það oftast að verkum að verkkaupendur og verktakar höfðu sitthvora hugmyndina um hvað stæði til að gera. Þetta kemur enn fyrir, en það færist í aukanna að fólk skilgreini "lágmarksverkefni" (e. "minimum viable product"), sem inniheldur alla þá eiginleika sem forritið verður að hafa, en útilokar allt sem væri gaman að hafa, en er ekki bráðnauðsynlegt. Sú útgáfa er gerð á stuttum tíma, eftir mjög vel skilgreindum lista, og svo er farið í ítrekað útgáfuferli þar á eftir, þar sem allir eru á sömu blaðsíðu. Þetta minnkar tæknilega áhættu og kostnað. Mantran er "release early, release often" -- það er alltaf hægt að búa til nýja útgáfu, en það er aldrei hægt að ná til baka hálft ár af þróunartíma sem fór til spillis vegna þess að fólk misskildi hvort annað.

Í gamla daga, þegar forrit voru tilbúin, þá voru þau prufukeyrð aðeins, handvirkt, og ef allt leit út fyrir að virka þá var það samþykkt og sent út. Svo byrjaði hugbúnaðurinn að hrynja trekk í trekk, þegar notendur gerðu hluti sem forriturunum datt ekki í hug að prófa -- yfirleitt órökréttar aðgerðarunur sem gengu gegn upprunalegri hönnun forritsins (en voru fullkomnlega skynsamar í huga notandans!).

Til að stemma stigum við þetta er gott að búa til próf áður en þróun hugbúnaðarins hefst: einingapróf, sem sannreyna virkni allra skilgreindra eininga, samþættipróf, sem sannreyna virkni eininganna í heild, og samþykkispróf, sem sannreyna að hugbúnaðurinn uppfylli kröfur notandans. Prófin eru í rauninni forrit sem keyra forritið undir mismunandi skilyrðum.

Það besta við þetta er að prófin eru í rauninni kerfislýsing, og verkefninu er lokið þegar forritið stenst öll prófin. Sem verkefnisstjóri forritunarteymis, þá er stór hluti af vinnunni minni að búa til kerfislýsingar og búa til haug af prófum, sem svo forritarnir í teyminu mínu sjá svo um að uppfylla.

Nú er margt fleira sem gerir greinarmuninn á góðu og slæmu húgbúnaðarþróunarferli. Allt of margir forritarar eru mjög tregir við að tala við notendur, til að mynda -- þrátt fyrir að það eru notendurnir sem eiga eftir að þola hugbúnaðinn, hvernig sem hann endar. Allt of oft er hugbúnaður þróaður "í nefnd", án þess að tæknilegur raunveruleiki eða raunverulegar kröfur notandanna séu teknar inn í reikninginn. Og því miður líta flestir bæði innan og utan hugbúnaðargeirans á forritun sem handahófskennt dútl, frekar en iðju sem krefst fagmennsku. Vondir vinnusiðir eru gegnumgangandi.

En alveg sama hversu vel er að verki staðið, þá kemur það stundum fyrir að verkefni nær ekki að gera það sem því var ætlað, eða að þeir sem eru að forrita það hafa ekki næga reynslu til að leysa verkefnið, eða það er svo illa skilið í upphafi að það fer fram úr kostnaðaráætlun. Í þeim tilfellum gætir tilhneyging til hugsa á það leið að fyrst við erum búin að eyða X milljónum í þetta verkefni, ef við klárum það ekki, þá erum við búin að sóa þessum X milljónum í ekkert. Þetta er hugsunarvilla -- svokallað "sunken costs fallacy", og er í rauninni jafngilt því þegar fólk heldur áfram að vera í ofbeldisfullu sambandi í þeirri trú að það muni skána.

Hugbúnaðarverkefni á vegum opinberra stofnanna eru nánast alltaf eins of ofbeldisfull sambönd. Verktakarnir vita að verkkaupendur skilja lítið í tækninni, að ríkið er rosalega seinviljugt til að sætta sig við klúðrað verkefni, og að vasar ríkisins eru í rauninni óendanlega djúpir. Þessi blanda er baneitruð.

Þegar teknar eru ákvarðanir um hugbúnaðarþróun, sérstaklega hjá ríkisvaldinu, þá er ótrúlega mikilvægt að sjá til þess að það líði aldrei meira en vika milli þess sem afurðin er skoðuð og gæðavottuð, að það líði helst ekki meira en dagur milli nýrra útgáfa, og að allt apparatið sé þróað á þannig hátt að það sé alltaf hægt að stoppa, fari það af leið.

Að lokum er annað nauðsynlegt öllum hugbúnaðarverkkaupum, og það er að þeir hafi vald yfir kóðanum sem til verður, en ekki verktakinn. Helst með því að kóðinn sé opinn og frjáls (e. free/open source software). Þetta eykur endurnýtanleika, minnkar þróunartíma, og tryggir að sé einn verktaki í rauninni spilltur aðili sem situr báðum megin borðsins, þá sé hægt að skipta honum út fyrir annan verktaka með litlum tilkostnaði.


