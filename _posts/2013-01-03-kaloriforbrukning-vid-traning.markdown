---
layout: post
published: true
title: Kaloriförbrukning
excerpt: Räkna ut din kaloriförbrukning.
logo: calculator.jpg
title2: Kaloriförbrukning
keywords: kalori,förbrukning,kaloriförbrukning,met,träning,energiförbrukning,kalkylator
description: Räkna ut hur många kalorier du förbrukat under träningen. Energiförbrukning vid olika typer av aktiviteter kan räknas ut med hjälp av enheten MET, metabolic equivalent.
categories:
- Kalkylator
tags:
- Kalkylator
- kaloriförbrukning
- MET
- Träning
- energiförbrukning
comments: []
---
<p class="lead">
Energiförbrukning vid olika typer av aktiviteter kan räknas ut med hjälp av enheten MET, metabolic equivalent. MET är den relativa skillnaden i förbrukning mellan olika aktiviteter. Tillsammans med vikt, ålder och tid kan man med hjälp av nedanstående ekvation räkna ut ett uppskattat värde av kaloriförbrukningen för en aktivitet.
</p>

<strong>Vikt (kg) x Tid (timmar) x Intensiteten (METs) = Energiförbrukning (kcal)</strong>

Energiförbrukningen skiljer sig åt mellan individer och beror bland annat på kön, ålder,  muskelmassa, vikt och träningsintensitet. I uträkningen nedan räknar du ut hur många <strong>extra kalorier</strong> som förbrukas genom din ökade aktivitet.

<div id="contact-form">

<form>
	<fieldset>
	  <div class="half">
	      <label for="weight">Vikt (kg)</label>
		  <input id="weight" name="weight" type="text" onchange="calculate()" onfocus="if (this.value == 'Ange vikt...') { this.value = ''; }" onblur="if(this.value == '') { this.value = 'Ange vikt...'; }" value="Ange vikt..." size="20"/>
	  </div>
	  <div class="half pull-right">
	      <label for="time">Tid (min)</label>
		  <input id="time" name="time" type="text" onchange="calculate()" onfocus="if (this.value == 'Ange tid...') { this.value = ''; }" onblur="if(this.value == '') { this.value = 'Ange tid...'; }" value="Ange tid..." size="29"/>
	  </div>
	  <div class="half">
	      <label for="activity">Aktivitet</label>
		  <select style="height: 60px" id="activity" name="activity" onchange="calculate()">
		  	<option>Välj</option>
		  	<option value="7.5">Aerobics</option>
		  	<option value="5">Basket</option>
		  	<option value="7">Beachvolleyboll</option>
		  	<option value="8">Boxning</option>
		  	<option value="5">Brottning</option>
		  	<option value="7">Cykling</option>
		  	<option value="6">Fotboll</option>
		  	<option value="3.5">Golf</option>
		  	<option value="11">Handboll</option>
		  	<option value="7">Hockey</option>
		  	<option value="9">Kampsport</option>
		  	<option value="15">Löpning (3,75 min/km)</option>
		  	<option value="13">Löpning (4,5 min/km)</option>
		  	<option value="11.5">Löpning (5 min/km)</option>
		  	<option value="9">Löpning (6,25 min/km)</option>
		  	<option value="7">Löpning (7,5 min/km)</option>
		  	<option value="1.5">Promenad (Låg)</option>
		  	<option value="2.3">Promenad (Medel)</option>
		  	<option value="2.8">Promenad (Hög)</option>
		  	<option value="11.5">Roller blades</option>
		  	<option value="9">Rugby</option>
		  	<option value="9">Simning (Hög)</option>
		  	<option value="6">Simning (Låg-Medel)</option>
		  	<option value="6">Skidåkning</option>
		  	<option value="6">Skridskoåkning</option>
		  	<option value="2">Styrketräning (Lätt-Medel)</option>
		  	<option value="5">Styrketräning (Hård)</option>
		  	<option value="6">Tennis</option>
		  	<option value="2">Volleyboll</option>
		  </select>
	  </div>
	  <div class="half pull-right">
	      <label for="result">Beräknad förbrukning (kcal):</label>
		  <input id="result" name="result" type="text" readonly="readonly" />
		</div>
	 </fieldset>
	</form>

	Om du är intresserad av viktminskning eller effektiv styrketräning, läs vidare!
	<p><a href="{{ site.baseurl }}{% post_url 2011-12-02-tips-for-viktminskning %}">Tips för viktminskning</a><br>
	<a href="{{ site.baseurl }}{% post_url 2012-01-03-oka-i-muskelmassa-del-1 %}">Öka i muskelmassa</a></p>

</div>

<script type="text/javascript">

function calculate() {

	var met = document.getElementById("activity").value;
	var weight = document.getElementById("weight").value;
	var mins = document.getElementById("time").value;

	if ( (met != 0) && (weight > 0) && (mins > 0)) {
		var kcal = weight * (mins/60) * met;
		kcal = Math.round(kcal);
		document.getElementById("result").value = kcal;
	}
}
</script>
