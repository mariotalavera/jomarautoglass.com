---
exclude: true
layout: page
title: Jomar Auto Glass - Cuestionario de Servicio
permalink: /cuestionario/
metadescription: Jomar Auto Glass. Cuestionario de servicio al cliente.
---

<form name="cuestionariodeservicio" id="cuestionariodeservicio" data-netlify="true" method="post" action="{{ site.baseurl }}/cuestionario_response/index.html">
	<input type="hidden" name="data-netlify" value="true" />
	<fieldset>
	<legend>Acerca de nuestro servicio</legend>	
	<div>
		<label for="Uso_Jomar" style="vertical-align: top">¿Uso a Jomar?</label>
		<input type="radio" name="Uso_Jomar" value="Si" style="width: 40px;">Si
		<input type="radio" name="Uso_Jomar" value="No" style="width: 40px;">No
	</div>
	<div>
		<br/>¿Si no uso a Jomar, nos podría ayudar a entender porque?
	</div>
	<div class="checkbox">
		<input type="checkbox" name="Razon_1" value="Muy dificil hacer cita">
		<label for="Razon_1">Muy difícil hacer cita.</label><br/>
		<input type="checkbox" name="Razon_2" value="Precios altos">
		<label for="Razon_2">Precios altos.</label><br/>
		<input type="checkbox" name="Razon_3" value="Jomar no tiene lo que necesita.">		
		<label for="Razon_3">Jomar no tiene lo que necesita.</label>
	</div>
	<div>	
		<label for="Razon_Otra" style="width: 100%;"><br/>¿Otra Razon?</label>
		<textarea name="Razon_Otra" style="width:90%; height:60px"></textarea>
	</div>
	</fieldset>
	<fieldset>
	<legend>Su información (Si quiere que nos comuniquemos con usted.)</legend>	
	<div>
		<label for="Nombre">Nombre:</label>
		<input type="text" name="Nombre" />
	</div>
	<div>
		<label for="Correo_Electronico">Correo Electrónico:</label>
		<input type="email" name="Correo_Electronico"  id="Correo_Electronico" >
	</div>
	<div>
		<label for="Telefono">Teléfono:</label>
		<input type="tel" name="Telefono" />
	</div>
	</fieldset>
	<div class="button" align="center"><br/>
		<button type="submit" value="submit" class="myButton">Enviar</button>
	</div>
</form>
