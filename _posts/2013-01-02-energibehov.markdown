---
layout: post
published: true
title: Energibehov
excerpt: Se hur mycket energi du förbränner genom din träning.
logo: calculator.jpg
title2: Räkna ut ditt energibehov | fettfri.nu
keywords: energibehov,harris&benedict,harris & benedict,kalkylator
description: Räkna ut ditt energibehov med hjälp av Harris & Benedict principen.
categories:
- Kalkylator
tags:
- energibehov
- Harris &amp; Benedict
- Kalkylator
---
<p class="lead">
Kroppen förbränner kalorier genom att bara fungera. Den mängd energi som går åt för detta kallas kroppens basala energibehov. Nedan kan du räkna ut ditt ungefärliga dagsbehov av energi med hjälp av <a title="Harris &amp; Benedict principen" href="http://en.wikipedia.org/wiki/Harris-Benedict_equation">Harris &amp; Benedict</a> principen. Denna går ut på att man räknar ut sin <a title="Basal metabolic rate" href="http://en.wikipedia.org/wiki/Basal_metabolic_rate">BMR</a> (Basal metabolic rate) och sedan multiplicerar denna med en aktivitetsnivå.
</p>

<div id="contact-form">
<form>
	<fieldset>
	  <div class="half">
		  <label for="kroppsvikt">Kroppsvikt (kg)</label>
		  <input id="kroppsvikt" name="kroppsvikt" type="text" onfocus="if (this.value == 'Ange vikt...') { this.value = ''; }" onblur="if(this.value == '') { this.value = 'Ange vikt...'; }" value="Ange vikt..." size="20"/> 
	  </div>
	  <div class="half pull-right">
		  <label for="langd">Längd (cm)</label>
		  <input id="langd" name="langd" type="text" onfocus="if (this.value == 'Ange längd...') { this.value = ''; }" onblur="if(this.value == '') { this.value = 'Ange längd...'; }" value="Ange längd..." size="29"/>
	  </div>
	  <div class="half">
		  <label for="alder">Ålder</label>
		  <input id="alder" name="alder" type="text" onfocus="if (this.value == 'Ange ålder...') { this.value = ''; }" onblur="if(this.value == '') { this.value = 'Ange ålder...'; }" value="Ange ålder..." size="20"/> 
	  </div>
	  
 	  <div class="half pull-right">
		  <label for="aktivitetsniva">Aktivitetsnivå:</label>
		  <select id="aktivitetsniva" name="aktivitetsniva" style="height: 60px"> 
		  	<option value="1.2">Lite eller ingen träning</option> 
		  	<option value="1.375">Lätt träning (1-3 ggr/vecka)</option> 
		  	<option value="1.55">Medelhård träning (3-5 ggr/vecka)</option> 
		  	<option value="1.725">Hård träning (6-7 ggr/vecka)</option> 
		  	<option value="1.9"> Mycket hård träning (2 ggr/dag)</option> 
		  </select>
	  </div>
 	  <div class="half">
		  <label for="kon">Kön:</label>
		  <select id="kon" name="kon" style="height: 60px" value="kvinna"> 
		  	<option value="kvinna">Kvinna</option> 
		  	<option value="man">Man</option> 
		  </select>
	  </div>
	  <div class="half pull-right">
		  <label for="rakna">&nbsp;</label>
		  <input id="rakna" onclick="calculate()" name="rakna" type="button" value="Räkna ut" />
	  </div>
 	  <div class="half pull-right">
		  <label for="energi">Energibehov (Kcal):</label>
		  <input id="energi" name="energi" readonly="readonly" type="text" size="35" />
	  </div>
	  </fieldset>
	</form>
</div>

<script type="text/javascript">
	function calculate()
	{
		var vikt = document.getElementById("kroppsvikt").value;
		var alder = document.getElementById("alder").value;
		var langd = document.getElementById("langd").value;
		var kon = document.getElementById("kon").value 
		var result = 0;

		if (kon == "kvinna") {
			result = 655 + (9.6*vikt) + (1.8*langd) - (4.7*alder);
		} else {
			result = 66 + (13.7*vikt) + (5*langd) - (6.8*alder);
		}
		var aktivitet = document.getElementById("aktivitetsniva").value;
       result = result * aktivitet;

		if (isNaN(result)) {
			alert('Fel i uträkningen. Kontrollera dina inmatade värden. Använd punkt som skiljetecken för eventuella decimaler.');
			document.getElementById("energi").value = 'Fel';
		} else {
			document.getElementById("energi").value = Math.round(result);
		}
	}
</script>
